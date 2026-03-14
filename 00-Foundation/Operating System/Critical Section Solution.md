## Critical Section Solutions: Lock Variable, Test-and-Set, Turn Variable

These are **basic software/hardware techniques** used to solve the **critical section problem** in Operating Systems and ensure **process synchronization**.

---

### 1. Lock Variable

#### Concept

The **lock variable** is the simplest method used to control access to the **critical section**.

A shared variable called **lock** indicates whether the critical section is **available or occupied**.

* `lock = 0` → Critical section is free
* `lock = 1` → Critical section is busy

---

#### Working

1. A process checks if `lock = 0`.
2. If the lock is free, the process sets `lock = 1`.
3. The process enters the **critical section**.
4. After finishing, it sets `lock = 0`.

---

#### Problem

This solution **does not guarantee mutual exclusion**.
Two processes may read `lock = 0` at the same time and both enter the critical section.
This causes a **race condition**.

---

### 2. Turn Variable (Strict Alternation)

#### Concept

The **turn variable** ensures that processes enter the critical section **in a fixed order**.

A variable `turn` determines **which process can enter the critical section**.

Example with two processes:

* `turn = 0` → Process 0 can enter
* `turn = 1` → Process 1 can enter

---

#### Working

1. Process checks if it is its **turn**.
2. If yes → enter critical section.
3. After finishing → give turn to the other process.

---

#### Problem

It **violates the progress condition**.

Example:

* Process 0 finishes
* Process 1 is not interested
* Process 0 must still wait for its turn

This causes **unnecessary waiting**.

---

### 3. Test-and-Set Instruction

#### Concept

**Test-and-Set** is a **hardware atomic instruction** used to implement mutual exclusion.

It checks and modifies a variable **in one atomic operation**.

This prevents **race conditions**.

---

#### Working

1. Process calls `test_and_set()`.
2. If lock is **false**, it becomes **true** and process enters.
3. Other processes keep waiting.
4. When finished, the process sets `lock = false`.

---

#### Advantages

* Ensures **mutual exclusion**
* Prevents **race conditions**
* Atomic hardware instruction

---

#### Disadvantages

* Uses **busy waiting (spin waiting)**
* CPU cycles are wasted while waiting

---

### Comparison

| Method        | Mutual Exclusion | Progress | Problem            |
| ------------- | ---------------- | -------- | ------------------ |
| Lock Variable | Not guaranteed   | Yes      | Race condition     |
| Turn Variable | Yes              | No       | Strict alternation |
| Test-and-Set  | Yes              | Yes      | Busy waiting       |
