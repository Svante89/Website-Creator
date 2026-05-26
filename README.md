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

## Getting Started

1. Clone this repo
2. Open the folder in Claude Code
3. Install the plugins above
4. Ask Claude to build a website — it will handle scaffolding, design, and deployment

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
