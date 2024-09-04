## What is deadlock and how to avoid it? 
A deadlock is a situation in computing where two or more processes are unable to proceed because each is waiting for the other to release a resource. This can lead to a standstill where none of the processes can continue execution, effectively freezing the system.
### Conditions for Deadlock
Deadlocks typically occur when the following four conditions are met simultaneously:
1. **Mutual Exclusion**: At least one resource must be held in a non-shareable mode.
2. **Hold and Wait**: A process holding at least one resource is waiting to acquire additional resources that are currently being held by other processes.
3. **No Preemption**: Resources cannot be forcibly taken from a process; they must be voluntarily released.
4. **Circular Wait**: There exists a set of processes such that each process is waiting for a resource held by the next process in the cycle.
### Strategies to Avoid Deadlock
1. **Resource Allocation Graph**: Use a graph to represent the allocation of resources to processes. If a cycle is detected, it indicates a potential deadlock.

2. **Banker's Algorithm**: This algorithm checks whether resource allocation will leave the system in a safe state. If it does, resources are allocated; if not, the process must wait.

3. **Avoid Hold and Wait**: Require processes to request all the resources they need at once, preventing them from holding onto resources while waiting for others.

4. **Preemption**: Allow the system to forcibly take resources from processes if necessary, ensuring that no process holds onto resources indefinitely.

5. **Circular Wait Prevention**: Impose an ordering on resource types and require processes to request resources in a specific order, preventing circular wait conditions.

