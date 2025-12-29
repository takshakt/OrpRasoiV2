# Orpington Rasoi V2 — Deployment Plan

## Project Overview

**Objective**: Deploy a production-ready restaurant storefront with Stripe payments and admin backend
**Technology**: MedusaJS v2 + Next.js Storefront
**Target**: OCI Compute Instance
**Timeline**: Same-day deployment

---

## Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                     OCI Compute Instance                        │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  ┌─────────────┐    ┌─────────────┐    ┌─────────────┐         │
│  │   Nginx     │    │   Medusa    │    │  Next.js    │         │
│  │   Reverse   │───▶│   Backend   │◀───│  Storefront │         │
│  │   Proxy     │    │   :9000     │    │   :8000     │         │
│  │   :80/443   │    └──────┬──────┘    └─────────────┘         │
│  └─────────────┘           │                                    │
│                            │                                    │
│              ┌─────────────┼─────────────┐                      │
│              │             │             │                      │
│        ┌─────▼─────┐ ┌─────▼─────┐       │                      │
│        │ PostgreSQL│ │   Redis   │       │                      │
│        │   :5432   │ │   :6379   │       │                      │
│        └───────────┘ └───────────┘       │                      │
│                                          │                      │
└─────────────────────────────────────────────────────────────────┘
                            │
                            ▼
                    ┌───────────────┐
                    │    Stripe     │
                    │     API       │
                    └───────────────┘
```

---

## Phase 1: Infrastructure Setup (30 minutes)

### Step 1.1: Prepare OCI Instance

```bash
# SSH into your OCI instance
ssh -i <your-key> opc@<your-instance-ip>

# Update system
sudo dnf update -y

# Install Docker (if not present)
sudo dnf install -y docker
sudo systemctl enable docker
sudo systemctl start docker
sudo usermod -aG docker $USER

# Install Docker Compose
sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# Verify
docker --version
docker-compose --version
```

### Step 1.2: Open Firewall Ports

```bash
# OCI Security List (via console or CLI)
# - Port 80 (HTTP)
# - Port 443 (HTTPS)

# Instance firewall
sudo firewall-cmd --permanent --add-port=80/tcp
sudo firewall-cmd --permanent --add-port=443/tcp
sudo firewall-cmd --reload
```

---

## Phase 2: Clone and Configure (45 minutes)

### Step 2.1: Clone Medusa Eats (Recommended Path)

```bash
cd /opt
sudo mkdir orpington-rasoi && sudo chown $USER:$USER orpington-rasoi
cd orpington-rasoi

# Clone Medusa Eats as base
git clone https://github.com/medusajs/medusa-eats.git .

# Or use standard starter if preferred:
# npx create-medusa-app@latest --with-nextjs-starter
```

### Step 2.2: Environment Configuration

Create `.env` files:

**Backend `.env`:**
```env
# Database
DATABASE_URL=postgres://medusa:medusa_password@postgres:5432/medusa_db

# Redis
REDIS_URL=redis://redis:6379

# JWT & Cookies
JWT_SECRET=your-super-secret-jwt-key-min-32-chars
COOKIE_SECRET=your-super-secret-cookie-key-min-32-chars

# Stripe
STRIPE_API_KEY=sk_live_YOUR_STRIPE_SECRET_KEY
STRIPE_WEBHOOK_SECRET=whsec_YOUR_WEBHOOK_SECRET

# Admin
ADMIN_CORS=https://admin.orpingtonrasoi.co.uk
STORE_CORS=https://orpingtonrasoi.co.uk

# Environment
NODE_ENV=production
```

**Storefront `.env.local`:**
```env
NEXT_PUBLIC_MEDUSA_BACKEND_URL=https://api.orpingtonrasoi.co.uk
NEXT_PUBLIC_MEDUSA_PUBLISHABLE_KEY=pk_xxxxx
NEXT_PUBLIC_STRIPE_KEY=pk_live_YOUR_STRIPE_PUBLISHABLE_KEY
```

---

## Phase 3: Docker Deployment (30 minutes)

### Step 3.1: Create docker-compose.yml

```yaml
version: '3.8'

services:
  postgres:
    image: postgres:15-alpine
    environment:
      POSTGRES_USER: medusa
      POSTGRES_PASSWORD: medusa_password
      POSTGRES_DB: medusa_db
    volumes:
      - postgres_data:/var/lib/postgresql/data
    restart: unless-stopped

  redis:
    image: redis:7-alpine
    restart: unless-stopped

  medusa-backend:
    build:
      context: ./backend
      dockerfile: Dockerfile
    depends_on:
      - postgres
      - redis
    environment:
      - DATABASE_URL=postgres://medusa:medusa_password@postgres:5432/medusa_db
      - REDIS_URL=redis://redis:6379
    env_file:
      - ./backend/.env
    ports:
      - "9000:9000"
    restart: unless-stopped

  storefront:
    build:
      context: ./storefront
      dockerfile: Dockerfile
    depends_on:
      - medusa-backend
    env_file:
      - ./storefront/.env.local
    ports:
      - "8000:3000"
    restart: unless-stopped

  nginx:
    image: nginx:alpine
    ports:
      - "80:80"
      - "443:443"
    volumes:
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf
      - ./nginx/ssl:/etc/nginx/ssl
    depends_on:
      - medusa-backend
      - storefront
    restart: unless-stopped

volumes:
  postgres_data:
```

### Step 3.2: Deploy

```bash
# Build and start
docker-compose up -d --build

# Check logs
docker-compose logs -f

# Run migrations (first time only)
docker-compose exec medusa-backend npx medusa db:migrate
```

---

## Phase 4: Initial Configuration (60 minutes)

### Step 4.1: Access Admin Dashboard

1. Navigate to `https://admin.orpingtonrasoi.co.uk`
2. Create admin user (first-time setup)
3. Complete initial store setup

### Step 4.2: Configure Store Settings

1. **Regions**: Add UK region with GBP currency
2. **Shipping Options**:
   - "Collection" — Free, 0 GBP
   - "Local Delivery" — Set your delivery fee
3. **Payment Providers**: Enable Stripe

### Step 4.3: Add Menu Items

1. Create Categories:
   - Starters
   - Main Courses
   - Biryanis
   - Breads
   - Sides
   - Drinks
   - Desserts

2. Add Products (menu items):
   - Name, description, price
   - Use variants for options (e.g., "Mild", "Medium", "Hot")
   - Upload food images

### Step 4.4: Stripe Webhook Configuration

1. Go to Stripe Dashboard → Developers → Webhooks
2. Add endpoint: `https://api.orpingtonrasoi.co.uk/hooks/payment/stripe`
3. Select events:
   - `payment_intent.succeeded`
   - `payment_intent.payment_failed`
4. Copy webhook secret to backend `.env`

---

## Phase 5: Go Live Checklist

### Pre-Launch
- [ ] All menu items added with correct prices
- [ ] Stripe test payment successful
- [ ] Delivery zones configured
- [ ] Order notification email/SMS configured
- [ ] SSL certificates active (Let's Encrypt)

### DNS Configuration
```
orpingtonrasoi.co.uk        A     <OCI-IP>
api.orpingtonrasoi.co.uk    A     <OCI-IP>
admin.orpingtonrasoi.co.uk  A     <OCI-IP>
```

### Launch
- [ ] Switch Stripe to live mode
- [ ] Update environment variables with live keys
- [ ] Restart services: `docker-compose restart`
- [ ] Place test order with real card
- [ ] Announce launch!

---

## Rollback Plan

If issues occur:
```bash
# Stop services
docker-compose down

# Restore previous version (if applicable)
git checkout <previous-commit>

# Restart
docker-compose up -d --build
```

---

## Support Resources

- [MedusaJS Documentation](https://docs.medusajs.com/)
- [Medusa Eats GitHub](https://github.com/medusajs/medusa-eats)
- [Next.js Starter](https://docs.medusajs.com/resources/nextjs-starter)
- [Stripe Integration](https://docs.medusajs.com/resources/commerce-modules/payment/payment-provider/stripe)
- [Restaurant Delivery Recipe](https://docs.medusajs.com/resources/recipes/marketplace/examples/restaurant-delivery)

---

## Customization Roadmap (Post-Launch)

### Week 1-2: Essential Enhancements
- Custom branding (logo, colors, fonts)
- Order notification system (email/SMS)
- Opening hours display
- "Kitchen closed" functionality

### Month 1: Nice-to-Have
- Customer accounts and order history
- Loyalty points system
- Discount codes for regulars
- WhatsApp order notifications

### Future: Growth Features
- Multiple location support
- Real-time order tracking
- Mobile app (React Native)
- Integration with accounting software
