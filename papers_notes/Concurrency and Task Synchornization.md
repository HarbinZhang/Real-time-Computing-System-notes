### Concurrency and Task Synchronization
##### Mutual Exclusion
This paper provides three solutions to achieve mutual exclusion:
1. Make the operation "indivisible" by disabling interrupts during the critical section.
2. Reduce the critical code section to a single indivisible machine instruction.
3. Use a monitor to ensure only one process at a time is attempting to execute a critical section related to a particular shared resource.

And explain how these three ways implemented.
##### Deadlock
Four prerequisites:
1. Mutual exclusion.
2. Non-preemptive scheduling.
3. Partial allocation.
Processes can acquire needed resources one at a time. 
4. Circular waiting.
##### 1. Avoiding partial allocation
The way provided here is we can divide the resources into several parts. Which may reduces speed.
##### 2. Ordered Allocation
Or we can simply force partial allocations to occur in a specific sequence. 
##### My gains or viewpoints.
How to achieve mutual exclusion can be simply divided into two basic parts:
1. Moniter
2. Self-control

Self-control such as make the operation "indivisible" is hard to implement, upgrade, but it can get high efficiency. 
Moniter is not that sophistiated but appropriate for many cases. There are many mutual helper structure such as semaphore, wait, signal. It may be slower than self-control in switching threads, but I think it is a better way to achieve mutual exclusion in most cases.
