# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Nedaa Abdul Alhaq-Alaraby] |
| **Student ID** | [446052622] |
| **University Email** | 446052622@std.psau.edu.sa |
| **GitHub Username** | [Nedaa AbdulAlhaq] |
| **Repository Link** | [https://github.com/NedaaAbdulAlhaq/OS-Assignment3-Nedaa-Alaraby] |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 6, 2026 at 1:30 AM]
**What I did**:
Started Assignment 3, opened the project in VS Code, and ran the original code before making any changes.

**Details**:
I opened the project in VS Code and checked that my student ID was correctly added in SchedulerSimulationSync.java. After that, I created a commit for updating my student ID as required before starting the assignment. I then ran the original starter code before making any modifications. During execution, I noticed that more than one CPU selected the same process, and the program produced an IllegalThreadStateException. I saved the output because I will need it later when answering the technical questions.

**Challenges**:
I did not understand why the same process was selected by multiple CPUs.

**Solution**:
I reviewed the code comments and learned that the problem was caused by a race condition in the ready queue.

**Time spent**:
30 minutes
---

### Entry 2 - [November 6, 2026 at 2:00 AM]
**What I did**:
Worked on Feature 1 and learned how to use ReentrantLock.
**Details**:

I read the ReadyQueue class and identified the methods that access shared data. I learned how lock(), unlock(), and try/finally work. After understanding the problem, I added queueLock and protected the methods add(), poll(), processOf(), and snapshot().

**Challenges**:
I was confused about where to place the lock and why finally is required.

**Solution**:
I learned that finally guarantees that the lock will always be released, even if an error occurs. 

**Time spent**:
1 hour 
---

### Entry 3 - [November 15, 2026 at 9:00 PM]
**What I did**:
Implemented Feature 2 and protected the shared statistics variables. 

**Details**:
I added a ReentrantLock in the Shared Stats class. Then I updated the methods that modify contextSwitchCount, completedProcessCount, and totalServiceTime by using lock() and unlock(). I also protected the methods that read these values. After running the program, the verification block showed that all statistics values matched the expected results.

**Challenges**:
At first, I did not fully understand why the read methods also needed a lock.

**Solution**:
 I learned that shared data should be protected when reading and writing because another thread may change the value at the same time. After protecting both operations, the results became consistent.

**Time spent**:
1 hour 54 minutes
---

### Entry 4 - [November 16, 2026 at 10:30 PM]
**What I did**:
Implemented Feature 3 using a counting semaphore.
**Details**:
I added a Semaphore to the ReadyQueue class and initialized it with 0. Then I used release() when a process is added to the ready queue and acquire() before polling a process. After that, I tested the program multiple times to make sure busy waiting was removed. I also added the shutdown logic so blocked CPUs can wake up and terminate after all processes finish.

**Challenges**:
was confu
sed about how the CPUs should stop after the last process finished. At one point, I got a NullPointerException while testing the shutdown logic.

**Solution**:
I reviewed the semaphore flow and adjusted the shutdown logic until the program finished correctly. After testing several runs, the verification block showed all checks passing and Busy-waiting polls became 0.

**Time spent**:
1 hour 20 minutes
---

### Entry 5 - [November 16, 2026 at 7:00 PM]
**What I did**:
Reviewed the final solution, tested the program, and completed the assignment documentation.

**Details**:
I ran the program several times to verify that there were no exceptions and no watchdog  messages. I checked that all four verification lines showed correct results and that the program terminated normally. I also reviewed my commits and started completing MY_WORK.md.

**Challenges**:
I wanted to make sure that the final output was correct and consistent in every run.

**Solution**:
I repeated the tests multiple times and compared the verification results. After confirming that all values matched the expected values, I completed the remaining documentation.

**Time spent**:
1 hour 
---

### Entry 6 - [Optional - Date and Time]
**What I did**:
Prepared and recorded the assignment video presentation.

**Details**:
I reviewed my repository, commits, and MY_WORK.md before recording. During the video, I explained the three implemented features and showed the final program output. I also demonstrated that the verification block passed successfully and that the program terminated normally without any errors. After recording, I uploaded the video and added the link to MY_WORK.md. 

**Challenges**:
I was worried about the video requirements and making sure I did not forget any important part while recording.

**Solution**:
I checked the README and final checklist to make sure everything was completed before recording the video.

**Time spent**:
40 minutes
---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [6 hours 24 minutes
]

**Most challenging part**:

Understanding the semaphore logic and the shutdown process in Feature 3.


**Most interesting learning**:

Learning how race conditions happen and how locks and semaphores prevent synchronization problems.

**What I would do differently next time**:

I would start the documentation earlier and test each feature immediately after finishing it.

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

Before this assignment, I knew the basic idea of threads but I did not really understand how race conditions happen. After running the starter code, I saw that shared data can become incorrect when multiple CPUs access it at the same time. I learned how ReentrantLock is used to protect critical sections and why unlock() should be placed inside a finally block. I also learned that shared variables need protection during both reading and writing. Another thing I learned was how a semaphore can be used to block threads instead of making them repeatedly check the queue. The most surprising part for me was seeing how a very small timing difference between threads could cause errors or incorrect results.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part for me was Feature 3 and understanding the semaphore logic. At first, I understood where to place acquire() and release(), but I was confused about how the CPUs should stop after all processes finished. During testing, I got different outputs and at one point I got a NullPointerException while working on the shutdown logic. It took some time to understand why blocked CPUs needed a wake-up signal at the end. I spent a lot of time testing and checking the output. After I understood the shutdown process, the feature became much clearer.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I solved most of the challenges by working on one feature at a time and testing after each change. When something did not work, I went back to the README and read the feature requirements again. I also checked the program output carefully to understand where the problem was happening. Running the program several times helped me confirm whether the issue was fixed or not. Instead of changing many things at once, I made small changes and tested them. This made it easier to find mistakes and understand the behavior of the program.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is important in many real-world systems where multiple users or threads access the same data. For example, in online banking, locks can prevent two operations from changing the same account balance at the same time. Ticket booking systems also need synchronization so that the same seat is not sold to more than one customer. Another example is a print queue where several users send print jobs to the same printer. Databases also use synchronization techniques to keep data consistent when many users access it together. This assignment helped me understand why these protections are necessary in real applications.

### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In my original starter run, the simulation failed because multiple CPUs selected the same process at the same time. For example, CPU-1, CPU-2, and CPU-3 all picked P1, which resulted in an IllegalThreadStateException and incorrect statistics. The verification block showed several mismatches, including context switches, completed processes, total service time, and busy-waiting polls. This happened because the ready queue was not protected by a lock, allowing multiple threads to access the same process concurrently. Similar race conditions can happen on real systems because thread scheduling is unpredictable, which makes these bugs difficult to reproduce and debug.

Verification block of the **original starter**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
Context switches (quanta executed)     expected 34       observed 29       ✖ MISMATCH
Completed processes                    expected 19       observed 17       ✖ MISMATCH
Total service time (ms)                expected 52197    observed 43451    ✖ MISMATCH
Busy-waiting polls (must be 0)         expected 0        observed 794      ✖ MISMATCH
✖ At least one check failed (see the ✖ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
Context switches (quanta executed)     expected 34       observed 34
Completed processes                    expected 19       observed 19
Total service time (ms)                expected 52197    observed 52197
Busy-waiting polls (must be 0)         expected 0        observed 0
✔ All shared values are consistent.

```

**Explanation of the timeline:**

CPU-1 reads the first process (P1) from the ready queue. Before CPU-1 removes it, RaceWindow.pause() allows another thread to run. CPU-2 also reads P1 and believes it is available. Then CPU-3 reads the same process as well. As a result, all three CPUs try to execute P1, which causes an IllegalThreadStateException and corrupts the shared statistics. After adding queueLock, only one CPU can access the critical section at a time, preventing this race condition.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I protected the shared ready queue and the shared statistics because they are accessed by multiple threads at the same time. For the ready queue, I used queueLock to protect add(), poll(), processOf(), and snapshot(). For the statistics, I used one lock called statsLocks for contextSwitchCount, completedProcessCount, and totalServiceTime. I chose one lock because it was simpler to implement and manage. The ready queue uses a different lock because it is a separate shared resource.


| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [ `ReadyQueue.add()`] | [queueLock ] | [Shared queue access] |
|[ `ReadyQueue.poll()`] | [queueLock ] |[Prevent race conditions] |
[ `ReadyQueue.processOf()`] | [queueLock ] | [Shared map access] |
[ `ReadyQueue.snapshot()`] | [queueLock ] | [Prevent concurrent modification] |
[ `contextSwitchCount`] | [statsLocks ] | [Prevent lost updates] |
[ `completedProcessCount`] | [ statsLocks ] | [Keep completed process count correct] |
[ `totalServiceTime`] | [ statsLocks ] | [Protect shared accumulator] |


## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the starter code, CPUs kept checking the queue repeatedly when it became empty. This is called busy waiting because the CPUs continue checking instead of sleeping. In my solution, the semaphore value represents the number of available processes in the ready queue. The initial value is 0 because no process is available before processes are added. After the initial add() operations, the semaphore value becomes equal to the number of processes in the queue. The last CPU calls release(SharedStats.totalCPUs) so blocked CPUs can wake up and terminate correctly.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
This problem is similar to the Producer-Consumer synchronization problem. The ready queue acts as the shared buffer between threads. CPUs consume processes by removing them from the queue and can also produce by adding unfinished processes back to the queue. A bounded queue would require additional synchronization to manage available slots and ready processes. Proper ordering of locks and semaphores is important to avoid deadlocks.

**Classical problem and roles**:
Producer-Consumer problem.
The CPUs act as consumers when removing processes from the ready queue and also act as producers when re-enqueuing unfinished processes after a quantum expires.


**Semaphores for a bounded queue (name and initial value)**:
empty = K
full = 0
mutex = 1

**Deadlock scenario and prevention**:
A deadlock could occur if a thread acquires the mutex and then waits on a semaphore while still holding the mutex. Another thread would need the same mutex to continue, but it would be blocked from acquiring it. As a result, both threads may wait forever. To prevent this, the hold-and-wait condition should be broken by not waiting for a resource while holding another resource.

## Summary

**Key concepts I understood through these questions:**
1.Race conditions
2.ReentrantLock and mutual exclusion
3.Semaphores and busy waiting

**Concepts I need to study more:**
1.Deadlock prevention
2.Advanced synchronization techniques

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
