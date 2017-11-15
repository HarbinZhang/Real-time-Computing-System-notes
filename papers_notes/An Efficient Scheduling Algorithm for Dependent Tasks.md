### An Efficient Scheduling Algorithm for Dependent Tasks
This paper propose a greedy algorithm that can generate a shorter schedule than other major algorithms.
The time complexity of our algorithm is O(dv^2logv) , where v represents the number of tasks and d represents the maximum indegree of tasks.
##### Basic idea
We assume that a parallel program can be expressed as a directed acyclic graph(DAG) G=(V, E, w, c), where V is the set of tasks and E is the set of edges. The size of task ni is w(ni). An edge from ni to task nj is expressed as e(ni, nj) and size of the edge is expressed as c(ni, nj). Given task ni, est(ni) and ect(ni) represent the earliest start time and completion time of ni respectively.

1. Given task na, est(na) and C(na) are determined according to its parent tasks. If task na has a single parent task ni, then C(na) should be C(ni) U {na}.
2. If task na has s parent task n1, n2, …, ns, we should follow this rule:
- The objective of merge operation is to merge tasks of parent clusters of na as little as possible.

