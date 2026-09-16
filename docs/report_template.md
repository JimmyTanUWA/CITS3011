# CITS3011 Intelligent Agent Project 2026: Report (template)

Markdown copy of the Google Doc "CITS3011 Project report (template)". Guidance is in
square brackets; delete every bracketed line before submission. Hard limits: PDF,
maximum 4 A4 pages, legible font (11 pt body is safe). Suggested budget: 0.4 page
introduction, 1 page basic technique, 2 pages new techniques, 0.5 page overall results
and discussion, then references.

**Group number:** [___]
**Members:** [Full name, student number]; [Full name, student number]; [Full name, student number]

*Note to marker: the skeleton of this document (section headings, structure and
bracketed placeholders) was generated with an LLM as an outline of the marking rubric.
All prose, figures, results and analysis are written by the group members. Every LLM
prompt used during the project is recorded in llm_usage_[group].pdf, submitted with
this report.*

## 1. Introduction

[About 0.4 page. State the task in your own words: Diplomacy, standard map, no-press,
game ends 1920, 1 second per action, 512 MB, CPU only, no file writes. Say what the
agent must decide in each phase (movement orders for every unit, retreats, builds and
disbands) and why that is hard (joint action space, six simultaneous opponents, no
communication). Finish with a two-sentence overview of the agent: the basic technique
plus the three additions, and the name of the code file.]

## 2. Basic technique (6 marks)

### 2.1 Description (2 marks)

[Name the technique and where it comes from: a lecture topic or a cited source.
Describe it precisely enough that a reader could re-implement it: inputs, the search
or decision procedure, the evaluation or heuristic used, and how the 1 second budget
is respected. Reference the class or function in agent_[group].py. Spec note [3]: it
must be implemented in the submitted code even if the final agent does not use it.]

### 2.2 Motivation and justification (2 marks)

[Why this technique for this game under these constraints? Compare against at least
one alternative you rejected and say why: time limit, state space size, no training
data, no GPU.]

### 2.3 Evaluation and analysis (2 marks)

[Experimental setup first: games per scenario, random seeds, which baselines, metrics
(win rate, average supply centres, maximum time per action). Then quantitative results
(Table 1 or a figure) and analysis: where it does well, where it fails and why. Spec
note [5]: negative results are fine if the analysis is meaningful.]

[Table 1: basic technique alone.]

| Scenario | Games | Win rate | Average SCs | Max time per action (s) |
|---|---|---|---|---|
| 1 | | | | |
| 2 | | | | |
| 3 | | | | |

## 3. New techniques (9 marks)

[Three distinct techniques designed by the group. Spec note [6]: a new heuristic, a
search variant, or a modification of the basic method; parameter tuning does not
count. Each earns 1 mark for description, 1 for motivation, 1 for evaluation. Spec
note [7]: each must be implemented and referenced in the code, even if not used in the
final agent.]

### 3.1 New technique 1: [working title: stalemate-line heuristic]

**Description.** [What it is, exactly. Define any map partition, weights or rules.
Reference the code.]

**Motivation.** [Which weakness of the basic technique it targets, and the Diplomacy
reasoning behind it, for example why 18 centres cannot be reached without crossing the
line.]

**Evaluation.** [Ablation: basic versus basic plus this technique, same seeds and game
counts. Numbers first, then analysis.]

### 3.2 New technique 2: [working title]

**Description.** [ ]

**Motivation.** [ ]

**Evaluation.** [ ]

### 3.3 New technique 3: [working title]

**Description.** [ ]

**Motivation.** [ ]

**Evaluation.** [ ]

## 4. Overall results and discussion

[Final agent configuration: which techniques are switched on. Table 2 with all
configurations side by side, compared against the rubric thresholds for each scenario.
Limitations, failure cases seen in games, what you would try next.]

[Table 2: ablation summary.]

| Configuration | S1 win% / avg SC | S2 win% / avg SC | S3 win% / avg SC |
|---|---|---|---|
| Basic | | | |
| + NT1 | | | |
| + NT2 | | | |
| + NT3 | | | |
| All | | | |

## References

[Required for any existing technique you use (spec note [4]). Lecture slides count as
sources; cite them properly. Likely entries: Russell and Norvig, Artificial
Intelligence: A Modern Approach; the diplomacy engine, github.com/diplomacy/diplomacy;
the Diplomacy rules, en.wikibooks.org/wiki/Diplomacy/Rules.]

## [Delete before submission] Submission checklist

- [PDF, 4 pages maximum, group number and every member's full name and student number on page 1]
- [Files: agent_[group].py (100 KB max), report_[group].pdf, test_[group].py (100 KB max), llm_usage_[group].pdf]
- [All four techniques exist in agent_[group].py and are referenced by name in this report]
- [Every number in this report is reproducible from test_[group].py]
- [No existing Diplomacy code reused; references given for existing techniques]
- [No LLM-written prose anywhere in this document]
