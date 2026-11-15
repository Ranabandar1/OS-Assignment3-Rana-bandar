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
| **Full Name** | [Write your full name here] |
| **Student ID** | [Write your student ID here] |
| **University Email** | [yourid]@std.psau.edu.sa |
| **GitHub Username** | [your-github-username] |
| **Repository Link** | [Paste your repository link here] |
 
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

### Entry 1 - [November 15, 2026 (11:00 AM – 12:00 PM)]
**What I did**:Examined the assignment repository and tested the original starter program.

**Details**:
- Read the assignment instructions and examined SchedulerSimulationSync.java.
- Before adding the synchronization features, the initial starting program was compiled and executed.
- observed the concurrent access to the Ready Queue by CPU threads.
- The first terminal output was saved for comparison.

**Challenges**:
I looked at the RaceWindow and ReadyQueue.poll().To comprehend how concurrent access could result in a race scenario when the queue was not protected, use the pause() method.
**Solution**:

**Time spent**: 1 hour

---

### Entry 2 - [November 15, 2026 (12:00 PM – 1:30 PM)]
**What I did**:Ready Queue Lock is the first feature that has been implemented.

**Details**:
- ooked at the map and shared list in the ReadyQueue class.
- Added a ReentrantLock named queueLock.
- Protected add(), poll(), processOf(), and snapshot().

- Used lock() before accessing the shared data structures.

- Used try/finally to ensure that the lock was always released.

**Challenges**:Since map, protecting just the poll() method would not be adequate.

**Solution**:To ensure the shared queue data structures with the same queueLock.

**Time spent**: 1 hour and 30 minutes

---

### Entry 3 - [November 15, 2026 (1:30 PM – 4:00 PM)]
**What I did**:Shared Statistics Locks is the second feature that has been implemented.

**Details**:
- Examined contextSwitchCount, completedProcessCount, and totalServiceTime in SharedStats.

- Added separate locks for the three independent statistics.

- Protected the methods that update each statistic.

- Also protected the corresponding getter methods.

- Used try/finally to release each lock safely.

**Challenges**:I had to determine how to safeguard the three independent statistics without needlessly stalling irrelevant updates and avoid race circumstances during read-modify-write operations.

**Solution**:For every statistic, I utilized a different ReentrantLock. This allows actions on various statistics to continue independently while providing mutual exclusion for each variable.

**Time spent**: 2 hours and 30 minutes

---

### Entry 4 - [November 16, 2026 (11:00 AM – 1:30 PM)]
**What I did**:Feature 3: Counting Semaphore was put into practice.

**Details**:
- Imported java.util.concurrent.Semaphore.

- Created a counting semaphore initialized to zero.

- Released one permit whenever a process was added to the Ready Queue.

- Replaced the repeated polling loop and Thread.sleep(20) with acquire().

- Added shutdown signaling to wake up CPU threads after all processes were completed.

**Challenges**:Managing CPU threads that were stalled while awaiting a semaphore permit presented the biggest difficulty. When no more processes were created, I had to make sure they could awaken and shut down.
**Solution**:After all processes are finished, I put in place a shutdown procedure that releases permits equal to totalCPUs. To make sure the shutdown signal is transmitted only once, I additionally employed a shutdown flag.

**Time spent**:2 hours and 30 minutes

---

### Entry 5 - [ November 16, 2026 (1:30 PM – 4:00 PM)]
**What I did**:assembled, examined, and confirmed the finished product.


**Details**:
- Compiled SchedulerSimulationSync.java.

- Corrected a missing closing brace that initially caused a compilation error.

- Ran the final simulation and examined the verification block.

- Checked the context switches, completed processes, total service time, and busy-waiting polls.

- Repeated the final verification runs and reviewed the results.

**Challenges**:I had to ensure that the application generated accurate statistics, finished all processes, terminated without leaving any stopped CPU threads, and properly compiled.


**Solution**:I corrected the syntax error, reviewed the synchronization and shutdown logic, and ran the program repeatedly. The final successful output showed that all four expected values matched the observed values and that busy-waiting polls were zero.

**Time spent**:2 hours and 30 minutes

---

### Entry 6 - [November 16, 2026 (3:30 PM – 4:00 PM)]
**What I did**:prepared the repository for submission after reviewing the project documentation.

**Details**:
- Reviewed MY_WORK.md to make sure the development log, reflection, and technical answers were included.

- Checked the project files and verified that the three synchronization features were implemented.

- Reviewed the Git commit history to ensure that the feature changes were documented with meaningful commit messages.

- Checked the final verification results and confirmed that the repository was ready for submission.

**Challenges**:ensuring consistency and completeness in the implementation, documentation, and Git history.

**Solution**:To find anything that needed to be fixed before submission, I went over the project requirements and contrasted them with the features and documentation that had been put in place.

**Time spent**:30 minutes

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: 10 hours

**Most challenging part**:Implementing the counting semaphore shutdown technique was the most difficult component since blocked CPU threads had to wake up and end once all processes were finished.

**Most interesting learning**:I discovered how a counting semaphore enables CPU threads to wait effectively rather than continuously checking an empty queue and how locks shield shared data from race situations

**What I would do differently next time**:
Before putting the features into practice, I would examine the shared data structures and thread interactions. Additionally, I would test each feature independently and record the outcomes following each work session.
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
I discovered that when several threads access and alter shared data simultaneously, synchronization is crucial. When two threads read the same data, change it, and then write it back without adequate security, it can result in a race condition and a lost update. To safeguard the shared Ready Queue and stop several CPU threads from simultaneously accessing its data structures, I employed a ReentrantLock in my project. To safeguard their getter and update methods, I also implemented different locks for each of the three shared statistics. I discovered that the use of try/finally is crucial since it ensures that a lock is released even in the event of an exception. Ultimately, I discovered that CPU threads can be forced to wait until a process gets
## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

Implementing the counting semaphore and properly managing the CPU shutdown were the most difficult aspects of this task. I realized that since there are no processes available before they are added to the Ready Queue, the semaphore should begin with 0 permits. But I had to ensure that each CPU obtained a permit before accepting a process, and that each new process added to the queue released one permit. The possibility of CPU threads becoming blocked indefinitely after all programs were finished presented another difficulty. I created a shutdown mechanism that releases permissions equivalent to the entire number of CPUs in order to address this issue. Because the CPUs had to awaken, acknowledge that the work was completed, and end without interruption, this section required careful consideration.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*
By carefully reading the task instructions and reviewing the program structure before making any changes, I was able to overcome the difficulties. To comprehend how the threads shared data, I looked at the roles of ReadyQueue, SharedStats, and CpuWorker. One by one, I added the synchronization features, and after each modification, I verified the methods that were impacted. I looked over the code structure and fixed the missing closing brace that I found during compilation, which resulted in a compilation problem. Once the features were finished, I assembled and repeatedly executed the program to verify the outcomes. These tests enabled me to verify that the busy-waiting polls were zero and that all four expected values matched the observed values.


## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*
Many real-world applications that allow many users or processes to access shared resources require synchronization. For instance, locks in financial systems can stop two transactions from simultaneously changing the same account balance. Synchronization keeps two clients from concurrently reserving the same seat in online ticketing systems. When several transactions read or update data in a database, locks safeguard shared records. In a printing system, a semaphore can also be used to restrict access to certain printers or other resources. These examples are comparable to my project since synchronization was required to maintain accurate results when different CPU cores accessed a common Ready Queue and shared statistics.

### Optional: What would you like to learn more about?
I'm interested in learning more about sophisticated synchronization methods, thread scheduling, and deadlocks. Additionally, I'm curious about how operating systems effectively handle numerous threads.

### Optional: How confident do you feel about synchronization concepts now?

Intermediate.I am familiar with the fundamental ideas of locks, counting semaphores, mutual exclusion, critical sections, and race conditions. I can describe how I applied these ideas to my project, but I still need more experience with complex multithreaded programs and deadlock prevention.

### Optional: Feedback on the assignment

Instead of just learning theoretical ideas, the assignment helped me understand synchronization through real implementation. The semaphore shutdown technique, however, was difficult and needed thorough testing. The assignment, in my opinion, offers a good chance to comprehend how different threads interact when they share resources..


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

[Write your answer here.]

Verification block of the **original starter**:
```
[Paste the verification block (or the exception/watchdog message) of the starter here]
```

Verification block of **my final version**:
```
[Paste the verification block of your final version here (all lines ✔)]
```

**Explanation of the timeline:**
[Explain the lost update step by step.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[Write your answer here.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
[Name the problem; who is the producer, who is the consumer?]

**Semaphores for a bounded queue (name and initial value)**:
[Name the three semaphores and their initial values.]

**Deadlock scenario and prevention**:
[Describe the scenario and the necessary condition you would break.]

## Summary

**Key concepts I understood through these questions:**
1.
2.
3.

**Concepts I need to study more:**
1.
2.

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
