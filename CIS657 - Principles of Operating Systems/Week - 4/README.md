# Semaphores and Process Management Cont.
## Process Suspension
This is the temporary stopping of a process and allows for process resumption at a later time. The process table entry is retained and the complete state of computation is saved. The OS sets the process table entry to indicate when a process is suspended.

In Xinu, the _current_ or _ready_ process can be suspended and only suspended processes can be resumed. The __system__ calls suspend() and resume(). Xinu must follow this state transition for suspension. 
** Everytime we kick a current process out of the ready state, we must call resched() to make the processor run the idle process. 
** Everytime we call create(), the created process is in a suspended state. 

## Process Resumption
This is the continuation of the execution of a previously suspended process. Essentially makes the process eligible for the process and re-establish scheduling invariant. 

## Process Termination
This is a permanent termination of a process (using kill() in Xinu) and the process table entry becomes available for reuse.   

## Process Creation
This refers to the starting of a new process (using create() in Xinu). This create() method in Xinu finds a free entry in process table, fills in the entry, and then places a new process in the suspended state.

## Coordination of Concurrent Processes
Concurrent processes often have to access shared data and non-atomic (non-linear execution) operations can produce unexpected results.

### Semaphores
In Xinu, wait() function is called on the current process, sets it state to waiting, then enqueues the process into the semaphore queue and call resched() to make sure the CPU is doing something useful (running null process). When the semaphore value is < 0, the signal() function calls ready() on the PID returned from the dequeue() function on the process in the semaphore queue. 
