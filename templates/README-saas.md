# [Product Name]

> One-line product tagline — what it does and who it is for.

[![CI](https://github.com/jumpspaces/saas-product/actions/workflows/ci.yml/badge.svg)](https://github.com/jumpspaces/saas-product/actions/workflows/ci.yml)
[![License](https://img.shields.io/badge/license-private-red)](./LICENSE)

---

## Overview

Describe the product in 2–3 sentences. What problem does it solve? Who are the target users? What makes it different?

---

## Status

| Environment | URL | Status |
|---|---|---|
| **Production** | https://product.jumpspaces.com | 🟢 Live |
| **Staging** | https://staging.product.jumpspaces.com | 🟢 Active |
| **Docs** | https://docs.product.jumpspaces.com | 🟢 Live |

---

## Architecture

```
┌────────────────────────────────┐
│  Frontend (Next.js / React)    │
│  Hosted on Vercel              │
└───────────────┬────────────────┘
                │ HTTPS / REST or GraphQL
┌───────────────▼────────────────┐
│  Backend API (Node / FastAPI)  │
│  Hosted on Railway / AWS       │
└───────┬───────────────┬────────┘
        │               │
┌───────▼──────┐ ┌──────▼───────┐
│  PostgreSQL  │ │    Redis      │
│  (primary)   │ │  (cache/jobs) │
└──────────────┘ └──────────────┘
```

| Layer | Technology |
|---|---|
| **Frontend** | Next.js 14, Tailwind CSS |
| **Backend** | Node.js / FastAPI |
| **Database** | PostgreSQL |
| **Cache** | Redis |
| **Auth** | Clerk / NextAuth / custom JWT |
| **Email** | Resend / SendGrid |
| **Payments** | Stripe |
| **Storage** | AWS S3 / Cloudflare R2 |
| **Monitoring** | Sentry, Posthog |

---

## Getting Started

### Prerequisites

- Node.js 20+
- Docker & Docker Compose (for local DB + Redis)
- Access to environment secrets (ask @owner-handle)

### Local Development

```bash
# Clone the repo
git clone git@github.com:jumpspaces/saas-product.git
cd saas-product

# Copy environment template
cp .env.example .env

# Start local services (DB, Redis, etc.)
docker-compose up -d

# Install dependencies
npm install

# Run database migrations
npm run db:migrate

# Seed development data (optional)
npm run db:seed

# Start the dev server
npm run dev
```

---

## Environment Variables

See `.env.example` for all required variables with descriptions.
Production secrets are stored in **[1Password / GitHub Secrets]** — request access from @owner-handle.

---

## Available Scripts

```bash
npm run dev            # Start development server
npm run build          # Build for production
npm run start          # Start production server
npm run lint           # ESLint
npm run type-check     # TypeScript check
npm run test           # Unit tests (Jest / Vitest)
npm run test:e2e       # End-to-end tests (Playwright)
npm run db:migrate     # Run pending DB migrations
npm run db:rollback    # Roll back last migration
npm run db:seed        # Seed development data
```

---

## Branch Strategy

| Branch | Purpose | Deploys To |
|---|---|---|
| `main` | Production | production |
| `staging` | Pre-production | staging |
| `dev` | Integration | dev server |
| `feature/*` | New features | — |
| `fix/*` | Bug fixes | — |
| `release/x.x` | Release prep | — |

---

## Deployment

| Environment | Trigger | Notes |
|---|---|---|
| **Staging** | Push to `staging` | Auto via GitHub Actions |
| **Production** | Merge PR to `main` | Auto via GitHub Actions |

Manual deploy (if needed):
```bash
# Example for Vercel
npx vercel --prod
```

---

## Project Structure

```
/
├── .github/
│   └── workflows/          # CI/CD pipelines
├── src/
│   ├── app/                # Next.js app router or Express routes
│   ├── components/         # UI components
│   ├── lib/                # Utilities, DB client, helpers
│   ├── services/           # Business logic layer
│   └── types/              # TypeScript types and interfaces
├── tests/
│   ├── unit/               # Unit tests
│   └── e2e/                # End-to-end tests
├── prisma/ (or migrations/) # Database schema and migrations
├── docs/                   # Architecture docs, ADRs
├── docker-compose.yml
├── .env.example
└── README.md
```

---

## Roadmap

Track planned features and upcoming releases on the [GitHub Project Board](https://github.com/orgs/jumpspaces/projects).

---

## Contributing

See [CONTRIBUTING.md](https://github.com/jumpspaces/.github/blob/main/CONTRIBUTING.md) for branch naming, PR process, commit conventions, and code standards.

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for release history.

---

## Team

| Role | GitHub |
|---|---|
| Product Owner | @handle |
| Lead Developer | @handle |
| Designer | @handle |

**Internal Slack:** `#product-name`
