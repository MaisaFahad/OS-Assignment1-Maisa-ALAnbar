# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**

[Process: A heavyweight entity with its own address space,Independent memory space (code, data, heap, stack),Expensive to create and manage,Inter-process communication (IPC) required for communication,Context switching between processes is costly,Processes provide isolation and protection

Thread: A lightweight entity within a process, Shares address space with other threads in the same process,Cheap to create and manage, Direct communication through shared memory,Invented memory, Context switching between threads is fast, Threads provide efficiency and resource sharing 

so we use threads in this assignmentWe because they are lightweight, share the same memory space, and allow for fast context switching, which is exactly what a Round-Robin scheduler needs to work efficiently.]

---

## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**

[In Round-Robin scheduling, if a process does not finish its work within the given Time Quantum it is interrupted, The system saves its current state and the process is moved from the CPU back to the end of the Ready Queue,It must then wait for its turn again while other processes get their chance to run This ensures fairness so that no single process occupies the CPU for too long]

Example from my output:
```
[ ? P5 executing quantum [4000ms]
  ? Quantum progress: [███████████████] 100%
  ? P5 completed quantum 4000ms │ Overall progress: [██████████░░░░░░░░░░] 51%
     Remaining time: 3805ms
  ? P5 yields CPU for context switch
 ? P5 added to ready queue │ Burst time: 7805ms │ Priority: 1

It must then wait for its turn again

 ? P5 executing quantum [3805ms]
  ? Quantum progress: [███████████████] 100%
  ? P5 completed quantum 3805ms │ Overall progress: [████████████████████] 100%
     Remaining time: 0ms
  ? P5 finished execution!]
```

**Explanation of example:**
[P5 illustrates the preemption logic of Round-Robin Since its burst time (7805ms) was larger than the time quantum (4000ms)  it was forced to stop midway and return to the Ready Queue,The output shows a Context Switch occurring as P5 yields the CPU. Finally, P5 was re-scheduled, completed its remaining 3805ms, and successfully finished its execution.]

---

## Question 3: Thread States

**Question**: A thread can be in different states: **New**, **Runnable**, **Running**, **Waiting**, **Terminated**. Walk through these states for one process (P1) from your simulation.

**Your Answer:**

[Write your answer here. For each state, explain when P1 enters that state during the simulation. Use your understanding of the code to trace through the lifecycle.]

1. **New**: [When is P1 in New state?]

2. **Runnable**: [When does P1 become Runnable?]

3. **Running**: [When is P1 Running?]

4. **Waiting**: [When/why would P1 be Waiting?]

5. **Terminated**: [When is P1 Terminated?]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

### Example 2: [Name of application/scenario]

**Description**: 
[Describe the real-world scenario or application]

**Why Round-Robin works well here**: 
[Explain why Round-Robin scheduling is suitable. Consider fairness, responsiveness, predictability, etc.]

---

## Summary

**Key concepts I understood through these questions:**
1. 
2. 
3. 

**Concepts I need to study more:**
1. 
2. 
