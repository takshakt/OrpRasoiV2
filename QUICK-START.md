# Orpington Rasoi V2 — Quick Start Guide

## Fastest Path to Live (4-6 hours)

This guide prioritises getting you LIVE TODAY over perfect architecture.

---

## Option A: Medusa Eats Fork (Recommended)

**Why**: Already built for food ordering, less customization needed.

```bash
# On your local machine first (for faster iteration)
git clone https://github.com/medusajs/medusa-eats.git orpington-rasoi-v2
cd orpington-rasoi-v2

# Install dependencies
yarn install

# Start development (uses Docker for Postgres/Redis)
yarn dev
```

**Then customize:**
1. Remove multi-restaurant logic (you're single restaurant)
2. Remove driver dashboard (or keep for your delivery person)
3. Update branding
4. Deploy to OCI

---

## Option B: Standard Starter (Simpler, More Generic)

**Why**: Cleaner codebase, but needs more customization for food.

```bash
npx create-medusa-app@latest orpington-rasoi-v2 --with-nextjs-starter

cd orpington-rasoi-v2

# Start backend
cd backend && yarn dev

# In another terminal - start storefront
cd storefront && yarn dev
```

---

## Critical Environment Variables

### Backend `.env`
```env
DATABASE_URL=postgres://localhost/medusa-store
REDIS_URL=redis://localhost:6379
JWT_SECRET=supersecret-min-32-characters-long
COOKIE_SECRET=supersecret-min-32-characters-long
STRIPE_API_KEY=sk_test_xxxxx
```

### Storefront `.env.local`
```env
NEXT_PUBLIC_MEDUSA_BACKEND_URL=http://localhost:9000
NEXT_PUBLIC_MEDUSA_PUBLISHABLE_KEY=pk_xxxxx
NEXT_PUBLIC_STRIPE_KEY=pk_test_xxxxx
```

---

## First Hour Checklist

- [ ] Clone repository
- [ ] Install dependencies
- [ ] Start development server
- [ ] Access admin at http://localhost:9000/app
- [ ] Create admin account
- [ ] Add one test product
- [ ] View product on storefront http://localhost:8000

---

## Second Hour: Stripe Setup

1. Go to [Stripe Dashboard](https://dashboard.stripe.com)
2. Get API keys (use TEST keys first)
3. Add to `.env` files
4. Enable Stripe in Medusa Admin → Settings → Payment Providers
5. Test checkout flow

---

## Third Hour: Add Your Menu

Use Medusa Admin to add:

### Categories (Collections)
- Starters
- Main Courses
- Biryanis
- Breads & Rice
- Sides
- Beverages

### Products (Your Menu Items)
For each item:
- Title: "Chicken Tikka Masala"
- Description: Your menu description
- Price: £12.95
- Variants (optional): Mild/Medium/Hot
- Images: Food photos

**Pro tip**: Add 5-10 items first, go live, add rest later.

---

## Fourth Hour: Deploy to OCI

See [DEPLOYMENT-PLAN.md](./DEPLOYMENT-PLAN.md) for detailed steps.

Quick version:
```bash
# On OCI instance
git clone <your-repo> /opt/orpington-rasoi
cd /opt/orpington-rasoi
docker-compose up -d --build
```

---

## Go Live Minimum Requirements

You can go live with just:
- [ ] 10+ menu items (add more later)
- [ ] Stripe in LIVE mode
- [ ] Collection option enabled
- [ ] Working checkout flow
- [ ] Your domain pointing to OCI

**Everything else can wait.**

---

## Emergency Contacts & Resources

- Medusa Discord: https://discord.gg/medusajs
- Stripe Support: https://support.stripe.com
- Next.js Docs: https://nextjs.org/docs
