# founder-os

**How serious AI-native founders keep context from falling apart.**

An opinionated operating system for AI-native work: a single git repo of versioned markdown that every AI surface (Claude, Codex, ChatGPT, Grok, whatever comes next) can read from and write back to. Not another PKM or "second brain" — the point isn't storing knowledge, it's *maintaining* it: version-controlled context, digest routing, compiled context packs, public/private boundaries, and agent coordination, in files no vendor owns.

**This copy is populated with a fictional founder** — Jordan Rivers of **Riverline Advisory, LLC**, an AI-native project-management consultancy — so you can see the system working, not just its skeleton. To adopt it: fork, find-and-replace Jordan/Riverline, then replace the contents of `01-foundation/` with your own (start with `about.md` — the fill plan is written inside each file).

## Why this exists

Context scattered across chat histories, Notion, and notes decays — and every new AI session starts from zero. Centralizing who you are, what you believe, and where each bet stands in versioned markdown makes every AI workflow smarter, every decision traceable, and no vendor your landlord. **The interchange format is files, not any model's memory** — that's the whole trick, and it's why the system is model-agnostic.

## The architecture

```
                         you, everywhere
        ┌──────────┬──────────┬──────────┬──────────┐
        Claude Code   Codex    ChatGPT     Grok
        (/digest)   (AGENTS.md) (paste lane: tagged session digest)
             │          │          │          │
             ▼          ▼          ▼          ▼
        ┌─────────────────────────────────────────┐
        │  00-inbox/  +  project SYNC-DIGEST.md   │   capture
        └────────────────────┬────────────────────┘
                     /digest routes by tag
                             ▼
   01-foundation/ · 02-projects/ · 03-studio/ · 04-decisions/   knowledge
                             │
                   /digest compiles packs
                             ▼
        ┌─────────────────────────────────────────┐
        │ context-packs/  founder-pack, brand-pack │   compiled exports
        └────────────────────┬────────────────────┘
                             ▼
      pasted into ChatGPT/Grok custom instructions;
      loaded by agents (.agents/roles/) — never the raw repo
```

**In:** every AI session ends by filing what happened — Claude and Codex write digests directly (see `CLAUDE.md` / `AGENTS.md`); chat-only models emit a tagged digest block you paste into `00-inbox/`.
**Routing:** `/digest` (`.claude/commands/digest.md`) parses capture and routes each line by tag to its one destination.
**Out:** `/digest` recompiles `context-packs/` — one-page distillations you paste into chat models and hand to agents. The repo is source code; packs are the compiled binaries.

## The tag grammar

Six tags, one per routing destination. Every tag is a promise that a route exists — don't add a seventh until it has a home.

| Tag | Routes to |
|---|---|
| `#belief` | `01-foundation/beliefs.md` (raw intake → distilled into `principles.md` over time) |
| `#canon` | `01-foundation/canon.md` (taste, not conviction) |
| `#decision` | `04-decisions/YYYY-MM-DD-<slug>.md` |
| `#idea` | `02-projects/ideas.md` (parked; the Connections gate decides if it ever becomes a card) |
| `#todo(project)` | that project's card, tagged Now/Next/Later |
| `#content` | `01-foundation/../content-backlog.md` — or wherever your content pipeline lives |

## The rules that keep it lean

1. **README is mandatory; every other file is created the day it first has real content.** Pre-scaffolded empty files rot, and stubs poison AI context.
2. **No card without Connections.** A new project earns a folder in `02-projects/` only when its `product-vision.md` Connections section exists — which principle it expresses, what it lets the brand say, which other bets it feeds. That one paragraph is the alignment gate (`01-foundation/prioritization.md` is the scoring rubric upstream of it).
3. **Raw exports never enter git.** ChatGPT exports and conversation dumps go in `sources/` (gitignored), get distilled once into `01-foundation/` with `source:` provenance, and are never read again. Process the ore; commit the metal.
4. **Exposed surfaces load packs, never the repo.** Anything other people can prompt (a Discord bot, a public agent) reads `context-packs/` extracts only and writes to a queue a human reviews. Instructions are bypassable; credentials aren't.
5. **The lean test:** every file must be loaded by something — a `/digest` route, a pack, a role manifest, or a template. A file with no consumer doesn't get created. That's the difference between a second brain and a second filing cabinet.

## Repo conventions

- Every folder has a README answering: What this is / Why it matters / Current status / Active priorities / Open questions / Links.
- Every markdown file starts with YAML frontmatter: `project`, `status` (`stub`·`draft`·`active`·`paused`·`archived`), `priority`, `updated`, `tags`.
- Context commits stay separate from code commits; sync commits use `context-sync(<source>): <summary>`.

## Quickstart

1. Fork. `grep -ri "jordan\|riverline" --include="*.md" .` and replace with yourself.
2. Rewrite `01-foundation/` — each file explains how to fill itself; do `about.md`, `principles.md`, and `brand-voice.md` first.
3. Copy `templates/claude-md-snippet.md` / `templates/agents-md-snippet.md` into each project code repo so Claude/Codex sessions end with a digest.
4. Add the block in `templates/chatgpt-session-digest.md` to your ChatGPT custom instructions; paste its output into `00-inbox/` after long sessions.
5. Run `/digest` at the end of OS work sessions; paste the refreshed `context-packs/founder-pack.md` into your chat models when it drifts.

MIT licensed. Built from the pattern behind a working founder OS; the fictional data is yours to delete.
