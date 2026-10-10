# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

The Iran Conflict Model (ICM) is a completed research artifact, not a software project. There is no source code, no build system, no tests, and no dependencies to install. The repository is a structured, versioned record of 98 days (28 feb–7 jun 2026) of human-AI dialectic geopolitical analysis of the US-Israel-Iran conflict, produced conversationally in claude.ai (not via this CLI) and committed to git as the log of record.

**The formal model is permanently closed (v0.2.0, session S13, 2026-06-07)** and its record (README.md, CHANGELOG.md, PROTOCOLO-ANCHOR.md, `simulaciones/2026-04-06-...` through `...-sesion-13-cierre.md`) is immutable history — never renumber S01–S13, never rewrite their probabilities/conclusions, never re-run the formal ANCHOR protocol as if the project were reopening.

That said, **post-closure tracking is an active, ongoing pattern, not a violation of the closure.** Pendiente P6 ("Retroalimentación del checklist") is explicitly designed to be executed after close, against the Grupo 1/2/3 checklist in README.md. The first such follow-up landed 2026-09-18 as `simulaciones/2026-09-18-sesion-14-seguimiento-extraoficial.md` — a dated, clearly-labeled "seguimiento extraoficial" (unofficial follow-up) that verifies checklist items against fresh press/expert sources, updates scenario probability *ranges* (not the closed point estimates), and revises the falsifiability table. It is explicitly not a new formal session: it doesn't get an S-number in the closed sequence, doesn't touch the `datos/` CSV pipeline, and repeatedly declares itself provisional/open (R4 spirit: "no resuelve por diseño"). If asked to produce another one of these, follow that file's structure and rigor (multi-source cross-checks, explicit falsification checks, declared confidence ranges, K17 external/academic contrast) and name it consistently (`YYYY-MM-DD-sesion-NN-seguimiento-extraoficial.md`, continuing the loose numbering S14, S15, ...) — but do not fold its content back into the closed README/CHANGELOG narrative as if it were part of v0.2.0.

The second follow-up, **S15 (2026-10-09, `simulaciones/2026-10-09-sesion-15-seguimiento-extraoficial.md`)**, established the current working pattern, which the operator expects to be repeated:

1. **The operator brings a list of facts from their own press reading before the analysis starts**, often in a few batches and sometimes vague, misdated or with the wrong subject. They have said their access to international news is limited and that coverage of the Iran war is shrinking. Evaluate each fact for relevance against the checklist and scenarios first, ask for clarifications, and **do not write files until the operator says the list is complete and says to start.**
2. **Agree on a source plan before searching**, spread across blocs to offset the English/Western bias the README's ethics audit declares: wire agencies, US, Europe, Gulf/Arab (K7), Iran (state *and* opposition, both treated as positions rather than proof), Israel, China (K24), Latin America in Spanish (P8), markets (E5) and expert voices of declared orientation (K17). Rule: "verified" needs ≥2 independent sources from different blocs; a single source is "plausible, no verificado"; "not found" never means "didn't happen".
3. **Verify every operator fact in its own table** (✅/🟡/⚪ plus corrections). Several facts that reached the operator as "new" turned out to be weeks old or to predate the previous cut-off, so check dates explicitly.
4. **Then proactively look for what the list missed** (threads from the previous follow-up that weren't revisited, plus anything new). S15 put these in a separate "Ampliación" section (§10) so the operator's facts and the model's own additions stay distinguishable.
5. Include a self-critique section listing what the previous follow-up missed or got wrong (S15 found five pre-S14 facts that S14 never recorded, plus a modeling error on Netanyahu's caretaker status).

**State left open by S15 — check these first in the next follow-up (S16):**

- **The 3 Nov 2026 US midterms end Trump's declared pause on striking Iran.** S15 recorded a dated falsification criterion for "F era la sala de espera de C": if US/Israeli strikes on Iran resume after 3 Nov, the thesis is confirmed; if none by 31 Dec and negotiation moves toward a text, it is weakened.
- **Two dated predictions of the K26 candidate** (refined in S15: proximity to an accountability event predicts *that* behavior changes; what each actor's electorate punishes predicts the *direction*): Netanyahu's behavior after the 27 Oct Israeli election, and Trump's toward Iran after 3 Nov.
- **Other dates to watch:** the Pentagon's livestreamed firing-squad execution scheduled for 3 Dec (a test case for the "cortinas de humo" analysis: patterns, not proof); the 25 Oct Brazil runoff; the 28 Oct Fed meeting; the 29–30 Oct Canada–EU summit; Colombia's embassy in Jerusalem (15 Oct, closes checklist item 3.7).
- **Declared gaps:** the current state of the AI bubble (Nvidia/Burry) wasn't verified; the date of the Oman-led mediation and Hormuz corridor proposal is unconfirmed; Colombia hasn't officially confirmed the MQ-9s; Iran protest figures come from opposition sources.
- **S15 ranges to 31 Dec:** C 0.42–0.54, F 0.16–0.22, B 0.11–0.17, A 0.04–0.07, E 0.07–0.12, D 0.04–0.08; convergence 0.44–0.50. Recheck in the file rather than trusting this summary.

Unlike the closed S01–S13 record, **README.md itself now accumulates one dated `## SEGUIMIENTO POST-CIERRE — SNN (...)` section per follow-up, appended at the end of the file** (after the "ARQUITECTURA DEL MODELO" diagram) — it is the one place in README.md that is meant to keep growing post-closure. Each such section carries its own summary dashboard PNG (see below) and is written to be read on its own (hero stats, a checklist table, a scenario-range table, a plain-language evidence table) rather than assuming the reader has the source `simulaciones/...md` open.

Génesis and full methodology are documented in [README.md](README.md) (architecture, final probabilities, Kaizen log K1–K25), [PROTOCOLO-ANCHOR.md](PROTOCOLO-ANCHOR.md) (the ANCHOR v2.0 operating protocol, R1–R6), [COCREACION.md](COCREACION.md) (human/AI division of labor and responsible-use declaration), and [CHANGELOG.md](CHANGELOG.md) (per-session version history). Read the relevant one before making claims about methodology or history instead of relying on memory of this summary.

**Licensed under [CC BY-SA 4.0](LICENSE)** (added 2026-09-18) — reuse/adaptation (e.g. an ICM-Colombia per pendiente P3) is explicitly permitted with attribution and share-alike.

**Known gap: the quantitative data layer was never actually operated.** `datos/salidas/convergencia.csv` and `datos/validacion/registro-validacion.csv` contain only the S01 inaugural row — none of the 226 vectors across 13 sessions were ever captured as CSV rows, so the Brier Score validation that `docs/diseno-experimental.md` names as the project's success metric was never computed. Don't assume the `datos/` pipeline was exercised just because it's thoroughly documented in `datos/README-datos.md` and `docs/guia-captura-datos.md` (which now carries an explicit caveat about this) — treat any claim of "validated" or "measured" convergence/forecast accuracy as narrative judgment (as in the S14 seguimiento), not as data-backed.

## Repository structure

```
README.md                  Master document: architecture, final probabilities, Kaizen K1-K25, ethics audit
LICENSE                     CC BY-SA 4.0
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
simulaciones/YYYY-MM-DD-sesion-NN-seguimiento-extraoficial.md   Post-closure unofficial tracking updates (P6): S14 (2026-09-18), S15 (2026-10-09)
simulaciones/img/YYYY-MM-DD-sesion-NN-dashboard.png   Summary dashboard PNG for a seguimiento-extraoficial, linked from README.md's matching section
investigacion/              Post-closure research line on the METHOD (not the conflict), started 2026-10-10: state of the art, conceptual framework, candidate patterns, process-line model, CEM comparison case, preregistration
datos/README-datos.md       Data dictionary for every CSV schema below
datos/entradas/{E1,E2,E4,E5}/          Input CSVs per session (press, timeline, narrative noise, markets)
datos/salidas/{S1,S2,S3,S4}/           Output CSVs per session (narratives, factual state, disinformation, scenarios)
datos/salidas/convergencia.csv         Cumulative time series: one row per session, the model's primary signal
datos/validacion/registro-validacion.csv   Forecast tracking: predicted scenario vs. actual outcome per horizon
```

## Research line on the method (`investigacion/`)

Started 2026-10-10 at the operator's request. It evaluates **the human-AI dialectic method itself**, aiming at an academic output: a case-study / Design Science framing, where the protocol is the artifact. The research question: does structured human-AI dialectic produce genuine consilience or false consilience (apophenia)? Start at [investigacion/README.md](investigacion/README.md). Rules that matter:

- **It never edits the closed v0.2.0 record.** It cites it.
- **The preregistration must be frozen before 2026-10-26**: commit, push and OSF. After that, `investigacion/protocolo-evaluacion-cierre-2026.md` is **never edited**; corrections go in a new dated document. One point probability per question, each with a written resolution rule.
- **References cited from memory carry †** until verified online. Never present a † reference as verified.
- **A second case exists:** the CEM (Colombia Electoral Model, [ensayos-aaad/modelo-electoral-colombia](https://github.com/ensayos-aaad/modelo-electoral-colombia)), an "ICM Lite" variant. It is **resolved and was wrong** (projected Cepeda, P = 0.52; De la Espriella won; Polymarket at 89% was right). Treat it as the comparison case, not as a success.
- **Consilience is not a new idea for this project:** V24 (S02 part 2) and V33 (the "Chomsky factor" warning about integrating captured narratives, S03) introduced it in April 2026. Check the record before presenting an idea as new.
- **The narrated "convergencia" in S14/S15 is a judgment, not a measure.** The Shannon entropy of the year-end scenario distribution rises S13 → S14 → S15 (1.976 → 2.033 → 2.143 bits), contradicting S15's claim that convergence rose. See investigacion/marco-conceptual.md §6.
- **The operator's personal academic or professional situation** stays out of this public CC BY-SA repo unless they explicitly decide otherwise.
- **Rule for excluded sources (operator decision, 2026-10-10): keep what was previously defined, change nothing.** The CEM's exclusions (Semana, El Colombiano, AtlasIntel, La Silla Vacía) stand; do not add La Silla Vacía to ICM follow-ups. The ICM never had an exclusion list. R-5 (justify and periodically contrast any exclusion) is only a proposed restriction for future variants. Declared, uncorrected inconsistency: S15 used Semana as the single source for the date of Colombia's Jerusalem embassy.

## Working with this repository

There are no build, lint, or test commands — this is markdown and CSV only. The only "commands" in this repo are git and manual CSV edits:

```bash
git add .
git commit -m "sesión [N] — [FECHA] — [TIPO]"
git push
```

Post-closure follow-ups use a different format: `feat(seguimiento): SNN extraoficial post-cierre — <summary>` (see S14 and S15 in `git log`). Commit only when the operator asks, and don't push without asking.

If asked to touch the data layer, follow the conventions in [datos/README-datos.md](datos/README-datos.md) exactly — they are load-bearing for the whole project:
- One CSV per session per input/output type, named `YYYY-MM-DD.csv`, copied from that folder's `schema.csv`.
- Never delete or reorder rows, never change headers, never leave a field blank (write `NULL` instead).
- Dates are `YYYY-MM-DD`; decimals use `.` not `,`; booleans are `TRUE`/`FALSE`.
- `convergencia.csv` and `registro-validacion.csv` are append-only historical series — corrections go in a `notas` field, not by editing/deleting the original row.

## Generating a seguimiento-extraoficial dashboard PNG

There is no in-repo script for this yet — each dashboard so far was generated ad hoc with a Python/matplotlib snippet (light-mode chart surface, `references/palette.md`'s validated categorical/status/sequential colors from the `dataviz` skill, one PNG per follow-up saved to `simulaciones/img/`). If asked to produce another one, load the `dataviz` skill first for the form/color rules, build the figure with matplotlib (already available in this environment), render at a large enough size to read as a "photo" (roughly 2300x1450px), and visually check the rendered PNG for label collisions before embedding it — matplotlib's default spacing does not guarantee that on its own.

S15's dashboard is the most recent layout to reuse: four hero stats, scenario range bars (current range in blue, previous range in gray, S13 close as a black diamond), a stacked bar of the operator-fact verification results in status colors, a Grupo 3 dumbbell (previous vs. current midpoint, labeled with ranges rather than false-precision decimals), and a timeline of hinge dates. Its script lived in a temporary scratchpad and was not saved to the repo, so rebuild it from this description.

## Model architecture (for understanding, not for extending)

The ICM's analytical engine is conversational (Claude in claude.ai), not code: 5 inputs (E1 press, E2 timeline, E3 user questions — undocumented as CSV, E4 narrative noise, E5 markets) feed a reasoning process grounded in Judea Pearl's Ladder of Causation (see/intervene/imagine), Kahneman System 1/2, and Tetlock superforecasting, producing 4 outputs (S1 narrative map, S2 factual state, S3 disinformation index, S4 scenarios) plus a meta-output (convergence signal) through 3 feedback loops. Each session followed the ANCHOR v2.0 protocol's 5 blocks (model grounding → operator grounding → joint limitation declaration → the one question that matters → operating rules R1–R6) — see [PROTOCOLO-ANCHOR.md](PROTOCOLO-ANCHOR.md) for the exact text.

Six mutually exclusive scenarios were tracked across all 13 sessions: A (formal verified agreement), B (prolonged limbo), C (escalation/sabotage — the scenario that ultimately dominated at close, 0.52), D (regime collapse), E (operational wildcard), F (narrative de-escalation without agreement — dominant for most of the project's life, collapsed at close). The project's central structural finding: "F era la sala de espera de C" (F was C's waiting room) — see README.md § CONCLUSIONES ESTRUCTURALES.

## Pending work (P1–P8, from README/CHANGELOG close-out)

If asked to extend this project, check the pendientes table in README.md § II ("PENDIENTES — LO QUE EL ICM NO TERMINÓ") and CHANGELOG.md's anexo first (README's section numbering has shifted after edits — verify with a quick read rather than trusting a cached section number). Items like a Bayesian engine (P1), a China signal follow-up (P2), an ICM-Colombia adaptation (P3), or a pedagogical simplification (P7) are sanctioned directions for new work, scoped as new/separate efforts rather than edits to the closed v0.2.0 record. P6 (checklist retroalimentación) is the one pendiente with an established, repeatable execution pattern — see the seguimiento-extraoficial convention above.
