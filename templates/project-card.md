# Template: project card

A business bet's folder in `02-projects/`. **README is mandatory; create the rest the day each first has real content.** The gate: no card until the bet scores ≥12 on `01-foundation/prioritization.md` AND the Connections section below is written.

```
02-projects/<name>/
├── README.md            # What/Why(Connections link)/Status/Business to-dos (Now-Next-Later)/Open questions/Links
├── product-vision.md    # philosophy + Connections (required section, below)
├── current-sprint.md    # where things stand
├── roadmap.md           # sequencing
├── decisions.md         # project-scoped decisions (graduate to 04-decisions/ when they generalize)
├── feedback.md          # evidence intake: who, what, date, what changed
└── SYNC-DIGEST.md       # only if a code repo exists (templates/SYNC-DIGEST-template.md)
```

Required in every product-vision.md:

```markdown
## Connections
- **Consciousness:** which principle/belief/canon entry this expresses (link it)
- **Brand:** what this lets the brand say publicly that it couldn't before
- **Flywheel:** which other bets this feeds
```

Rules: the card owns **business** to-dos; the code repo owns **build** to-dos (via the digest Outbound lane) — never mix, never mirror. Worked example: `02-projects/scope-sentry/`. Young-card example: `02-projects/critical-path-weekly/`.
