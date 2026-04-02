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

1. **New**: [P1 is in this state when the Process object is created but thread.start() has not been called yet]

2. **Runnable**: [P1 enters this state as soon as we call start() ,It is ready to run and is waiting in the Ready Queue for the CPU to become available]

3. **Running**: [P1 is in this state when the CPU picks it from the queue and it starts executing its run() method]

4. **Waiting**: [P1 enters a waiting state when we use Thread.sleep() to simulate processing time, or when the main thread uses join() to wait for P1 to finish its turn]

5. **Terminated**: [P1 reaches this state once its remainingTime reaches 0 and the run() method finishes execution,It is then removed from the system]

---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1: [Multi-tab Web Browsers like (Chrome or Firefox)]

**Description**: 
[When you have multiple tabs open in a browser, each tab often runs its own set of threads to render the page, execute JavaScript, or play a video.]

**Why Round-Robin works well here**: 
[It provides Responsiveness. If one tab is trying to load a very "heavy" website, Round-Robin ensures that the CPU doesn't get stuck on that one tab. By giving each tab a small Time Quantum, the browser allows you to click on a different tab or scroll through a simpler page without the whole application freezing. It keeps the user experience smooth across all open tasks.]

### Example 2: [Multi-User Access to a Cloud Server like (Google Docs)]

**Description**: 
[When multiple people are editing the same document or different documents on a cloud server at the same time, the server receives hundreds of "edit" requests every second.]

**Why Round-Robin works well here**: 
[It provides Fairness and Parallelism. If one user is pasting a huge amount of text (a heavy task) and another user is just typing a single letter (a light task), Round-Robin ensures the server doesn't get stuck processing the big task first. By giving each user's request a small Time Quantum, everyone sees their changes appear on the screen almost instantly.]

---

## Summary

**Key concepts I understood through these questions:**
1. Thread Lifecycle and States: I now understand how a process moves from being New to Runnable, and how it cycles between Running and Waiting based on the scheduler's decisions before finally reaching the Terminated state.
   
   2. Preemption and Fairness in Round-Robin: I learned that the Time Quantum is the heart of fairness; it ensures that no single "heavy" process can hog the CPU, by forcing it to yield and return to the Ready Queue if it doesn't finish in time

 3. Efficiency of Threads vs. Processes: I understood that Threads are "lightweight" because they share the same memory space, which makes Context Switching much faster and more efficient for simulating a high-speed CPU scheduler compared to using independent processes.

**Concepts I need to study more:**
1. Thread Synchronization and Race Conditions
2. Advanced Scheduling Algorithms
