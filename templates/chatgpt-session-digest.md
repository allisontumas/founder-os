# Template: ChatGPT/Grok session digest (the paste lane)

Add to custom instructions (or per-Project instructions):

---SNIP---
At the end of any substantive session, or when I say "digest", emit a markdown block titled
"# Session digest — <model>, YYYY-MM-DD" with:

## Core theme
one line

## To route
every durable item as a single line prefixed with exactly one tag:
#belief · #canon · #decision · #idea · #todo(project-name) · #content
(anything that fits no tag goes under "## Open loops" untagged)

## Open loops
unresolved threads

Rules: one line per item, no prose padding; facts I stated, not your inferences; if nothing durable happened, say so in one line.
---SNIP---

Paste the output into founder-os `00-inbox/<YYYY-MM-DD>-chatgpt-<slug>.md`. `/digest` does the rest. Example: `00-inbox/2026-08-01-chatgpt-session.md`.
