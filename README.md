# Website Creator

A Claude Code workspace for building production-grade websites with Next.js, Tailwind CSS, and Vercel.

## Requirements

- [Claude Code](https://claude.ai/code) (CLI or VS Code extension)

## Plugin Setup

Install the following plugins in Claude Code before using this workspace:

```
/install frontend-design@claude-code-plugins
/install vercel@claude-plugins-official
```

To install: open Claude Code, type the command above, and press Enter.

## Getting Started (for viewers / new users)

You are looking at someone else's repo. Follow these steps to get your own copy that you fully control.

### Step 1 — Fork the repo

Click **Fork** (top-right on GitHub). This creates a copy under your own GitHub account.

### Step 2 — Authenticate with GitHub on your machine

Install the GitHub CLI:

```bash
brew install gh        # macOS
# Windows: winget install GitHub.CLI
```

Log in to **your** GitHub account:

```bash
gh auth login
```

Follow the prompts: GitHub.com → HTTPS → authenticate via browser.

### Step 3 — Clone your fork

```bash
gh repo clone <your-github-username>/Website-Creator
```

This clones **your fork**, not the original. You own it — you can push freely.

### Step 4 — Open in Claude Code and install plugins

```bash
cd Website-Creator
code .        # or open Claude Code and point it at the folder
```

Then in Claude Code:

```
/install frontend-design@claude-code-plugins
/install vercel@claude-plugins-official
```

### Step 5 — Start building

Ask Claude to build a website. It handles scaffolding, design, and deployment.

---

## Daily workflow (once set up)

```bash
git add CLAUDE.md README.md    # never add .env files or secrets
git commit -m "your message"
git push                       # pushes to your fork, not the original
```

> `projects/` is gitignored in this workspace — each website you build under `projects/` gets its own separate git repo and Vercel deployment.

## Structure

```
Website Creator/
├── CLAUDE.md       ← instructions for Claude
├── README.md       ← this file
└── projects/       ← your websites (not tracked in git)
    └── my-site/
```

Each website under `projects/` is its own independent project with its own git repo.

## Tech Stack

- **Framework**: Next.js (App Router)
- **Language**: TypeScript
- **Styling**: Tailwind CSS v4
- **Components**: shadcn/ui
- **Deployment**: Vercel
