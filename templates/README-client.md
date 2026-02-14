# [Client Name] — [Project Title]

> One-line description of what this project is and who it is for.

---

## Project Info

| Key | Value |
|---|---|
| **Client** | Client Name |
| **Status** | 🟢 Active / 🟡 Maintenance / ⚫ Complete |
| **Project Manager** | @github-handle |
| **Lead Developer** | @github-handle |
| **Designer** | @github-handle |
| **Staging URL** | https://staging.clientdomain.com |
| **Production URL** | https://clientdomain.com |
| **Start Date** | YYYY-MM-DD |
| **Contract** | Notion / Drive link |

---

## Tech Stack

| Layer | Technology |
|---|---|
| **Framework** | Next.js 14 |
| **Styling** | Tailwind CSS |
| **Backend** | Node.js / FastAPI / etc. |
| **Database** | PostgreSQL / MongoDB / etc. |
| **Auth** | NextAuth / Clerk / etc. |
| **Hosting** | Vercel / AWS / Railway |
| **CMS** | Sanity / Contentful / none |

---

## Getting Started

### Prerequisites

- Node.js 20+
- npm 10+
- Access to the project's environment secrets (ask @owner-handle)

### Setup

```bash
# Clone the repository
git clone git@github.com:jumpspaces/client-name.git
cd client-name

# Install dependencies
npm install

# Copy environment template and fill in your local values
cp .env.example .env.local

# Run the development server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## Environment Variables

Copy `.env.example` to `.env.local` and fill in all values.
Request production/staging secrets from @owner-handle via 1Password / team Slack.

See `.env.example` for all required variables and descriptions.

---

## Available Scripts

```bash
npm run dev          # Start development server
npm run build        # Build for production
npm run start        # Start production server
npm run lint         # Run ESLint
npm run type-check   # TypeScript type checking
npm run test         # Run unit tests
npm run test:e2e     # Run end-to-end tests
```

---

## Branch Strategy

| Branch | Purpose |
|---|---|
| `main` | Production — protected, deploy on merge |
| `staging` | Pre-production testing |
| `dev` | Active development integration |
| `feature/*` | New features, branch from `dev` |
| `fix/*` | Bug fixes, branch from `dev` |

See [CONTRIBUTING.md](https://github.com/jumpspaces/.github/blob/main/CONTRIBUTING.md) for the full workflow.

---

## Deployment

| Environment | Trigger | URL |
|---|---|---|
| **Staging** | Push to `staging` | https://staging.clientdomain.com |
| **Production** | Merge PR to `main` | https://clientdomain.com |

CI/CD is configured via GitHub Actions (see `.github/workflows/`).

---

## Project Structure

```
/
├── .github/
│   └── workflows/          # CI/CD pipelines
├── src/
│   ├── app/                # Next.js app router
│   ├── components/         # Reusable UI components
│   └── lib/                # Utilities, helpers, API clients
├── public/                 # Static assets
├── tests/                  # Unit & integration tests
├── docs/                   # Project documentation
├── .env.example            # Environment variable template
└── README.md
```

---

## Key Contacts

| Role | Name | Contact |
|---|---|---|
| JUMP SPACES PM | Name | @github-handle / Slack |
| JUMP SPACES Dev Lead | Name | @github-handle / Slack |
| Client Contact | Name | email@client.com |

**Internal Slack channel:** `#project-clientname`

---

## Changelog

See [CHANGELOG.md](./CHANGELOG.md) for a history of notable changes.
