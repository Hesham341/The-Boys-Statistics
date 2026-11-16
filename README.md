# The Boys Statistics

Early-stage **Dota League Tracker** project built as a Replit pnpm/TypeScript workspace.

> **Project status:** Work in progress. The current `artifacts/dota-league/src/App.tsx` home screen is still a “Replit Agent is building...” placeholder. The repository does **not** yet demonstrate a finished statistics dashboard. No production URL is verified in this repository.

## Repository map

| Path | Purpose |
| --- | --- |
| `artifacts/dota-league/` | React/Vite frontend for the planned Dota League Tracker |
| `artifacts/api-server/` | Express API server; currently exposes a health route |
| `artifacts/mockup-sandbox/` | Replit UI/mockup preview tooling |
| `lib/` | Shared workspace libraries |
| `scripts/` | Workspace development utilities |
| `replit.md` | Replit-specific development notes |

## Stack

- **Frontend:** React, TypeScript, Vite, Tailwind CSS, Radix UI and TanStack Query
- **Backend:** Express / TypeScript
- **Workspace:** pnpm monorepo
- **Intended persistence:** PostgreSQL with Drizzle tooling documented by the Replit workspace; a working statistics database integration is **not verified** here

## Local development

Use Node.js **24** and **pnpm**, as documented in `replit.md` and the workspace. Install dependencies from the repository root:

```sh
pnpm install --frozen-lockfile
pnpm --filter @workspace/dota-league dev
```

Quality checks from the root:

```sh
pnpm run typecheck
pnpm run build
```

To run the API service separately, use `pnpm --filter @workspace/api-server run dev` (Replit notes specify port 5000). A local backend setup may require `DATABASE_URL`, but do not commit credentials. Use `pnpm --filter @workspace/db run push` **only** against a development database after verifying its target.

## Scope and status notes

This is source code for a personal Dota-related concept, not a verified live league-results service. Any future statistic calculations, data-source integrations, and deployment links should be documented when implemented and tested. Do not publish user or game-account secrets to GitHub.
