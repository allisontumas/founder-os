# founder-os — Codex/agent contract

Same contract as CLAUDE.md, restated for any agent runtime that reads AGENTS.md:

1. This repo is source-of-truth founder context. Read `01-foundation/README.md` first; load `context-packs/` for a compressed view.
2. End every work session by filing what happened: durable signals into `00-inbox/` as a dated markdown file using the tag grammar in README.md (`#belief #canon #decision #idea #todo(project) #content`). The `/digest` pass (run in Claude Code, or by hand) routes them.
3. Do not restructure folders, edit `01-foundation/` convictions, or touch `sources/`.
4. Commit context changes separately: `context-sync(<agent>): <summary>`.

In project code repos, use `templates/agents-md-snippet.md` — sessions there end by appending to that repo's SYNC-DIGEST.md.
