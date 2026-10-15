# Rahul Sain — Full-Stack Engineer

**Next.js · React · Node.js / Bun · TypeScript · Postgres / MongoDB · System Design**

I build production-grade SaaS — AI-powered apps, developer tools, and full-stack systems with clean architecture, type-safety, and real-world trade-offs.

Portfolio: **https://rahulxcode.vercel.app/** · Email: **sainrahul374@gmail.com** · LinkedIn: **https://www.linkedin.com/in/rahulxcode/** · X: **https://x.com/RahulSain714**

---

## Selected Work

### 1. RoastMyTube — AI YouTube Roast Engine
**Live:** https://roastmytube.vercel.app · **Code:** https://github.com/Anos714/RoastMyTube

Connect YouTube, get roasted by AI. Brain-Rot Score, red-flag detector, shareable roast cards in English + Hinglish.

Engineering notes:
- Google OAuth with `youtube.readonly` scope, offline tokens + auto-refresh
- 4 parallel YouTube Data API calls — 5 quota units / roast (~2,000 roasts/day on free tier)
- 3-level LLM fallback: Groq `gpt-oss-120b` → `20b` → Gemini Flash, Zod-validated JSON output
- Neon Postgres + Drizzle ORM for roast history, privacy-first (read-only, one-click wipe)
- Share Studio: Post / Square / Story cards in PNG, JPG, WebP, AVIF

Stack: Next.js 16, React 19, TypeScript, Bun, Better Auth, Neon, Drizzle, Groq, Gemini, Tailwind v4

---

### 2. waku — Profile Page + Identity Card Studio
**Live:** https://wakucards.vercel.app · **Code:** https://github.com/Anos714/waku

Local-first studio that turns name + role + links into a themeable public profile page and matching downloadable identity card with QR + PNG export.

Engineering notes:
- One renderer (`ProfileView`) for both editor preview and public `/p/[slug]` — no drift
- Themes as CSS tokens: 10 themes × 8 fonts × 16 accents × 8 backgrounds, zero content rewrites
- Local-first drafts in `localStorage` (debounced), claimed on first sign-in; server owns slugs
- AI bio writer (Groq-first, Gemini fallback) constrained to facts-only prompts, resume PDF import
- Signed Cloudinary uploads, graceful degradation when DB/OAuth/AI keys are missing, Vitest suite

Stack: Next.js 16, TypeScript, Tailwind v4, Better Auth, Neon, Drizzle, Groq, Gemini, Cloudinary

---

### 3. stackit — Opinionated Full-Stack Scaffolder
**Live Docs:** https://stackitcli.vercel.app · **Code:** https://github.com/Anos714/stackit · **npm:** `bunx create-stackit-app@latest`

`create-next-app` for the whole stack — MERN, PERN, Hono + Postgres, Go + Fiber monorepos with validation, Docker and docs in one command.

Engineering notes:
- Bun + TypeScript CLI with file-map driven scaffolding per stack
- Built-in validation (Zod), Dockerfiles, README/docs generation out of the box
- 13 unit tests (semver, registry, scaffold maps) + `tsc --noEmit` clean
- Docs + landing site in Next.js 16 + Tailwind v4

Stack: TypeScript, Bun, Node.js, React, Hono, Go + Fiber, Postgres, MongoDB, Docker

---

### 4. CodeVault — Searchable Snippet Vault
**Live:** https://codevault-self.vercel.app · **Code:** https://github.com/Anos714/CodeVault

Centralized vault for reusable code — save, tag, search with syntax highlighting. Stop rewriting the same logic.

Engineering notes:
- Next.js server actions + DAL, every read/write owner-scoped in SQL (`WHERE author_id = ?`)
- Zod as single mutation contract, atomic counters (`SET favorites = favorites + 1`)
- Unlisted share links (`/s/[token]`, 32-hex, expiry + revocation), chrome-free `/embed/[id]` + OG cards
- Monaco composer with live preview, 19 languages, flat tags, URL-driven filters (`?q&tag&visibility&sort`)
- Better Auth (Google/GitHub + demo account), lazy Neon client — build passes with no DB

Stack: Next.js 16, React 19, TypeScript, Tailwind v4, Neon, Drizzle, Better Auth, Monaco, Upstash Redis

---

### 5. SmartBillr — Manual + AI Invoice Platform
**Code:** https://github.com/Anos714/SmartBillr *(live deployment in progress)*

Invoice generation that combines full manual control with AI-assisted content — descriptions, pricing, structure.

Engineering notes:
- JWT + Google OAuth, secure cookie sessions, Zod validation on every input
- MongoDB (Mongoose) for persistence, Redis for caching/performance, Nodemailer for email
- React 19 + Vite frontend, React Query for server state, Zustand for client state
- Clean invoice UI designed to be export-ready

Stack: React 19, Vite, TypeScript, Express 5, MongoDB, Redis, JWT, Zod, Tailwind CSS

---

## Engineering Focus

- **Backend-first thinking:** API design, auth (JWT / OAuth / RBAC), validation with Zod, rate limiting
- **Data:** Postgres (Neon + Drizzle), MongoDB, Redis — indexing, atomic updates, cache strategy
- **Architecture:** monorepo scaffolding, DAL pattern, server actions, background jobs (BullMQ), edge deployment
- **Quality:** TypeScript strict, ESLint, Vitest / Jest, manual API testing, regression fixing
- **DevOps:** Docker, CI/CD, Vercel / Render / Railway, zero-downtime habits

## Tech Stack

**Languages:** TypeScript, JavaScript, SQL, Go, Java
**Frontend:** React, Next.js, Tailwind CSS, TanStack Query, Zustand, Redux Toolkit, React Hook Form, Framer Motion, ShadCN/UI
**Backend:** Node.js, Express.js, Hono, Elysia.js, Bun
**Database / Cache:** PostgreSQL (Neon), MongoDB, MySQL, Redis, Drizzle ORM, Prisma
**Testing:** Jest, Vitest, Supertest
**Tools / DevOps:** Git, GitHub, Docker, Vercel, Render, Railway, Postman, Bruno, Linux, VS Code

---

## Currently

- Building AI SaaS with structured LLM output + fallback chains
- Learning system design + advanced backend (queues, caching, microservices)
- Practicing DSA consistently

---

## Contact

- Portfolio: https://rahulxcode.vercel.app/
- Email: sainrahul374@gmail.com
- LinkedIn: https://www.linkedin.com/in/rahulxcode/
- X: https://x.com/RahulSain714
- GitHub: https://github.com/Anos714

> I don't optimize for "more projects". I optimize for understanding systems deeply enough to build them better.
