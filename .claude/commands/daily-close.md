---
description: The Daily Close — one batched full-scope sweep (digest + card reconciliation + pipeline check) producing a single report. Run once a day.
---

# /daily-close

Per-project digest runs leak: projects without code repos have no loop that closes their tasks, and the founder becomes the scheduler. This command is the fix — one run, whole OS, one report.

## 1. Full digest pass
Run everything in [.claude/commands/digest.md](digest.md) — gather, route, two-way feed, mark processed, recompile packs. All its rules apply.

## 2. Card reconciliation (the repo-less leak)
For EVERY card in `02-projects/` and `03-studio/` — with or without a SYNC-DIGEST:
- Check each unchecked to-do against today's journal, inbox, and digests: if the work happened, check it off with `(closed YYYY-MM-DD)`.
- Flag any **(Now)** item untouched for 7+ days as `stale` in the report — never demote it yourself.
- If a card's status section contradicts newer capture, update the card (card follows capture, never the reverse).

## 3. Pipeline check (if you keep one)
For each open lead in your pipeline file: confirm a next action with a date exists; flag leads untouched for 5+ days. Stale-lead flags go at the TOP of the report — revenue outranks tidy markdown.

## 4. The one report
Single summary: leads needing touch · to-dos closed today · items routed (source → destination) · stale Now items · ⚑ suggests awaiting the founder · inbox leftovers · pack drift. Commit per digest rules, then /clear.

**Cadence:** once daily. If /digest already ran today, skip step 1 and run 2–4 only.
