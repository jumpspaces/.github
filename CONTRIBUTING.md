# Contributing to JUMP SPACES

Thank you for being part of the JUMP SPACES team. This document outlines how we work together across all repositories — client projects, internal SaaS products, and open-source tools.

---

## Table of Contents

- [Getting Started](#getting-started)
- [Branching Strategy](#branching-strategy)
- [Commit Messages](#commit-messages)
- [Pull Requests](#pull-requests)
- [Code Reviews](#code-reviews)
- [Code Standards](#code-standards)
- [Environment Variables](#environment-variables)
- [Testing](#testing)

---

## Getting Started

1. Make sure you have been added to the correct GitHub Team by an Owner.
2. Clone the repository:
   ```bash
   git clone git@github.com:jumpspaces/<repo-name>.git
   cd <repo-name>
   ```
3. Copy the environment template and fill in your local values:
   ```bash
   cp .env.example .env.local
   ```
4. Install dependencies and run locally:
   ```bash
   npm install
   npm run dev
   ```
5. Read the project's own `README.md` for any project-specific setup steps.

---

## Branching Strategy

We use a simplified GitHub Flow with the following branches:

| Branch | Purpose | Protected |
|---|---|---|
| `main` | Production — always deployable | ✅ Yes |
| `staging` | Pre-production testing | ✅ Yes |
| `dev` | Active integration of completed features | ✅ Yes |
| `feature/xxx` | New features — branch from `dev` | ❌ No |
| `fix/xxx` | Bug fixes — branch from `dev` (or `main` for hotfixes) | ❌ No |
| `release/x.x.x` | Release prep — branch from `dev` | ❌ No |

### Rules

- **Never push directly to `main` or `staging`.** Always open a PR.
- Branch names must use the correct prefix and be lowercase hyphen-separated.
- Delete your branch after it is merged.

```bash
# Creating a new feature branch
git checkout dev
git pull origin dev
git checkout -b feature/user-authentication

# Creating a bug fix branch
git checkout -b fix/login-redirect-loop
```

---

## Commit Messages

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification.

```
<type>(<scope>): <short description>

[optional body]

[optional footer — e.g. Closes #42]
```

### Types

| Type | When to Use |
|---|---|
| `feat` | A new feature |
| `fix` | A bug fix |
| `docs` | Documentation changes only |
| `style` | Formatting — no logic change |
| `refactor` | Code restructure, no feature or fix |
| `test` | Adding or updating tests |
| `chore` | Build, tooling, dependency updates |
| `ci` | CI/CD configuration changes |

### Examples

```bash
git commit -m "feat(auth): add Google OAuth login"
git commit -m "fix(api): return 404 instead of 500 for missing user"
git commit -m "docs(readme): update local dev setup instructions"
git commit -m "chore(deps): upgrade next.js to 14.2"
```

---

## Pull Requests

- All changes to `dev`, `staging`, and `main` must go through a PR.
- Use the PR template — it auto-fills when you open a PR.
- Link the relevant issue in the PR description using `Closes #<issue-number>`.
- Assign at least one reviewer before marking as Ready for Review.
- PRs should be focused — one feature or fix per PR.
- Keep PRs small (under 400 lines changed) whenever possible.

### PR Checklist

Before requesting review, confirm:

- [ ] Self-reviewed the diff
- [ ] No `console.log`, debug code, or commented-out blocks left in
- [ ] Tests added or updated
- [ ] `.env.example` updated if new environment variables were added
- [ ] `CHANGELOG.md` updated (for SaaS products)
- [ ] No merge conflicts with target branch

---

## Code Reviews

### As a Reviewer

- Review within **one business day** of being assigned.
- Be specific and constructive — suggest alternatives, not just point out problems.
- Approve when the code is production-ready, even if minor improvements are possible.
- Use the following comment prefixes for clarity:
  - `nit:` — Minor style preference, not blocking
  - `suggestion:` — Non-blocking improvement idea
  - `question:` — Seeking understanding, not blocking
  - `blocker:` — Must be resolved before merge

### As an Author

- Respond to all comments before requesting re-review.
- Don't dismiss reviews without discussion.
- If you disagree with feedback, explain your reasoning.

---

## Code Standards

### General

- Write code for the next person who reads it, not just to make it work.
- Prefer explicit over implicit — clear variable names, no magic numbers.
- Keep functions small and focused on one responsibility.
- Delete dead code — don't comment it out.

### JavaScript / TypeScript

- Use TypeScript for all new projects.
- Use `const` by default; `let` only when reassignment is necessary.
- No `any` types — use `unknown` or proper typing.
- Follow the project's ESLint configuration.

### Python

- Follow [PEP 8](https://pep8.org/).
- Use type hints for all function signatures.
- Use `ruff` or `flake8` for linting.

### CSS / Styling

- Use Tailwind CSS utility classes for new projects.
- Avoid inline styles unless dynamically computed.
- Keep class names meaningful when using CSS modules.

---

## Environment Variables

- **Never commit `.env` files.** They are in `.gitignore` for a reason.
- Always update `.env.example` when adding a new variable.
- Use clear, descriptive names in `UPPER_SNAKE_CASE`.
- Add a comment above any non-obvious variable in `.env.example`:

```bash
# Stripe secret key — get from dashboard.stripe.com
STRIPE_SECRET_KEY=

# Feature flag: set to "true" to enable new onboarding flow
FEATURE_NEW_ONBOARDING=false
```

---

## Testing

- Write tests for all new features and bug fixes.
- Tests live in the `tests/` or `__tests__/` directory, mirroring `src/`.
- Aim for meaningful coverage — test behaviour, not implementation details.
- Run the full test suite before opening a PR:

```bash
npm run test          # unit tests
npm run test:e2e      # end-to-end tests (if applicable)
npm run lint          # linting
```

---

## Questions?

Reach out in the team Slack or open a GitHub Discussion in the relevant repository.
