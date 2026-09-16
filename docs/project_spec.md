# CITS3011 Intelligent Agent Project 2026 (text version of the official PDF)

Source: `docs/CITS3011_Intelligent_Agent_Project_2026.pdf`. This is a faithful
plain-text transcription for grepping and quick reference. The PDF is authoritative.

- Groups of two or three students. One mark per group, every member gets the same mark.
- Marked out of 30, worth 30% of the unit mark.
- **Due 11:59 pm AWST, Friday 2 October 2026.** Submit early; late penalties may apply.

## Description

Research, design, develop, evaluate and analyse an agent for playing the game
**Diplomacy**. Assessed on (1) agent performance and (2) a written report on the
techniques investigated and developed. Treat it as a novel problem: **do not reuse any
existing code or computational solutions for Diplomacy.**

## Introduction to Diplomacy

Seven players compete and cooperate to capture supply centres on a map of Europe.
Very large action and state spaces. Required reading and tools:

- Game rules: https://en.wikibooks.org/wiki/Diplomacy/Rules
- Game engine: https://github.com/diplomacy/diplomacy
- Engine documentation: https://diplomacy.readthedocs.io/en/stable/
- Optional statistics: https://vdiplomacy.net/variants.php?variantID=1
- Optional database: https://world-diplomacy-database.com
- Play online: https://webdiplomacy.net/

## Getting started

Download `the_diplomacy_2026.zip`. Build the agent in `agent_groupnumber.py`
(replace `groupnumber` with the group number). After renaming, update the import in
`test.py` and `visualize.py`. Subclass the `Agent` class from `agent_baselines.py`
and override/implement methods.

1. Create a virtual environment (conda or venv, recommended).
2. Install: `pip3 install diplomacy tqdm networkx numpy timeout-decorator`
   or `pip3 install -r requirements.txt`.
3. `python3 test.py` runs a large number of games and reports agent performance.

Objective: maximise expected performance when the agent is dropped into complex
(possibly unknown) scenarios. `test.py` may be reused/adapted during development.
After submission the agent is tested under multiple scenarios against multiple
baseline agents.

## Game setup

- Standard map.
- **No Press** mode (no messages between agents).
- Game ends in the year **1920** if there is no winner before then.

## Agent rules

- Must implement the provided Python interface.
- **Time limit: every action must complete within 1 second.**
- **Memory limit: 512 MB.**
- Agents may not save files.
- Agents must not circumvent or hack the simulation.
- No internet, no API calls (e.g. to LLMs).
- No GPU access.
- Suspected violations may mean disqualification and no mark.

## Report

- Details the techniques researched and investigated, the reasoning behind the
  design and technique choices, and the assessment/analysis of the agent's
  effectiveness.
- **Maximum four A4 pages**, submitted as a **PDF**.
- Must state the group number and the full names and student numbers of all members.
- All members are responsible for the contents.
- Not a PDF: may receive no mark. Over length: may receive no mark or be truncated.
  Illegible formatting (tiny font etc.): may receive no mark.

## Baseline agents (five)

- **Static Agent**: always takes the default action, i.e. hold.
- **Random Agent**: always takes random actions.
- **Attitude Agent**: random actions, but holds an attitude (friendly, neutral or
  hostile) towards each other power that depends on their actions and can change
  during the game. Friendly never attacks you; hostile never supports you; neutral
  can do anything.
- **Greedy Agent**: greedy actions without long-term planning. Each unit moves
  towards and attacks the closest supply centre, or supports other units that have
  the same target.
- **Hidden Agent**: unknown.

## Scenarios

- **Scenario 1**: our agent controls a random power; all other powers are Static.
- **Scenario 2**: our agent controls a random power; other powers are copies of agents
  chosen randomly from Random, Attitude and Greedy. Random is less likely than the
  other two.
- **Scenario 3**: as Scenario 2 plus Hidden; exactly one Hidden Agent per game. Hidden
  is reasonably strong, with about a 50% win rate in Scenario 2.
- **Scenario 4**: all group agents play a multi-round tournament.

## Marking

Agent and report are marked independently. Agent marking focuses on performance;
report marking on knowledge, thinking, reasoning and presentation.

### Agent rubric (15 pts) [1]

Each tier is met by **either** the win rate **or** the average supply centres captured.

| Scenario | 1 pt | 3 pts | 5 pts |
|---|---|---|---|
| 1 | >2% win or >7 SC | >20% win or >12 SC | >90% win or >16 SC |
| 2 | >2% win or >7 SC | >25% win or >10 SC | >50% win or >13 SC |
| 3 | >2% win or >7 SC | >20% win or >9 SC | >40% win or >12 SC |

- Scenario 4 (bonus) [2]: agent ranks top 3 among all group agents: 3 bonus pts.

### Report rubric (15 pts)

- **Basic technique (6 pts)**
  - Considers and describes one basic technique [3] as the basic method. Can be from
    the lectures or another existing technique [4]. (2 pts)
  - Discusses the motivation for the basic technique and justifies the choice. (2 pts)
  - Evaluates and analyses its effectiveness with quantitative experimental
    results [5]. (2 pts)
- **New techniques (9 pts)**
  - Creates and describes three new techniques [6][7] designed by the group for
    improvement (e.g. improving the basic method). (3 pts, 1 each)
  - Discusses the motivations and justifies the designs. (3 pts, 1 each)
  - Evaluates and analyses their effectiveness with quantitative experimental
    results [5]. (3 pts, 1 each)

### Rubric notes

1. Baseline agents are provided; reading their code is allowed. Plagiarising them
   (e.g. copying them to score in some scenarios) may mean no mark.
2. Total after bonus is capped at 30.
3. The basic technique must be implemented in the submitted code and referenced from
   the report, even if the final agent does not use it.
4. Other existing techniques need references in the report. Reusing existing code is
   prohibited.
5. Results may be positive or negative; marking focuses on meaningful presentation
   and analysis, not the exact numbers.
6. A new technique can be e.g. a new heuristic function, a variant of the search
   process, or a modification of a basic technique. Must be well motivated and
   justified. The three must be distinct; parameter tuning does not count.
7. New techniques must be implemented in the submitted code and referenced from the
   report. At least three must be tried and implemented even if not all are used in
   the final agent.

## Submission (one submission per group, to LMS)

- `agent_groupnumber.py`: the agent (max 100 KB).
- `report_groupnumber.pdf`: the report (max 4 pages).
- `test_groupnumber.py`: the group's experiments (max 100 KB).

### Allowed packages

Python 3 built-ins plus (use the provided `requirements.txt` for consistent versions):
diplomacy, tqdm, random, networkx, numpy, scipy, scikit-learn, timeout-decorator,
simpleai (https://pypi.org/project/simpleai/).
The textbook implementation may be used as a coding reference:
https://github.com/aimacode/aima-python.

### LLM / GenAI policy

- LLMs may be used for brainstorming, co-designing and coding assistance.
- LLMs may **not** be used for report writing.
- If any member uses LLMs, the group must submit one combined extra PDF recording
  **all the prompts**, named `llm_usage_groupnumber.pdf`.
- The agent itself cannot use any LLM.
