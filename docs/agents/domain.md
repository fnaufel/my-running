# Domain Docs

The engineering skills use a single-context domain documentation layout.

## Layout

- `GLOSSARY.md` at the repo root defines domain terms.
- `docs/adr/` holds architecture decision records.

## Before exploring

Read `GLOSSARY.md` and any ADRs relevant to the area of work. If they do not exist yet, proceed silently. The `/domain-modeling` skill creates them when terms or decisions are resolved.

## Use the glossary's vocabulary

Use defined domain terms in issue titles, proposals, hypotheses, and tests. If a needed concept is absent, reconsider the term or note the gap for `/domain-modeling`.

## Flag ADR conflicts

If a proposed change contradicts an existing ADR, call out the conflict explicitly.
