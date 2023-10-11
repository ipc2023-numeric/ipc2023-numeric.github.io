---
layout: default
title: International Planning Competition 2023 - Numeric Tracks
---

# International Planning Competition 2023 - Numeric Tracks

This is the website for the numeric tracks of the [IPC 2023](https://ipc2023.github.io).


## Calls
Please forward the following calls to all interested parties.

 - [Call for Domains](calls/ipc2023-call-for-domains.txt)


## Preliminary Schedule

| Event                                   | Date |
|:----------------------------------------|:-----|
| Domain submission deadline              | 9th December 2022 |
| Demo problems provided                  | December 2022|
| Planner submission opens                | February 28 2023 |
| Final Planner submission                | April 19 2023  |
| Planner Abstract submission deadline    | May 24 2023 |
| Contest run                             | May-June 2023 |
| Results announced                       | July 2023 |
| Result analysis deadline                | August 2023 |


## Tracks


### Optimal Track

- single CPU core
- 8Gb memory limit
- 30min time limit
- Plans must be optimal
- The score of a planner is the number of solved tasks
- If a suboptimal or invalid plan is returned, all tasks in the domain are counted as unsolved.
- If that happens in more than one domain, the entry is disqualified.

### Satisficing Track

- single CPU core
- 8Gb memory limit
- 30min time limit
- Multiple plans can be returned, the one with the lowest cost is counted.
- The score of a planner on a solved task is the ratio C/C where C is the cost of the cheapest discovered plan and C* is the cost of a reference plan. The score on an unsolved task is 0. The score of a planner is the sum of its scores for all tasks.
- If an invalid plan is returned, all tasks in the domain are counted as unsolved.
- If that happens in more than one domain, the entry is disqualified.

### Agile Track

- single CPU core
- 8Gb memory limit
- 5min time limit
- The cost of the discovered plan is ignored, only the CPU time to discover a plan is counted.
- The score of a planner on a solved task is 1 if the task was solved within 1 second and 0 if the task was not solved within the resource limits. If the task was solved in T seconds (1 ≤ T ≤ 300) then its score is 1 - log(T)/log(300). The score of a planner is the sum of its scores for all tasks.
- If an invalid plan is returned, all tasks in the domain are counted as unsolved.
- If that happens in more than one domain, the entry is disqualified.

## PDDL Fragment

We will use a subset of PDDL 2.1, considering two fragments:
- Simple Numeric Planning (SNP): Numeric variables can only be increased or decreased by a constant using the increase and decrease operations.
- Linear Numeric Planning (LNP): In addition to SNP, numeric variables can now be also assigned directly using the assign operator and the right-hand of an effect can now be a linear combination.

Preconditions and goals are arbitrary propositional formulas. That is, they include quantifiers, negative preconditions, disjunctive preconditions and any number of numeric predicates. Conditional effects are not considered. Terms can either be literals as in classical planning, or numeric terms of the form f(X){ >=,>, =} 0 where f(X) is a linear expressions. Each domain of  the competition will be either a SNP or a LNP (LNP is more expressive than SNP).
Planners supporting only SNP will be accepted and their performance will be reported when compared with respect to only SNP problems. A planner can also only support SNP. We are considering to have separate rankings.

In terms of the optimisation track, the optimisation functions will always be a minimisation. Problems will either be a minimisation of action costs, or a metric function that is a weighted sum with positive coefficients where each involved variable can only be increased by the actions.

Sample problems are here: [Domain1](sample_problems/d1.pddl), [Problem1](sample_problems/p1.pddl), [Domain2](sample_problems/d2.pddl), [Problem2](sample_problems/p2.pddl), [Domain3](sample_problems/d3.pddl), [Problem3](sample_problems/p3.pddl)

## Participant Teams

- **LNM-Plan** [(planner abstract)](abstracts/NLM_CutPlan_Abstract.pdf)[(frozen source)](https://github.com/ipc2023-numeric/team-1) <br />
  by Ryo Kuroiwa, Alexander Shleyfman and J. Christopher Beck
- **OMTPlan** [(planner abstract)](https://content.iospress.com/articles/journal-on-satisfiability-boolean-modeling-and-computation/sat220001)[(frozen source)](https://github.com/ipc2023-numeric/team-2) <br />
  by Francesco Leofante

## Results 

The results were presented at the 33rd International Conference on Automated Planning and Scheduling on July 11 in Prague.
The [presentation slides](results/presentation.pdf) of this talk contain additional details.

- Optimal Track Winner SNP: **LNM-Plan** using NLM-CutPlan Orbit
- Optimal Track Winner LNP: **LNM-Plan** using NLM-CutPlan, NLM-CutPlan Orbit
- Optimal Track Winner SNP+LNP: **LNM-Plan** using NLM-CutPlan Orbit
- Satisficing Track Winner SNP: **LNM-Plan** using NLM-CutPlan SAT2
- Satisficing Track Winner LNP: **LNM-Plan** using NLM-CutPlan SAT
- Satisficing Track Winner SNP+LNP: **LNM-Plan** using NLM-CutPlan SAT
- Agile Track Winner SNP: **LNM-Plan** using NLM-CutPlan SAT2
- Agile Track Winner LNP: **LNM-Plan** using NLM-CutPlan SAT
- Agile Track Winner SNP+LNP: **LNM-Plan** using NLM-CutPlan SAT

### Satisficing

<font size="2">
|     |                          | ENHSP hmrp | ENHSP hmrp+ha | ENHSP hmrp+ha+ht | NLM-CutPlan Sat | NLM-CutPlan OC Sat | NLM-CutPlan Sat2 | OMTPlan (Sequential)| OMTPlan (Parallel)|
| --- | ------------------------ | ---------- | ------------- | ---------------- | --------------- | ------------------ | ---------------- | --------------------- | ------------------- |
| SNP | block-grouping           | 19         | 20            | 19               | 0               | 0                  | 0                | 0                     | 2                   |
| SNP | counters                 | 13         | 19            | 20               | 11              | 12                 | 12               | 3                     | 20                  |
| SNP | delivery                 | 13         | 10            | 10               | 7               | 7                  | 6                | 2                     | 2                   |
| SNP | expedition               | 3          | 20            | 20               | 4               | 4                  | 4                | 0                     | 3                   |
| SNP | ext-plant-watering       | 18         | 20            | 20               | 18              | 16                 | 17               | 0                     | 0                   |
| SNP | farmland                 | 20         | 20            | 20               | 9               | 11                 | 11               | 0                     | 0                   |
| SNP | hydropower               | 2          | 0             | 0                | 4               | 9                  | 6                | 1                     | 1                   |
| SNP | markettrader             | 2          | 2             | 2                | 0               | 0                  | 0                | 0                     | 0                   |
| SNP | mprime                   | 13         | 16            | 16               | 10              | 9                  | 13               | 16                    | 11                  |
| SNP | pathwaysmetric           | 1          | 12            | 12               | 2               | 1                  | 1                | 1                     | 3                   |
| SNP | rover                    | 6          | 8             | 8                | 3               | 6                  | 5                | 4                     | 16                  |
| SNP | sailing                  | 20         | 20            | 20               | 8               | 8                  | 9                | 0                     | 0                   |
| SNP | sugar                    | 4          | 20            | 18               | 5               | 5                  | 4                | 15                    | 19                  |
| LNP | settlers/settlersnumeric | 1          | 4             | 3                | 2               | 0                  | 0                | 0                     | 0                   |
| LNP | fo_counters              | 4          | 20            | 20               | 4               | 0                  | 0                | 4                     | 3                   |
| LNP | fo-farmland              | 9          | 13            | 13               | 9               | 0                  | 0                | 1                     | 1                   |
| LNP | fo-sailing               | 0          | 0             | 0                | 14              | 0                  | 0                | 1                     | 1                   |
| LNP | tpp                      | 4          | 4             | 4                | 2               | 0                  | 0                | 4                     | 4                   |
| LNP | drone                    | 19         | 19            | 19               | 15              | 0                  | 0                | 3                     | 3                   |
| LNP | zenotravel               | 20         | 20            | 20               | 9               | 0                  | 0                | 8                     | 11                  |
|     |                          |            |               |                  |                 |                    |                  |                       |                     |
|     | Total                    | 191        | 267           | 264              | 136             | 88                 | 88               | 63                    | 100                 |
|     | SNP                      | 134        | 187           | 185              | 81              | 88                 | 88               | 42                    | 77                  |
|     | LNP                      | 76         | 99            | 98               | 70              | 0                  | 0                | 24                    | 26                  |
</font>

### Optimal

<font size="2">

|     |                    | ENHSP BLIND | ENHSP OPT | NLM-CutPlan | NLM-CutPlan Orbit | NLM-CutPlan OC | NLM-CutPlan OC Orbit | OMTPlan (Sequential)| OMTPlan (Parallel)|
| --- | ------------------ | ----------- | --------- | ----------- | ----------------- | -------------- | -------------------- | --------------------- | ------------------- |
| SNP | block-grouping     | 0           | 2         | 0           | 0                 | 0              | 0                    | 0                     | 1                   |
| SNP | counters           | 3           | 4         | 5           | 4                 | 4              | 5                    | 2                     | 4                   |
| SNP | delivery           | 2           | 2         | 1           | 5                 | 2              | 2                    | 1                     | 1                   |
| SNP | expedition         | 5           | 5         | 6           | 5                 | 6              | 6                    | 0                     | 1                   |
| SNP | ext-plant-watering | 0           | 0         | 0           | 0                 | 0              | 0                    | 0                     | 0                   |
| SNP | farmland           | 4           | 18        | 11          | 13                | 7              | 12                   | 0                     | 0                   |
| SNP | hydropower         | 8           | 8         | 8           | 10                | 11             | 7                    | 1                     | 1                   |
| SNP | markettrader       | 0           | 0         | 0           | 0                 | 0              | 0                    | 0                     | 0                   |
| SNP | mprime             | 4           | 11        | 13          | 14                | 10             | 10                   | 5                     | 6                   |
| SNP | pathwaysmetric     | 0           | 1         | 0           | 1                 | 0              | 0                    | 1                     | 1                   |
| SNP | rover              | 4           | 4         | 3           | 4                 | 2              | 4                    | 4                     | 6                   |
| SNP | sailing            | 0           | 3         | 6           | 7                 | 6              | 6                    | 0                     | 0                   |
| SNP | sugar              | 0           | 6         | 4           | 8                 | 8              | 5                    | 3                     | 1                   |
| LNP | settlersnumeric    | 0           | 0         | 1           | 1                 | 0              | 0                    | 0                     | 0                   |
| LNP | fo_counters        | 4           | 0         | 2           | 3                 | 0              | 0                    | 3                     | 3                   |
| LNP | fo-farmland        | 3           | 0         | 10          | 8                 | 0              | 0                    | 1                     | 1                   |
| LNP | fo-sailing         | 2           | 0         | 7           | 6                 | 0              | 0                    | 1                     | 1                   |
| LNP | tpp                | 2           | 0         | 1           | 2                 | 0              | 0                    | 0                     | 0                   |
| LNP | drone              | 3           | 0         | 5           | 4                 | 0              | 0                    | 2                     | 2                   |
| LNP | zenotravel         | 4           | 0         | 5           | 7                 | 0              | 0                    | 0                     | 0                   |
|     |                    |             |           |             |                   |                |                      |                       |                     |
|     | Total              | 48          | 64        | 88          | 102               | 56             | 57                   | 24                    | 29                  |
|     | SNP                | 30          | 64        | 57          | 71                | 56             | 57                   | 17                    | 22                  |
|     | LNP                | 21          | 0         | 36          | 35                | 0              | 0                    | 9                     | 9                   |
</font>

Note that planners that were not able to process LNP problems have zeroes in the respective cells.

## Domains

The competition tasks can now be found in the following [Github Repository](https://github.com/ipc2023-numeric/ipc2023-dataset).

## Registration

We require that a planner is registered through a team. For this you need to send an e-mail with a subject containing “[Registration for Numeric Tracks]” to jea20@st-andrews.ac.uk. The email must contain:

names of participants,
email contacts,
track (agile/satisficing/optimal),
at least one github account

Based on that, we will create a private repository under the ipc2023-numeric organization and add all participants as users with with write access and participants can both upload their planner there, and then commit to the repository as they wish until the “final planner submission” deadline.

All participants must subscribe to the Google Group. We will announce further details on the submission process there in due time.

To propose a domain for the competition, please contact the organizers (see below).

## Planner submission

The competitors must submit the source code of their planners that will be run by the organizers on the actual competition domains/problems, unknown to the competitors until this time. This way no fine-tuning of the planners will be possible.
We will host repositories of planners ourselves. The repositories will be hosted on Github under the ipc2023-numeric organisation, and they will be kept private until the end of the competition when we make them public, i.e., after the competition is concluded, we plan to make all planners, domains, and all related data accessible from one place.
We require participants to provide self-contained code, with scripts for compilations and running, “compile” and “run”, respectively. The code should be compilable on a fresh installation of Ubuntu 20.04 LTS, and running has to require only three parameters as an input in the following order: the domain file, the problem file, and the name of the file where the last solution found will be saved.
The solution format is the usual IPC solution format, which consists of a list of actions separated by a new line.


## Organizers
 - [Joan Espasa Arxer](https://joanespasa.github.io) (University of St Andrews)
 - [Enrico Scala](https://sites.google.com/view/enricoscalashomepage/) (University of Brescia)

Contact us: [ipc2023-numeric@googlegroups.com](mailto:ipc2023-numeric@googlegroups.com)

