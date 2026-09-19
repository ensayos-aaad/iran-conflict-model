# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

The Iran Conflict Model (ICM) is a completed research artifact, not a software project. There is no source code, no build system, no tests, and no dependencies to install. The repository is a structured, versioned record of 98 days (28 feb–7 jun 2026) of human-AI dialectic geopolitical analysis of the US-Israel-Iran conflict, produced conversationally in claude.ai (not via this CLI) and committed to git as the log of record.

**The formal model is permanently closed (v0.2.0, session S13, 2026-06-07)** and its record (README.md, CHANGELOG.md, PROTOCOLO-ANCHOR.md, `simulaciones/2026-04-06-...` through `...-sesion-13-cierre.md`) is immutable history — never renumber S01–S13, never rewrite their probabilities/conclusions, never re-run the formal ANCHOR protocol as if the project were reopening.

That said, **post-closure tracking is an active, ongoing pattern, not a violation of the closure.** Pendiente P6 ("Retroalimentación del checklist") is explicitly designed to be executed after close, against the Grupo 1/2/3 checklist in README.md. The first such follow-up landed 2026-09-18 as `simulaciones/2026-09-18-sesion-14-seguimiento-extraoficial.md` — a dated, clearly-labeled "seguimiento extraoficial" (unofficial follow-up) that verifies checklist items against fresh press/expert sources, updates scenario probability *ranges* (not the closed point estimates), and revises the falsifiability table. It is explicitly not a new formal session: it doesn't get an S-number in the closed sequence, doesn't touch the `datos/` CSV pipeline, and repeatedly declares itself provisional/open (R4 spirit: "no resuelve por diseño"). If asked to produce another one of these, follow that file's structure and rigor (multi-source cross-checks, explicit falsification checks, declared confidence ranges, K17 external/academic contrast) and name it consistently (`YYYY-MM-DD-sesion-NN-seguimiento-extraoficial.md`, continuing the loose numbering S14, S15, ...) — but do not fold its content back into the closed README/CHANGELOG narrative as if it were part of v0.2.0.

Unlike the closed S01–S13 record, **README.md itself now accumulates one dated `## SEGUIMIENTO POST-CIERRE — SNN (...)` section per follow-up, appended at the end of the file** (after the "ARQUITECTURA DEL MODELO" diagram) — it is the one place in README.md that is meant to keep growing post-closure. Each such section carries its own summary dashboard PNG (see below) and is written to be read on its own (hero stats, a checklist table, a scenario-range table, a plain-language evidence table) rather than assuming the reader has the source `simulaciones/...md` open.

Génesis and full methodology are documented in [README.md](README.md) (architecture, final probabilities, Kaizen log K1–K25), [PROTOCOLO-ANCHOR.md](PROTOCOLO-ANCHOR.md) (the ANCHOR v2.0 operating protocol, R1–R6), [COCREACION.md](COCREACION.md) (human/AI division of labor and responsible-use declaration), and [CHANGELOG.md](CHANGELOG.md) (per-session version history). Read the relevant one before making claims about methodology or history instead of relying on memory of this summary.

## Repository structure

```
README.md                  Master document: architecture, final probabilities, Kaizen K1-K25, ethics audit
CHANGELOG.md                Per-session changelog, S01 -> S13 cierre
PROTOCOLO-ANCHOR.md         ANCHOR v2.0 protocol text (5 blocks, R1-R6 rules) pasted at the start of each session
COCREACION.md                Human/AI co-creation and responsible-use declaration
docs/
  diseno-experimental.md    Experimental design: hypothesis, sampling protocol, Brier score validation method
  prompt-plantilla.md       Daily/emergency/omitted-session prompt templates used to run a session in claude.ai
  guia-captura-datos.md     Non-technical guide for copying a session's CSV output into datos/
  guia-github.md            Non-technical guide for git/GitHub setup and daily push
prompts/README-prompts.md   Prompt documentation methodology (P[N]-titulo.md format)
prompts/YYYY-MM-DD/         Archived prompts (evidencia experimental) grouped by date
simulaciones/YYYY-MM-DD-sesion-NN.md   Full transcript/output of each closed formal session (S01-S13)
simulaciones/YYYY-MM-DD-sesion-NN-seguimiento-extraoficial.md   Post-closure unofficial tracking updates (P6), e.g. S14 (2026-09-18)
simulaciones/img/YYYY-MM-DD-sesion-NN-dashboard.png   Summary dashboard PNG for a seguimiento-extraoficial, linked from README.md's matching section
datos/README-datos.md       Data dictionary for every CSV schema below
datos/entradas/{E1,E2,E4,E5}/          Input CSVs per session (press, timeline, narrative noise, markets)
datos/salidas/{S1,S2,S3,S4}/           Output CSVs per session (narratives, factual state, disinformation, scenarios)
datos/salidas/convergencia.csv         Cumulative time series: one row per session, the model's primary signal
datos/validacion/registro-validacion.csv   Forecast tracking: predicted scenario vs. actual outcome per horizon
```

## Working with this repository

There are no build, lint, or test commands — this is markdown and CSV only. The only "commands" in this repo are git and manual CSV edits:

```bash
git add .
git commit -m "sesión [N] — [FECHA] — [TIPO]"
git push
```

If asked to touch the data layer, follow the conventions in [datos/README-datos.md](datos/README-datos.md) exactly — they are load-bearing for the whole project:
- One CSV per session per input/output type, named `YYYY-MM-DD.csv`, copied from that folder's `schema.csv`.
- Never delete or reorder rows, never change headers, never leave a field blank (write `NULL` instead).
- Dates are `YYYY-MM-DD`; decimals use `.` not `,`; booleans are `TRUE`/`FALSE`.
- `convergencia.csv` and `registro-validacion.csv` are append-only historical series — corrections go in a `notas` field, not by editing/deleting the original row.

## Generating a seguimiento-extraoficial dashboard PNG

There is no in-repo script for this yet — each dashboard so far was generated ad hoc with a Python/matplotlib snippet (light-mode chart surface, `references/palette.md`'s validated categorical/status/sequential colors from the `dataviz` skill, one PNG per follow-up saved to `simulaciones/img/`). If asked to produce another one, load the `dataviz` skill first for the form/color rules, build the figure with matplotlib (already available in this environment), render at a large enough size to read as a "photo" (roughly 2300x1450px), and visually check the rendered PNG for label collisions before embedding it — matplotlib's default spacing does not guarantee that on its own.

## Model architecture (for understanding, not for extending)

The ICM's analytical engine is conversational (Claude in claude.ai), not code: 5 inputs (E1 press, E2 timeline, E3 user questions — undocumented as CSV, E4 narrative noise, E5 markets) feed a reasoning process grounded in Judea Pearl's Ladder of Causation (see/intervene/imagine), Kahneman System 1/2, and Tetlock superforecasting, producing 4 outputs (S1 narrative map, S2 factual state, S3 disinformation index, S4 scenarios) plus a meta-output (convergence signal) through 3 feedback loops. Each session followed the ANCHOR v2.0 protocol's 5 blocks (model grounding → operator grounding → joint limitation declaration → the one question that matters → operating rules R1–R6) — see [PROTOCOLO-ANCHOR.md](PROTOCOLO-ANCHOR.md) for the exact text.

Six mutually exclusive scenarios were tracked across all 13 sessions: A (formal verified agreement), B (prolonged limbo), C (escalation/sabotage — the scenario that ultimately dominated at close, 0.52), D (regime collapse), E (operational wildcard), F (narrative de-escalation without agreement — dominant for most of the project's life, collapsed at close). The project's central structural finding: "F era la sala de espera de C" (F was C's waiting room) — see README.md § CONCLUSIONES ESTRUCTURALES.

## Pending work (P1–P8, from README/CHANGELOG close-out)

If asked to extend this project, check the pendientes table in README.md § II ("PENDIENTES — LO QUE EL ICM NO TERMINÓ") and CHANGELOG.md's anexo first (README's section numbering has shifted after edits — verify with a quick read rather than trusting a cached section number). Items like a Bayesian engine (P1), a China signal follow-up (P2), an ICM-Colombia adaptation (P3), or a pedagogical simplification (P7) are sanctioned directions for new work, scoped as new/separate efforts rather than edits to the closed v0.2.0 record. P6 (checklist retroalimentación) is the one pendiente with an established, repeatable execution pattern — see the seguimiento-extraoficial convention above.
