# Development Log

## Instructions
Document your development process as you work on the assignment. Add entries showing:
- What you worked on
- Problems you encountered
- How you solved them
- Time spent

**Requirements**: Minimum 5 entries showing progression over time.

---

## Example Entry Format:

### Entry 1 - [April 1, 2026, 2:30 PM]
**What I did**: Forked the repository and set up my student ID

**Details**: 
- Created GitHub account with university email
- Forked the starter repository
- Changed student ID on line 92 to my actual ID (441234567)
- Compiled and ran the program successfully

**Challenges**: Had to install JDK first because javac wasn't recognized

**Solution**: Downloaded JDK 17 from Oracle website and set PATH variable

**Time spent**: 30 minutes

---

## Your Development Log:

### Entry 1 - [March 12th, 2026 7:18 AM]
**What I did**: 
Forked a starter repository from GitHub and set my student ID 
**Details**: 

- created an account in GitHub with university email
-  Renamed my Repository with  my username and made it public
-  Forked the starter repository
-  Changed student ID on line 192  to my actual ID (445052201)
-  commit changes
**Challenges**: 
Learning on GitHub and using it for editing
**Solution**: 
Follow the instruction written in the assignment and watch some videos
**Time spent**: 
45 minutes
---

### Entry 2 - [March 23rd, 2026 8:46 AM]
**What I did**: Add Feature 1 : add process priority

**Details**: 
-  Add a priority field to the Process class
-  in SchedulerSimulation class in main methode Generate random priorities when creating processes (integer 1-5)
-    Display priority when a process enters the ready queue
-    commit changes

**Challenges**: Generate random priorities with value from 1 to 5 only

**Solution**: ask chatGPT to explain this for me  

**Time spent**: 20 minutes

---

### Entry 3 - [march 27th,2026 2:17 AM]
**What I did**: implemented context switch counter (feature 2)

**Details**: 
- in SchedulerSimulation class Add a static counter variable for context switches outside main method
- Increment the counter each time a new process starts running
-  Display total context switches
-  commit changes

**Challenges**: choose the right place to adding the  counter in code 

**Solution**: search where the processes start runing

**Time spent**:  30 minutes
---

### Entry 4 - [March 31st, 2026 1:06 AM ]
**What I did**: Feature 3: Track Waiting Time 

**Details**:
- Add fields to track
- Calculate waiting time for each process
-  Display a summary table showing: Process Name, Burst Time, Waiting
Time
-commit changes

**Challenges**: 
display summary table showing: Process Name, Burst Time, Waiting
Time for each processes+ calculate average time 
**Solution**: 
thinking of solutions and asking external assistance
**Time spent**: 24 hours 

---

### Entry 5 - [March 31st ,2026 12:30]
**What I did**: updateWaitingTime() method
In the Round Robin algorithm the process does not end all at once, but enters and exits the queue several times ,The function of this is to calculate the total waiting time of the process while it is in the queue each time it returns to the queue.
**Details**: 
-using lastReadyTime feild and currentTime local feild in process class to calculate totalWaitingTime
_ like this ->    long currentTime=System.currentTimeMillis();
       long waitTime=(currentTime - lastReadyTime); // time spent waiting since last added to ready queue
        totalWaitingTime+= waitTime;

**Challenges**: choose the right place to adding the method in code 

**Solution**: Called in the main method after dequeuing the process and before starting its thread

**Time spent**: 
15 minutes
---

### Entry 6 - [Optional - Date and Time]
**What I did**: 

**Details**: 

**Challenges**: 

**Solution**: 

**Time spent**: 

---

## Summary

**Total time spent on assignment**: [ 26 hours]

**Most challenging part**: Feature 3

**Most interesting learning**: I learned how the CPU scheduler manages multiple processes using threads It was interesting to see how the Time Quantum works in practice forcing a process to leave the CPU and return to the 'Ready Queue'

**What I would do differently next time**: 
In the future I want to compare Round Robin with other algorithms like First-Come, First-Served (FCFS) to see which one is more efficient for different types of tasks and I would also like to improve the Priority feature so that higher-priority processes can jump to the front of the queue.
