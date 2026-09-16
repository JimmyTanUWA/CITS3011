# LLM usage log — CITS3011 Diplomacy project

The project spec requires that if any group member uses an LLM, the group submits one
combined PDF recording **all prompts** (`llm_usage_groupnumber.pdf`). LLMs may be used
for brainstorming, co-design and coding assistance, but **not for report writing**.

This file is the running record. Every prompt is logged verbatim, in order, with the
tool used and a one-line note of what the tool did in response. Append every new
session (Claude Code, ChatGPT, anything else) using the template at the bottom, then
export this file to PDF before submission (e.g. open in a browser and print to PDF, or
`pandoc prompt_log.md -o llm_usage_groupnumber.pdf`).

Times are AWST (UTC+8). Times marked `~` are approximate.

---

## Session 1 — 2026-09-16 — Claude Code (Anthropic coding agent, claude.ai/code)

Group member: [name]. Purpose: project kickoff, spec reading, advisor prompt, first
agent design steps. No report text was requested or produced.

### Prompt 1 (~10:17)

```
hello, make a branch, todays date, jimmysfirststeps. catch me up to speed. i havent looked at the project
```

Response: created and pushed branch `2026-09-16-jimmysfirststeps`; reported that the
repo held only a two-line README and no spec.

### Prompt 2 (~10:30)

Attached file: `CITS3011_Intelligent_Agent_Project_2026.pdf` (the official project spec).
No text was typed with the attachment.

Response: extracted and read the spec.

### Prompt 3 (~10:35, sent while the previous request was running)

```
firstly give me a metaprompt for chatgpt as my cits3011 advisor
```

Response: wrote `docs/llm_usage/chatgpt_advisor_metaprompt.md` (the instructions block
for a ChatGPT project/custom GPT acting as a project advisor; it forbids report writing
and reuse of existing Diplomacy code) and summarised the spec: deadline, marks split,
constraints, LLM logging requirement, missing starter kit.

### Prompt 4 (~12:00)

```
lets pick a heuristic of going past the stalemate line. just run with that, build a visualisation after this is done. see how we go. tell me waht you need at this point from me
```

Response (work in progress, interrupted by Prompt 5): set up a Python venv with the
allowed packages; probed the `diplomacy` engine API (order string formats for moves,
supports, convoys, retreats, builds and disbands; phase flow; timing of possible-order
generation, phase processing and game copying; SVG rendering structure); no agent code
written yet.

### Prompt 5 (~12:12, interrupting the previous task)

```
find gaps in my understanding with this project. ill put a text file in this directory of what i understand, then you catch me up to speed, because you have read the project requirements.
```

Response: paused the agent build; waiting for the understanding file.

### Prompt 6 (~12:14)

```
ok log every single prompt for me, including this one in a file.
```

Response: created this file, plus `docs/project_spec.md` (text transcription of the
spec), `.gitignore`, `requirements.txt`, and committed them to the branch.

### Prompt 7 (~12:22)

```
find CITS3011 Project report doc. fill in the template first. note to marker that the template is generated. get my feet wet first.
```

Response: found the blank Google Doc "CITS3011 Project report" in Drive; created a
sibling doc "CITS3011 Project report (template)" and `docs/report_template.md`
containing a rubric-mapped skeleton: headings, bracketed guidance, empty results
tables, a note to the marker that the skeleton was LLM-generated, and a submission
checklist. No report prose was written (the unit forbids LLM report writing).

---

## ChatGPT advisor sessions

The instructions block used to set up the ChatGPT advisor is in
`docs/llm_usage/chatgpt_advisor_metaprompt.md` and counts as a prompt. Log each
ChatGPT conversation below in the same format (prompt verbatim, one-line response note).

---

## Template for new entries

```
## Session N — YYYY-MM-DD — <tool> 

Group member: <name>. Purpose: <one line>.

### Prompt N (HH:MM)

<prompt text verbatim, in a code block>

Response: <one line: what the tool produced; note explicitly if any code was adopted>
```
