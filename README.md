# 🕹️ RetroWorks HR

> Production-grade HRMS/HRIS with Vintage Gaming UI  
> **HIRE → RETIRE + L&D + AI HR Copilot**

---

## Stack

| Layer | Technology |
|-------|-----------|
| Web | Next.js 14 (App Router) + TypeScript + TailwindCSS + Radix UI |
| API | NestJS + Prisma ORM + PostgreSQL + REST/OpenAPI |
| Mobile | Expo React Native (Phase 2) |
| AI | pgvector + OpenAI embeddings + RAG |
| Queue | BullMQ + Upstash Redis |
| Auth | JWT + Magic Links + TOTP MFA + Keycloak OIDC |
| Infra | Docker + EC2 t2.micro + RDS + S3 + CloudFront + SES |
| CI/CD | GitHub Actions |

---

## Quick Start

### Prerequisites
- Node.js ≥ 20
- pnpm ≥ 9
- Docker + Docker Compose

### Development

```bash
# Clone and install
git clone https://github.com/your-org/retroworks-hr
cd retroworks-hr
pnpm install

# Environment setup
cp .env.example .env.local
# Edit .env.local with your values

# Start all services
docker-compose up -d

# Run migrations + seed
pnpm --filter @retroworks/api db:migrate
pnpm --filter @retroworks/api db:seed

# Start development servers
pnpm dev
```

**Access:**
- Web UI: http://localhost:3000
- API: http://localhost:3001
- API Docs: http://localhost:3001/api/docs
- Keycloak: http://localhost:8080 (admin/admin)
- MinIO Console: http://localhost:9001 (minioadmin/minioadmin)
- MailHog: http://localhost:8025

### Demo Login
```
Email:    admin@acme.retroworks.local
Password: Admin@123!
```

---

## Project Structure

```
retroworks-hr/
├── apps/
│   ├── web/              # Next.js frontend
│   ├── api/              # NestJS backend
│   │   └── prisma/       # Schema + migrations + seed
│   └── mobile/           # Expo React Native (Phase 2)
├── packages/
│   ├── ui/               # Shared Radix + Tailwind components
│   ├── types/            # Shared TypeScript types
│   └── config/           # Tailwind config + design tokens
├── ai/                   # RAG service (Phase 4)
├── infra/
│   └── docker/           # Dockerfiles + compose configs
├── .github/
│   └── workflows/        # CI/CD
└── docs/
    └── adr.md            # Architecture Decision Records
```

---

## Modules

| Module | Status | Phase |
|--------|--------|-------|
| Core HR | 🚧 In Progress | 1 |
| Auth (JWT + Magic Link + TOTP) | 🚧 In Progress | 1 |
| RBAC/ABAC | 🚧 In Progress | 1 |
| Form Builder | 🚧 In Progress | 1 |
| Workflow Engine | 🚧 In Progress | 1 |
| DataOps Console | 🚧 In Progress | 1 |
| ATS | 📋 Planned | 2 |
| Onboarding | 📋 Planned | 2 |
| Leave Management | 📋 Planned | 2 |
| Attendance | 📋 Planned | 2 |
| Payroll (India) | 📋 Planned | 3 |
| Performance/OKRs | 📋 Planned | 3 |
| L&D/LMS | 📋 Planned | 3 |
| Helpdesk | 📋 Planned | 3 |
| AI HR Copilot | 📋 Planned | 4 |
| Reporting | 📋 Planned | 4 |

---

## Delivery Phases

- **PHASE 0** — Scaffold ✅ (current)
- **PHASE 1** — Core Platform (Auth + RBAC + Form/Workflow Builder + Employee CRUD)
- **PHASE 2** — HR Modules (ATS + Onboarding + Leave + Attendance)
- **PHASE 3** — Payroll + L&D (India PF/ESI/PT/TDS + Benefits + Performance)
- **PHASE 4** — AI + Hardening (RAG + Observability + EC2 Deploy)

---

## India Payroll Compliance

- ✅ PF (Provident Fund) — 12% employee + 12% employer
- ✅ ESI (Employee State Insurance) — 0.75% + 3.25%
- ✅ PT (Professional Tax) — state-wise slab configuration
- ✅ TDS (Tax Deducted at Source) — Old/New tax regime
- ✅ LWF (Labour Welfare Fund) — state-wise
- ✅ Gratuity — 5-year eligibility, 15/26 formula

---

## Security

- JWT + Refresh token rotation
- Magic link authentication
- TOTP MFA
- OIDC SSO (Keycloak)
- Row-level tenancy enforcement
- PII encrypted at rest (AES-256-GCM / AWS KMS)
- Immutable audit logs
- DSR export/delete workflow
- Consent tracking
- Biometric feature flag (OFF by default)

---

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md)

## License

Proprietary — RetroWorks HR
