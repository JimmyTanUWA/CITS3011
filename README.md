# CITS3011 Intelligent Agents project (2026): a Diplomacy agent

Group project for CITS3011 (UWA). We build an agent that plays the board game
Diplomacy (standard map, no-press, games end in 1920) using the open-source
`diplomacy` Python engine, and write a four-page report on the techniques used.

**Due: 11:59 pm AWST, Friday 2 October 2026.** Worth 30% of the unit.

## Read first

- `docs/project_spec.md`: the full spec in text form (the PDF in `docs/` is authoritative).
- `docs/llm_usage/prompt_log.md`: every LLM prompt used on this project, required for
  submission. Add yours.

## Key constraints (from the spec)

- Agent must subclass `Agent` from the official `agent_baselines.py` (starter kit
  `the_diplomacy_2026.zip`, not yet in this repo).
- 1 second per action, 512 MB memory, no file writes, no internet, no LLM calls, no GPU.
- Allowed packages only: see `requirements.txt`.
- No reuse of existing Diplomacy code or solutions.
- Submission: `agent_<group>.py`, `report_<group>.pdf` (4 pages max),
  `test_<group>.py`, `llm_usage_<group>.pdf`.

## Setup

```
python3 -m venv .venv
source .venv/bin/activate      # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

## Status

- 2026-09-16: repo created, spec transcribed, environment verified against
  `diplomacy` 1.1.2. Agent design in progress (stalemate-line heuristic).
