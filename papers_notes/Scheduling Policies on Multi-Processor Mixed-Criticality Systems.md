### Scheduling Policies on Multi-Processor Mixed-Criticality Systems
This paper extends the state-of-the-art single-processor mixedcriticality scheduling algorithm EY-VD to multi-processor systems. To begin with, it integrates EY-VD into traditional workload partitioning schemes to get a multiprocessor mixed-criticality scheduling algorithm MC-PEDF (mixed-criticality partitioned earliest deadline first). 
##### MC-PEDF
MC-PEDF is like the first fit Decreasing(FFD) in Bin-Packing.
Let's see this example.
| job | C(LO) | C(HI) | Criticality | Period/Deadline |
|-----|-------|-------|-------------|-----------------|
| t1  | 4     | 5     | HI          | 10              |
| t2  | 4     | 5     | HI          | 10              |
| t3  | 1     | 1     | LO          | 3               |
| t4  | 1     | 1     | LO          | 3               |
| t5  | 1     | 1     | LO          | 3               |
| t6  | 0.5     | 0.5     | LO          | 4               |

So, in this example, there are two processors p1, p2. When we choose FFD, t1, t2 will be assigned to p1. t3, t4 and t5 will be assigned to p2. And t6 cannot be assigned to p1 or p2 because of the utilization. But when the criticality changed to HI, the p1's utilization still be 80%, p2's utilization is 0%. Which make p2 inefficient in different criticality level.

##### OCOP
The rules for OCOP:
1. † = LO when system inits.
2. When system's criticality changes, OCOP allows task transfer between processors to balance the task utilization among all processors.
3. Task cannot be transfered during the general mode.


I think there are two cases here:
1. † from LO to HI: like the rules said, assign the HI tasks to processors. Which is easy to implement, like communication between processors. Let another processor to run the task sequentially.
2. † from HI to LO: in this paper, the HI tasks will be assigned to the same processor according to first fit. I think may be we can keep the current task allocation, but it is inconsistent.
