# picoploy

> Drop a folder, get a URL.

picoploy is a tiny, self-hostable deployment platform. Drag and drop a static site folder in your browser and get a shareable URL in seconds — like a minimal Netlify Drop.

It starts as a simple static site host and grows step by step into a mini PaaS (builds from source, container apps on ECS / Kubernetes).

> **Status:** Planning. Nothing to run yet.

## Concept

- **Drop & share** — drop a folder (`index.html`, CSS, images...) and get a temporary URL to share with your team.
- **Short-lived by default** — anonymous drops expire after 1 hour (configurable).
- **Safe by design** — user sites are served from a separate domain, with upload limits and abuse controls.

## Roadmap

| Phase | Scope |
|---|---|
| 0 | Repository, plan, architecture decision records |
| 1 | MVP (local): passphrase-gated folder drop, URL issuance, auto-expiry |
| 2 | Deploy to AWS (limited access): S3, CloudFront, Route 53, IaC, CI/CD |
| 3 | Public launch readiness: separate user-content domain, rate limiting, WAF, abuse reporting |
| 4 | Accounts: GitHub login, claiming drops, atomic deploys & rollback |
| 5 | Zip upload & builds from source (queue + workers) |
| 6 | Server apps in containers (ECS, Kubernetes) for trusted users |

## Tech stack

- **Frontend:** Vite + React (SPA)
- **API:** Hono on Node.js
- **Database:** PostgreSQL + Drizzle ORM
- **Monorepo:** TypeScript, pnpm workspaces
- **Local dev:** Docker Compose (PostgreSQL, Redis, MinIO)

## Docs

Design docs are written in Japanese.

- [Plan](docs/PLAN.md)
- [Architecture Decision Records](docs/adr/)

## License

[MIT](LICENSE)
