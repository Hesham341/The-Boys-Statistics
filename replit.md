# The Boys Statistics | Replit workspace notes

This repository contains a planned Dota League Tracker. **Current status:** work in progress. The frontend homepage is a Replit building placeholder, so this is not yet a completed statistics application.

For the source-of-truth overview, see [README.md](README.md).

## Run and check

Use Node.js 24 and pnpm from the repository root.

- `pnpm install --frozen-lockfile`: install workspace dependencies
- `pnpm --filter @workspace/dota-league dev`: run the current frontend
- `pnpm --filter @workspace/api-server run dev`: start the Express API (configured for port 5000 in the original Replit setup)
- `pnpm run typecheck`: type-check shared and workspace code
- `pnpm run build`: run checks and build the packages
- `pnpm --filter @workspace/api-spec run codegen`: regenerate API client/types when contracts change

## Workspace map

- `artifacts/dota-league/`: frontend
- `artifacts/api-server/`: backend and health route
- `artifacts/mockup-sandbox/`: mockup preview support
- `lib/`: shared packages
- `scripts/`: workspace utilities

## Safe development notes

- The workspace references `DATABASE_URL` for PostgreSQL operations. Configure it locally and never commit secrets.
- Never run `pnpm --filter @workspace/db run push` against a real database without verifying the destination and migration.
- Placeholder content or a successful build alone does not mean the planned statistics features are implemented or that a production site exists.
- Document confirmed data providers, computed statistics and live hosting only once they are implemented and verified.
