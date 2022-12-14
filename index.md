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
| Demo problems provided                  | December 2022 |
| Planner submission opens                | January 2023 |
| Planner submission closes               | March 2023  |
| Planner Abstract submission deadline    | May 2023 |
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
- The score of a planner on a solved task is the ratio C*/C where C is the cost of the cheapest discovered plan and C* is the cost of a reference plan. The score on an unsolved task is 0. The score of a planner is the sum of its scores for all tasks.
- If an invalid plan is returned, all tasks in the domain are counted as unsolved.
- If that happens in more than one domain, the entry is disqualified.

### Agile Track

- single CPU core
- 8Gb memory limit
- 5min time limit
- The cost of the discovered plan is ignored, only the CPU time to discover a plan is counted.
- The score of a planner on a solved task is 1 if the task was solved within 1 second and 0 if the task was not solved within the resource limits. If the task was solved in T seconds (1 ??? T ??? 300) then its score is 1 - log(T)/log(300). The score of a planner is the sum of its scores for all tasks.
- If an invalid plan is returned, all tasks in the domain are counted as unsolved.
- If that happens in more than one domain, the entry is disqualified.

## PDDL Fragment

We will use a subset of PDDL 2.1, considering two fragments:
- Simple Numeric Planning (SNP): Numeric variables can only be increased or decreased by a constant using the increase and decrease operations.
- Linear Numeric Planning (LNP): In addition to SNP, numeric variables can now be also assigned directly using the assign operator and the right-hand of an effect can now be a linear combination.

Preconditions and goals are arbitrary propositional formulas. That is, they include quantifiers, negative preconditions, disjunctive preconditions and any number of numeric predicates. Conditional effects are not considered. Terms can either be literals as in classical planning, or numeric terms of the form f(X){ >=,>, =} 0 where f(X) is a linear expressions. Each domain of  the competition will be either a SNP or a LNP (LNP is more expressive than SNP).
Planners supporting only SNP will be accepted and their performance will be reported when compared with respect to only SNP problems. A planner can also only support SNP. We are considering to have separate rankings.

In terms of the optimisation track, the optimisation functions will always be a minimisation. Problems will either be a minimisation of action costs, or a metric function that is a weighted sum with positive coefficients where each involved variable can only be increased by the actions.

Sample problems will be posted soon

## Registration

Comming soon

## Organizers
 - [Joan Espasa Arxer](https://joanespasa.github.io) (University of St Andrews)
 - [Enrico Scala](https://sites.google.com/view/enricoscalashomepage/) (University of Brescia)

Contact us: [ipc2023-numeric@googlegroups.com](mailto:ipc2023-numeric@googlegroups.com)

