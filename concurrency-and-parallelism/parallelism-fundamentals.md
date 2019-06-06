# Parallelism
__Job__ – a single step of a program execution consisting of sequential computations

## Computational graph (CG)
The execution of a parallel program can be modeled by a CG in which:
* Vertices (nodes) – the jobs
* Directed edges – the job ordering constraints

__Data race__ occurs when there's at least two disconnected nodes (no path from one to another in any valid direction) accessing shared data with at least one of them mutating that data

It is possible to reason about the speed of a parallel algorithm by assigning execution times to the nodes. In a graph G:
* __*work*(G)__ – the sum of execution times of all nodes
* __*span*(G)__ – the longest path in G (a.k.a. the critical path ⇒ span is a critical path length – *CPL*(G))
* __ideal parallelism__ – *work*(G) / *span*(G)

## Scheduling
__Forced Idleness__ – a state in which one job has to wait for the completion of another: *A → B*, B can't execute until *A* is completed

__Unforced Idleness__ – a CG node is available to be scheduled on a machine, but machine remains idle

__Legal schedule__ – a schedule in which for every directed edge *A → B*, the schedule guarantees that job *B* is only scheduled after job *A* completes

__Greedy Schedule__ – a schedule that restricts unforced idleness
