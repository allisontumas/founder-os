---
description: Context sync — route inbox + journal by tag, run the two-way project feed, recompile context packs, commit (run before /clear)
---

# /digest (founder-os repo)

## 1. Gather unprocessed capture
- `01-foundation/founder-journal.md` — every dated heading not marked `(synced …)`
- every file in `00-inbox/` except README.md
- each project card's `SYNC-DIGEST.md` `## Unsynced` entries

## 2. Route by tag (grammar in root README)
| Tag / signal | Destination |
|---|---|
| `#belief` | `01-foundation/beliefs.md` (raw intake — distilling is a separate review) |
| `#canon` | `01-foundation/canon.md` |
| `#decision` (company-level) | new `04-decisions/YYYY-MM-DD-<slug>.md` (Date/Decision/Why/Alternatives) |
| `#decision` (project-scoped) | that card's `decisions.md` |
| `#idea` | `02-projects/ideas.md` with rubric score + revisit date |
| `#todo(project)` — business | that card's README, tagged Now/Next/Later per the founder stack |
| `#todo(project)` — build | that project's `SYNC-DIGEST.md` under `## Outbound (from OS)` — never on the card |
| `#content` | the content backlog |
| long-horizon goal/dream | `01-foundation/aspirations.md` |
| untagged / unroutable | stays in `00-inbox/` for the next pass |

Rules: capture is sacred — refine wording in the routed copy, never the journal · one item may route to several destinations · new-project ideas cannot become cards here — the rubric + Connections gate (`templates/project-card.md`) is a founder act.

## 3. Two-way project feed
**Down:** stamp each touched card's Now/Next/Later to match `active-priorities.md` — sequencing flows down.
**Up:** refresh each project's rollup line; if a rollup implies the stack should change, append `⚑ suggest: <change>` — never reorder `active-priorities.md` yourself. The digest suggests; the founder decides.

## 4. Mark processed
Journal headings get `(synced YYYY-MM-DD)` · fully-routed inbox files are deleted (git is the archive) · digest entries move to `## Synced`.

## 5. Recompile context packs
Regenerate `context-packs/founder-pack.md` and `brand-pack.md` from their `compiled-from` sources (≤600 words each). If founder-pack changed materially, flag in the report: **"founder-pack drifted — re-paste into chat models."**

## 6. Housekeeping & report
Bump `updated:` frontmatter on touched files · commit context changes alone: `sync: YYYY-MM-DD digest` · report: routed items (source → destination), rollup, `⚑ suggest:` lines, inbox leftovers, pack drift. Remind to `/clear`.
