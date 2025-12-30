# MedusaJS v2 Deployment — Orpington Rasoi V2

## Status: DEPLOYED

## Server Details
- **Host:** ubuntu@132.145.19.17
- **Server Name:** pt-prod
- **Architecture:** ARM64 (aarch64)
- **Docker:** v28.1.1
- **Reverse Proxy:** Caddy

## Deployment Location
- **Path:** `/home/ubuntu/docker/orprasoi-v2`
- **MedusaJS Version:** 2.12.3

## Running Services

| Container | Image | Status | Port |
|-----------|-------|--------|------|
| orprasoi-v2-backend | orprasoi-v2-backend | Running | 9000 |
| orprasoi-v2-postgres | postgres:15-alpine | Healthy | 5432 |
| orprasoi-v2-redis | redis:7-alpine | Healthy | 6379 |

## Domains

| Domain | Status | Points To |
|--------|--------|-----------|
| api.orpingtonrasoi.co.uk | Working | Backend API |
| admin.orpingtonrasoi.co.uk | Working | Admin Panel |
| orpingtonrasoi.co.uk | Placeholder | Storefront (coming soon) |

## Admin Credentials

- **Email:** admin@orpingtonrasoi.co.uk
- **Password:** OrpRasoi2024!

---

## Configuration Files

### /home/ubuntu/docker/orprasoi-v2/docker-compose.yml
```yaml
services:
  postgres:
    image: postgres:15-alpine
    container_name: orprasoi-v2-postgres
    environment:
      POSTGRES_USER: medusa
      POSTGRES_PASSWORD: medusa_secret_2024
      POSTGRES_DB: medusa_db
    volumes:
      - orprasoi_v2_postgres:/var/lib/postgresql/data
    networks:
      - orprasoi-v2-network
    restart: unless-stopped
    healthcheck:
      test: ["CMD-SHELL", "pg_isready -U medusa -d medusa_db"]
      interval: 10s
      timeout: 5s
      retries: 5

  redis:
    image: redis:7-alpine
    container_name: orprasoi-v2-redis
    networks:
      - orprasoi-v2-network
    restart: unless-stopped
    healthcheck:
      test: ["CMD", "redis-cli", "ping"]
      interval: 10s
      timeout: 5s
      retries: 5

  backend:
    build:
      context: .
      dockerfile: Dockerfile
    container_name: orprasoi-v2-backend
    depends_on:
      postgres:
        condition: service_healthy
      redis:
        condition: service_healthy
    env_file:
      - .env.production
    expose:
      - "9000"
    networks:
      - orprasoi-v2-network
      - caddy_default
    restart: unless-stopped

networks:
  orprasoi-v2-network:
    driver: bridge
  caddy_default:
    external: true

volumes:
  orprasoi_v2_postgres:
```

### /home/ubuntu/docker/orprasoi-v2/.env.production
```env
DATABASE_URL=postgres://medusa:medusa_secret_2024@postgres:5432/medusa_db?sslmode=disable
REDIS_URL=redis://redis:6379
JWT_SECRET=orprasoi_jwt_secret_2024_xK9mN3pQ7tR
COOKIE_SECRET=orprasoi_cookie_secret_2024_vL8wR2sT5
STORE_CORS=https://orpingtonrasoi.co.uk
ADMIN_CORS=https://admin.orpingtonrasoi.co.uk
AUTH_CORS=https://orpingtonrasoi.co.uk,https://admin.orpingtonrasoi.co.uk
NODE_ENV=production
MEDUSA_ADMIN_ONBOARDING_TYPE=default
BACKEND_URL=https://api.orpingtonrasoi.co.uk
STORE_URL=https://orpingtonrasoi.co.uk
```

### /home/ubuntu/docker/orprasoi-v2/Dockerfile
```dockerfile
FROM node:20-alpine

WORKDIR /app

# Install build dependencies
RUN apk add --no-cache python3 make g++

# Install yarn
RUN corepack enable && corepack prepare yarn@1.22.22 --activate

# Copy package files
COPY package.json yarn.lock .yarnrc.yml ./

# Install dependencies
RUN yarn install --frozen-lockfile

# Copy source code
COPY . .

# Build the application
RUN yarn build

# Copy admin build from .medusa/server/public to /app/public for production serving
# This fixes MedusaJS v2.12.3 path resolution issue where admin-bundler looks for
# index.html in ./public/admin but build outputs to .medusa/server/public/admin
RUN cp -r .medusa/server/public ./public || true

# Expose port
EXPOSE 9000

# Start command
CMD ["yarn", "start"]
```

### /home/ubuntu/docker/orprasoi-v2/medusa-config.ts
```typescript
import { loadEnv, defineConfig } from "@medusajs/framework/utils"

loadEnv(process.env.NODE_ENV || "development", process.cwd())

module.exports = defineConfig({
  admin: {
    backendUrl: process.env.BACKEND_URL || "http://localhost:9000",
  },
  projectConfig: {
    databaseUrl: process.env.DATABASE_URL,
    redisUrl: process.env.REDIS_URL,
    http: {
      storeCors: process.env.STORE_CORS!,
      adminCors: process.env.ADMIN_CORS!,
      authCors: process.env.AUTH_CORS!,
      jwtSecret: process.env.JWT_SECRET || "supersecret",
      cookieSecret: process.env.COOKIE_SECRET || "supersecret",
    }
  }
})
```

---

## Caddy Configuration (Added to Caddyfile)

```
# Orpington Rasoi V2 - MedusaJS
api.orpingtonrasoi.co.uk {
    reverse_proxy orprasoi-v2-backend:9000
}

admin.orpingtonrasoi.co.uk {
    reverse_proxy orprasoi-v2-backend:9000
}

orpingtonrasoi.co.uk {
    respond "Orpington Rasoi - Storefront coming soon!" 200
}
```

---

## Quick Commands

```bash
# SSH to server
ssh ubuntu@132.145.19.17

# Go to project
cd /home/ubuntu/docker/orprasoi-v2

# Check status
docker compose ps

# View logs
docker compose logs -f backend

# Restart backend
docker compose restart backend

# Full rebuild
docker compose down && docker compose build --no-cache && docker compose up -d
```

---

## API Testing

```bash
# Health check
curl https://api.orpingtonrasoi.co.uk/health

# Store endpoints (require publishable API key)
curl -H "x-publishable-api-key: YOUR_KEY" https://api.orpingtonrasoi.co.uk/store/products
```

---

## Next Steps

1. **Create Storefront** — Build Next.js storefront using MedusaJS Starter or custom
2. **Configure Stripe** — Add payment provider for checkout
3. **Add Products** — Populate store with menu items via admin panel
4. **Configure Shipping** — Set up delivery options for restaurant
