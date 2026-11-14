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
| **Full Name** | [Mohammed Abdullah Alsoheimi] |
| **Student ID** | [445050126] |
| **University Email** | 445050126@std.psau.edu.sa |
| **GitHub Username** | [Mohammed0Alsoheimi] |
| **Repository Link** | https://github.com/Mohammed0Alsoheimi?tab=repositories |
 
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

### Entry 1 - [November 13, 2026, 10:00 PM]
**What I did**:
I executed the initial starter code after forking the repository and setting my student ID.
**Details**:
I ran the starter code after forking and renaming the assignment repository and adding my student ID (445050126) to line 304 in SchedulerSimulationSync.java. noticed that several CPUs selected the same process, which resulted in watchdog termination and exceptions since synchronization was lacking.
**Challenges**:
recognizing the reasons of the interference between several CPU threads when reading the ready queue.
**Solution**:
Examine the assignment guidelines again and note any instances of race in unprotected shared structures.
**Time spent**:
45 minutes
---

### Entry 2 - [November 13, 2026, 11:30 PM]
**What I did**:
Implemented Feature 1: ReentrantLock was used to safeguard the ready queue.
**Details**:
In the ReadyQueue class, a private final ReentrantLock queueLock was declared. To guaranty mutual exclusion, all crucial parts of add(), poll(), processOf(), and snapshot() were wrapped in lock(), try, and finally { unlock() } blocks.
**Challenges**:
To avoid deadlocks, make sure each lock acquisition is strictly matched with an unlock inside a finally block.
**Solution**:
All queue operations were encircled by ordinary try-finally blocks.
**Time spent**:
1 hour
---

### Entry 3 - [November 14, 2026, 2:00 AM]
**What I did**:
Feature 2 was implemented: shared statistics now have synchronization locks.
**Details**:
In SharedStats, a private static final ReentrantLock statsLock was declared. To avoid dirty readings and lost updates, all update methods (incrementContextSwitch, incrementCompletedProcess, addServiceTime) and reader methods (getCompletedProcessCount, getContextSwitchCount, getTotalServiceTime) were protected.
**Challenges**:
Choosing between a single lock and several locks, as well as making sure readers are appropriately synced.
**Solution**:
Select a single statisticAll reads and writes were wrapped in try-finally to ensure simplicity and atomicity across all shared counters.
**Time spent**:
1.5 hours
---

### Entry 4 - [November 14, 2026, 4:00 AM]
**What I did**:
Implemented Feature 3: Added clean shutdown logic and substituted a counting semaphore for busy-waiting.
**Details**:
declared a counting semaphore called readyQueue, with its initial value set to 0. To stop threads from busy-waiting, readyQueueSemaphore.release() was added to add() and readyQueueSemaphore.acquire() to poll(). When the simulation is over, sleeping CPUs can be unblocked thanks to the implementation of wakeUpAllCPUs(), which releases totalCPUs.
**Challenges**:
handling CPU threads that are stuck and waiting on the semaphore once the final process has completed its execution.
**Solution**:
developed the wakeUpAllCPUs() method, which is run when the last process is finished, enabling all worker threads to end gracefully and without hanging.
**Time spent**:
1.5 hours
---

### Entry 5 - [November 14, 2026, 9:00 PM]
**What I did**:
Final verification, technical solutions, documentation, and reflection.
**Details**:
completed MY_WORK.md entries, checked the output for all green checkmarks  throughout several runs, and got it ready for submission.
**Challenges**:
Clearly formatting technical explanations with specific output examples.
**Solution**:
To write accurate, superior responses, execution logs and code implementation details were cross-checked.
**Time spent**:
45 minutes
---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [5.5 hours]

**Most challenging part**: Semaphores without deadlocks are used to control thread synchronization and clean CPU shutdown.

**Most interesting learning**: How software primitives like ReentrantLocks and Semaphores can be used to tackle hardware-level concurrency problems (race situations).

**What I would do differently next time**: Start testing sooner and divide each feature's testing into smaller, incremental steps.

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

I discovered that when several threads access shared memory at once without synchronization, concurrent execution creates unforeseen race circumstances. To ensure that locks are always released, critical areas must be carefully identified and secured using mutual exclusion mechanisms like `ReentrantLock` wrapped in `try/finally` blocks. Additionally, I realized how semaphores allow threads to sleep and wake up deterministically by substituting blocking primitives for inefficient busy-waiting loops. This assignment showed that in multi-threaded operating systems, correct synchronization is crucial for preserving data consistency and avoiding deadlocks.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

Implementing Feature 3 and making sure that all CPU worker threads terminate cleanly at the simulation's conclusion were the most difficult aspects of this task. The worker threads would wait endlessly in the absence of a way to awaken CPUs trapped on the semaphore's `acquire()` method, which would result in the watchdog timer failing the simulation. It took a thorough understanding of semaphore dynamics and thread lifecycles to design the `wakeUpAllCPUs()` method, which releases allows equal to the total number of CPUs (`totalCPUs`) after the last process is finished.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

By methodically analyzing the code, adding informative print statements, and rereading the pertinent operating systems course notes about synchronization and semaphores, I was able to overcome these difficulties. I closely examined the bracket balances and lock scopes in Visual Studio Code whenever I came across compilation issues or strange thread behavior. I was also able to swiftly identify problems and confirm that the verification block produced green checkmarks by gradually testing the simulation after adding each feature.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Real-world software frequently uses synchronization notions. For example, database management systems require concurrent operations to update shared records atomically in order to prevent data corruption. Another typical use is in multi-threaded web servers processing user requests, where thread-safe access via mutexes is necessary for shared caches or connection pools. Semaphores and queues are also crucial for managing resource allocation and process scheduling among several CPU cores in print spoolers and operating system task schedulers.

### Optional: What would you like to learn more about?

I'm interested in learning more about memory barriers, sophisticated lock-free data structures, and how contemporary multi-core operating systems manage hardware-level thread scheduling and fine-grained locking.

### Optional: How confident do you feel about synchronization concepts now?

certain. I have a thorough understanding of mutex locks, critical sections, and semaphores, and I feel confident using them to avoid race situations and resolve concurrency problems.

### Optional: Feedback on the assignment

The task was very beneficial and useful. It connected the dots between practical multi-threaded Java programming and theoretical operating systems ideas (Chapter 5).

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

Race situations and missed updates result from the original starting code's concurrent updating of shared counters like `contextSwitchCount` without mutual exclusion. One update replaces the other when several CPU threads read the same counter value, pause using `RaceWindow.pause()`, and then post back their increased values. Due to erratic OS thread interleaving, this concurrency fault happens nondeterministically on actual machines, making it very challenging to find using traditional testing.

Verification block of the **original starter**:
```
⛔ WATCHDOG: the simulation did not finish. A process was lost, or a CPU is blocked forever, or the 'completed' counter lost an update.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
Context switches (quanta executed)          expected 26       observed 26      ✔
Completed processes                         expected 14       observed 14      ✔
Total service time (ms)                     expected 58055    observed 58055   ✔
Busy-waiting polls (must be 0)              expected 0        observed 0       ✔
✔ All shared values are consistent.
```

**Explanation of the timeline:**
CPU-1 reads `contextSwitchCount` = 12 and hits `RaceWindow.pause()`. Simultaneously, CPU-2 reads the same `contextSwitchCount` = 12. CPU-1 finishes its pause, computes `12 + 1 = 13`, and writes `13` back to `contextSwitchCount`. Shortly after, CPU-2 computes `12 + 1 = 13` and overwrites the counter with `13`, causing a lost update where two increments resulted in only a single net increase.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

In order to prevent data corruption, critical areas of code that access shared mutable state must be safeguarded by mutual exclusion locks. We decided to utilize a single `statsLock` for our statistics because the counters are independent and lightweight, reducing locking overhead while maintaining atomicity. To increase CPU thread concurrency and segregate queue management from statistics updates, a distinct `queueLock` protects the ready queue. Under high loads, thread starvation may result from threads acquiring locks in order of contention rather than FIFO due to the non-fairness of default `ReentrantLock` instances.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add(Process)` | `queueLock` | Prevents race conditions when adding threads and mapping processes concurrently. |
| `ReadyQueue.poll()` | `queueLock` | Ensures mutual exclusion when reading and removing the queue head. |
| `SharedStats.incrementContextSwitch()` | `statsLock` | Protects the read-modify-write sequence of the context switch counter. |
| `SharedStats.addServiceTime(int)` | `statsLock` | Ensures safe atomic updates to the total service time accumulator. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

The starter code produced busy-waiting polls and wasted CPU cycles since CPU worker threads polled the empty ready queue continually in a `while` loop. This ineffective polling is replaced by a blocking mechanism initialized to `0` by the counting semaphore (`readyQueueSemaphore`). The number of active processes that are presently waiting in the ready queue is appropriately reflected in its value. When the simulation concludes with 0 busy-waiting polls, as confirmed in our results, the final CPU to finish calls `wakeUpAllCPUs()` to perform `readyQueueSemaphore.release(totalCPUs)`, unblocking all sleeping worker threads so they may stop cleanly.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
This simulation represents the **Producer-Consumer Problem**. The main thread and CPU workers acting upon unfinished processes play the role of **producers** (adding processes to the ready queue), while CPU worker threads pulling items via `poll()` play the role of **consumers**.

**Semaphores for a bounded queue (name and initial value)**:
1. `mutex` (initial value: 1) - Ensures mutual exclusion for queue access.
2. `empty` (initial value: K) - Counts available empty slots in a bounded buffer of capacity K.
3. `full` (initial value: 0) - Counts filled slots containing ready processes.

**Deadlock scenario and prevention**:
A deadlock would occur if a worker thread acquired the queue mutex first and then blocked on a semaphore (`empty` or `full`) while holding the lock, preventing any other thread from freeing slots. To prevent this deadlock, we break the **Hold and Wait** or **Circular Wait** condition by acquiring the semaphore permit (waiting for a resource) before locking the critical section mutex, or by ensuring a strict, global lock acquisition ordering.

## Summary

**Key concepts I understood through these questions:**
1. Mutual exclusion and thread synchronization using ReentrantLocks and try-finally blocks.
2. Replacing inefficient busy-waiting loops with counting semaphores for blocking and waking threads.
3. Managing lock granularity and preventing race conditions in concurrent operating system simulations.

**Concepts I need to study more:**
1. Advanced deadlock prevention strategies and resource allocation graphs.
2. Lock-free data structures and fair locking policies in multi-core systems.
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
