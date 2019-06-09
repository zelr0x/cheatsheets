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

__Parallel speedup__ – ratio showing how much faster a parallel version with given number of processors runs compared to a serial version for the same schedule

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{100}&space;\large&space;T_{\infty}&space;=&space;span(G)" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{100}&space;\large&space;T_{\infty}&space;=&space;span(G)" title="\large T_{\infty} = span(G)" /></a> – execution time of a CG on infinite number of processors

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{100}&space;\large&space;T_{1}&space;=&space;work(G)" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{100}&space;\large&space;T_{1}&space;=&space;work(G)" title="\large T_{1} = work(G)" /></a> – execution time of a CG on one processor

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{100}&space;\large&space;T_{P}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{100}&space;\large&space;T_{P}" title="\large T_{P}" /></a> – execution time of a CG on P processors

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{100}&space;\large&space;T_{\infty}&space;\leq&space;T_{P}&space;\leq&space;T_{1}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{100}&space;\large&space;T_{\infty}&space;\leq&space;T_{P}&space;\leq&space;T_{1}" title="\large T_{\infty} \leq T_{P} \leq T_{1}" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=\inline&space;\dpi{100}&space;\large&space;Speedup(P)&space;=&space;\frac{T_{1}}{T_{P}}" target="_blank"><img src="https://latex.codecogs.com/svg.latex?\inline&space;\dpi{100}&space;\large&space;Speedup(P)&space;=&space;\frac{T_{1}}{T_{P}}" title="\large Speedup(P) = \frac{T_{1}}{T_{P}}" /></a>
