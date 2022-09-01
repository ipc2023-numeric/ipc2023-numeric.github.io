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
| Domain submission deadline              | 9th December 2022 |
| Demo problems provided                  | December 2022 |
| Planner submission opens                | January 2023 |
| Planner submission closes               | March 2023  |
| Planner Abstract submission deadline    | May 2023 |
| Contest run                             | May-June 2023 |
| Results announced                       | July 2023 |
| Result analysis deadline                | August 2023 |


## Tracks

### Satisficing Track

 - single CPU core
 - 8Gb memory limit
 - 30min time limit
 - Multiple plans can be returned, the one with the lowest cost is counted.
 - The score of a planner on a solved task is the ratio C\*/C where C is the
   cost of the cheapest discovered plan and C\* is the cost of a reference plan. The score on an unsolved task is 0. The score of a planner is the sum of its scores for all tasks.
 - If an invalid plan is returned, all tasks in the domain are counted as unsolved.
 - If that happens in more than one domain, the entry is disqualified.

Agile Track

 - single CPU core
 - 8Gb memory limit
 - 5min time limit
 - The cost of the discovered plan is ignored, only the CPU time to discover a plan is counted.
 - The score of a planner on a solved task is 1 if the task was solved within 1 second and 0 if the task was not solved within the resource limits. If the task was solved in T seconds (1 ≤ T ≤ 300) then its score is 1 - log(T)/log(300). The score of a planner is the sum of its scores for all tasks.
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


