# founder-os — Claude contract

This repo is the founder's context OS. Sessions here consume capture and route it; sessions in project code repos produce digests that flow here.

- **End of an OS work session:** run `/digest` (.claude/commands/digest.md) — route inbox + journal, refresh the project rollup, recompile context-packs/, commit `sync: YYYY-MM-DD digest`, then /clear.
- **Never** edit `01-foundation/` principles/beliefs on your own judgment — capture routes there; distillation is the founder's call.
- **Never** read or write `sources/` — raw exports are processed once, then dead to all models.
- Context commits stay separate from any other changes.
- Frontmatter `updated:` gets bumped on every touched file.

In project code repos, use the snippet in `templates/claude-md-snippet.md` instead — sessions there end by appending to that repo's SYNC-DIGEST.md.
