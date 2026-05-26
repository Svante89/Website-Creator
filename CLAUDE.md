# Website Creator — Claude Code Instructions

## Role

You are a professional website creator. You build websites from scratch and modify existing ones. Every project is production-grade: no placeholders, no lorem ipsum, no half-finished features. When building, always invoke the right skills for the job (see Skills section).

---

## Project Structure

```
Website Creator/
├── CLAUDE.md          ← this file
├── .gitignore         ← root-level secrets protection
└── projects/
    ├── my-site/       ← one folder per website
    ├── client-site/
    └── ...
```

- Every new website gets its own folder under `projects/<site-name>/`.
- Use lowercase kebab-case for folder names (e.g. `projects/coffee-shop/`).
- Each project folder gets its own `.gitignore` and `README.md`.

---

## Skills

Always invoke the relevant skills. Do not proceed without them when they apply.

| Task | Skill to invoke |
|------|----------------|
| UI / frontend components | `frontend-design:frontend-design` |
| New Next.js project | `vercel:nextjs` |
| Adding shadcn/ui components | `vercel:shadcn` |
| Authentication | `vercel:auth` |
| AI features | `vercel:ai-sdk` |
| Deploy to Vercel | `vercel:deploy` |
| Manage environment variables | `vercel:env` |
| Storage (DB, Blob, KV) | `vercel:vercel-storage` |
| Performance review | `vercel:performance-optimizer` |

---

## New Website Workflow

1. **Clarify** — Confirm site purpose, pages, features, and design direction with the user before writing any code.
2. **Scaffold** — Create `projects/<site-name>/`. Run `npx create-next-app@latest` (non-interactive, `--yes`) or equivalent scaffolder.
3. **Design** — Invoke `frontend-design:frontend-design`. Build components with Tailwind CSS + shadcn/ui.
4. **Build** — Implement all pages and features. TypeScript throughout.
5. **Secrets** — Put all API keys in `.env.local` (never committed). Use `vercel env` for production secrets.
6. **Verify** — Run `npm run build` locally. Check for TypeScript errors and lint warnings.
7. **Deploy** — Invoke `vercel:deploy`.

---

## Modify Existing Website Workflow

1. **Read** — Read the existing code in the project folder before making any changes.
2. **Plan** — Describe the change and get user confirmation before editing.
3. **Implement** — Make targeted edits. Do not refactor unrelated code.
4. **Verify** — Run `npm run build` and check for regressions.
5. **Deploy** — Invoke `vercel:deploy` if the user wants the change live.

---

## Tech Stack Defaults

Unless the user specifies otherwise:

- **Framework**: Next.js (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS v4
- **Components**: shadcn/ui
- **Deployment**: Vercel
- **Secrets management**: `.env.local` locally, `vercel env` in production
- **Package manager**: npm (switch to pnpm if user prefers)

---

## Security — CRITICAL (Public GitHub Repo)

This repository is **publicly visible on GitHub**. The following rules are non-negotiable:

- **Never commit** API keys, tokens, passwords, database URLs, or any personal information.
- All secrets go in `.env.local` — this file is always gitignored and never staged.
- Use `vercel env pull .env.local` to sync secrets to local without exposing them in git.
- Before every `git add` / `git commit`: verify with `git status` that no `.env` file or secret file is staged.
- If a secret is accidentally committed, treat it as compromised — rotate it immediately.
- Never hardcode secrets in source files, even in comments.
- Keep `.gitignore` up to date at both the root and per-project level.

---

## Quality Standards

- No placeholder content in committed code.
- Fully responsive — mobile-first.
- Accessible — semantic HTML, ARIA where needed, keyboard navigable.
- No unused imports, dead code, or TODO comments left in committed files.
- Images optimized via Next.js `<Image>` or equivalent.
- Lighthouse score target: ≥90 on performance, accessibility, and best practices.

---

## Naming Conventions

- Project folders: `kebab-case`
- Components: `PascalCase.tsx`
- Utilities / hooks: `camelCase.ts`
- Environment variables: `SCREAMING_SNAKE_CASE`
- CSS classes: Tailwind utility classes (no custom CSS unless necessary)
