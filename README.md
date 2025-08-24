# FuerzaYNutricion

Fuerza y Nutrición project

## Development Setup

This is a Turborepo monorepo containing the Fuerza y Nutrición project and Cal.com self-hosted setup.

### Prerequisites
- Node.js ≥18.x
- PostgreSQL ≥13.x (for Cal.com)
- Yarn package manager

### Turborepo Commands
- **Install dependencies**: `yarn install`
- **Start all dev servers**: `yarn dev`
- **Build all projects**: `yarn build`
- **Run all tests**: `yarn test`
- **Lint all projects**: `yarn lint`
- **Type check all projects**: `yarn type-check`
- **Clean all builds**: `yarn clean`

### Cal.com Specific Commands
- **Start Cal.com dev**: `yarn cal:dev`
- **Build Cal.com**: `yarn cal:build`
- **Cal.com DB migrations**: `yarn cal:db-migrate`
- **Cal.com DB seed**: `yarn cal:db-seed`

### Quick Start Cal.com
```bash
# Option 1: From root with Turborepo
yarn cal:dev

# Option 2: Direct approach
cd cal.com
yarn dev
```

### Cal.com Environment Setup
1. Copy environment file: `cp cal.com/.env.example cal.com/.env`
2. Generate secrets:
   - `NEXTAUTH_SECRET`: `openssl rand -base64 32`
   - `CALENDSO_ENCRYPTION_KEY`: `openssl rand -base64 32`
3. Configure database URL in `cal.com/.env`

### Project Structure
```
FuerzaYNutricion/
├── cal.com/              # Cal.com self-hosted setup
│   ├── apps/web/         # Main web application
│   ├── apps/api/         # API server
│   ├── packages/prisma/  # Database schema
│   └── .env              # Environment config
├── turbo.json            # Turborepo configuration
├── package.json          # Root workspace config
└── README.md             # This file
```

### Production Deployment
1. Set up PostgreSQL database
2. Configure environment variables in `cal.com/.env`
3. Run migrations: `yarn cal:db-migrate`
4. Build and start: `yarn build && yarn start`

### Repository
- Cal.com original: https://github.com/calcom/cal.com
- Local Cal.com setup: `/cal.com/`
