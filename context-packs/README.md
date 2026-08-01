---
project: Context Packs
status: active
priority: high
updated: 2026-08-01
tags: [packs, compiled, export]
---

# Context Packs

Compiled, one-page distillations of the repo — the outbound half of bi-directionality. The repo is source code; packs are binaries. `/digest` recompiles them each run and flags drift ("founder-pack drifted — re-paste").

**Consumers:** ChatGPT / Grok custom instructions (paste founder-pack) · brand-facing agents (`.agents/roles/` load brand-pack) · any exposed surface, which gets a pack extract and **never** the raw repo.

Rules: a pack never exceeds ~600 words · packs are generated, never hand-edited (fix the source file instead) · each pack lists its source files so drift is checkable.
