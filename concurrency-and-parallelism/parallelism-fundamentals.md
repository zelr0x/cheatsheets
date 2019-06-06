## Computational graph (CG)
The execution of a parallel program can be modeled by a CG in which:
* Vertices (nodes) – the steps of the program consisting of sequential a computation
* Directed edges – the ordering constraints for the steps

__Data race__ occurs when there's at least two disconnected nodes (no path from one to another in any direction) accessing shared data with at least one of them mutating that data.

It is possible to reason about the speed of a parallel algorithm by assigning execution times to the nodes. In a graph G:
* work(G) – the sum of execution times of all nodes
* span(G) – the longest path in G (a.k.a. the critical path => span is a CPL (critical path length) of G)
