# Assignment Questions

## Instructions
Answer all 4 questions with detailed explanations. Each answer should be **3-5 sentences minimum** and demonstrate your understanding of the concepts.

---

## Question 1: Thread vs Process

**Question**: Explain the difference between a **thread** and a **process**. Why did we use threads in this assignment instead of creating separate processes?

**Your Answer:**
A process is an independent program that has its own memory and resources, while a thread is a smaller unit inside a process and shares the same memory with other threads.

We used threads in this assignment instead of processes because threads are faster and use fewer resources. Since threads share memory, communication between them is easier and quicker compared to processes.

One difference is memory sharing, where threads share the same memory but processes do not. Another difference is creation overhead, as creating a process takes more time and system resources compared to creating a thread.

In SchedulerSimulation.java, threads are used to simulate multiple processes running at the same time, which helps demonstrate how CPU scheduling works in a more efficient way.


## Question 2: Ready Queue Behavior

**Question**: In Round-Robin scheduling, what happens when a process doesn't finish within its time quantum? Explain using an example from your program output.

**Your Answer:**
In Round-Robin scheduling, if a process does not finish within its time quantum, it is removed from the CPU and placed back at the end of the ready queue. This allows other processes to get a chance to run.

For example, in the program output, a process like P1 may run for a short time and then be re-queued if it still has remaining burst time. Later, it will get another turn to continue execution.

This re-queuing behavior is important for fairness because it ensures that all processes get equal CPU time. No single process can use the CPU for too long, which prevents starvation and keeps the system balanced.

Example from my output:

P1 completed quantum 4000ms
Remaining time: 4919ms
P1 yields CPU for context switch
P1 added to ready queue
Ready Queue: [P3 P4 P5 P6 P7 P8 P9 P10 P1]


**Explanation of example:**
The output shows that process P1 executed for its time quantum (4000ms), but it did not finish because it still has remaining time. After that, P1 yields the CPU, which means it stops running and allows another process to use the CPU.

Then, P1 is added back to the ready queue, which means it will wait for its next turn to run again. In the ready queue, we can see that P1 is placed at the end of the queue after other processes.

This behavior shows how Round-Robin scheduling works, where each process gets a fair share of CPU time and no process can run continuously without giving others a chance.
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


New: P1 is in New state after new Thread(process) is called in addProcessToQueue(), creating the thread object before it starts.

Runnable: P1 becomes Runnable when currentThread.start() is called in the main scheduling loop, making it ready for CPU execution.

Running: P1 is Running when the OS scheduler selects it and begins executing the run() method, calculating runtime and processing its quantum.

Waiting: P1 enters Timed-Waiting when Thread.sleep(stepTime) is called during execution to simulate work progress; the main thread also waits via currentThread.join() for P1 to complete.

Terminated: P1 is Terminated when the run() method returns normally after completing its quantum or finishing entirely via runToCompletion().
---

## Question 4: Real-World Applications

**Question**: Give **TWO** real-world examples where Round-Robin scheduling with threads would be useful. Explain why this scheduling algorithm works well for those scenarios.

**Your Answer:**

### Example 1:  Web server

**Description**: 
When many users access a website at the same time, the server handles each request as a separate thread.

**Why Round-Robin works well here**: 
Round Robin gives each request a small amount of CPU time instead of letting one request take everything. This makes the system more responsive and all users get served fairly.

### Example 2: Running programs on a computer

**Description**: 
When you open multiple programs like a browser and music player, each one needs CPU time to run.

**Why Round-Robin works well here**: 
Round Robin lets each program run for a short time in turns, so the system stays smooth and responsive. No single program takes all the CPU.

---

## Summary

**Key concepts I understood through these questions:**
1.I understood the difference between threads and processes, especially how threads share memory and are faster to create. 
2.I learned how Round-Robin scheduling works and how processes are re-added to the ready queue if they don’t finish.
3.I understood the lifecycle of a thread and how it moves between states during execution.


**Concepts I need to study more:**
1. I still need more practice understanding synchronization between threads. 
2. I want to learn more about advanced scheduling algorithms and how they compare to Round-Robin.

