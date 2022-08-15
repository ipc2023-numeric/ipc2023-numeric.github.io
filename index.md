---
layout: default
title: International Planning Competition 2023 - Numerical Tracks
---

# International Planning Competition 2023 - Numerical Tracks

This is the website for the numerical tracks of the [IPC 2023](https://ipc2023.github.io).


## Calls
Please forward the following calls to all interested parties.

 - [Call for Domains](calls/ipc2023-call-for-domains.txt)


## Preliminary Schedule

| Event                                   | Date |
|:----------------------------------------|:-----|
| Call for domains                        | TBA  |
| Call for participation                  | TBA  |
| Domain expression of interest deadline  | TBA  |
| Domain submission deadline              | TBA  |
| Demo problems provided                  | TBA  |
| Initial planner submission              | TBA  |
| Feature stop (final planner submission) | TBA  |
| Planner Abstract submission deadline    | TBA  |
| Contest run                             | TBA  |
| Results announced                       | TBA  |
| Result analysis deadline                | TBA  |


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
 - The score of a planner on a solved task is the ratio C\*/C where C is the
   cost of the cheapest discovered plan and C\* is the cost of a reference plan. The score on an unsolved task is 0. The score of a planner is the sum of its scores for all tasks.
 - If an invalid plan is returned, all tasks in the domain are counted as unsolved.
 - If that happens in more than one domain, the entry is disqualified.

## PDDL Fragment
TBA

## Registration
Comming soon

## Organizers
 - [Joan Espasa Arxer](https://joanespasa.github.io) (University of St Andrews)
 - [Enrico Scala](https://sites.google.com/view/enricoscalashomepage/) (University of Brescia)

Contact us: [ipc2023-numerical@googlegroups.com](ipc2023-numerical@googlegroups.com)


