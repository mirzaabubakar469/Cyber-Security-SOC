## Deadlock in Operating Systems

A **Deadlock** is a situation in an operating system where **two or more processes are unable to proceed** because each process is **waiting for a resource held by another process**.
As a result, all processes involved **remain stuck indefinitely**.
Deadlock occurs when processes are **waiting for each other forever**.

---

### Example: Two Processes and Two Resources

Assume:

* **Process P1** holds **Resource R1**
* **Process P2** holds **Resource R2**

Now:

* P1 requests **R2**
* P2 requests **R1**

Neither process releases its resource.

### Result

Both processes **wait forever**, causing a **deadlock**.

---

### Necessary Conditions for Deadlock

For a deadlock to occur, **four conditions must be true at the same time**.

These are called **Coffman Conditions**.

---

#### 1. Mutual Exclusion

At least one resource must be **non-shareable**.

Only **one process can use the resource at a time**.

Example:

* Printer
* File lock

---

#### 2. Hold and Wait

A process **holds at least one resource** and **waits for additional resources**.

Example:

Process holds **printer** but waits for **scanner**.

---

#### 3. No Preemption

Resources **cannot be forcibly taken** from a process.

They must be **released voluntarily** by the process.

Example:

OS cannot take printer from a process until it finishes.

---

#### 4. Circular Wait

A circular chain of processes exists where:

Process A waits for B
Process B waits for C
Process C waits for A

This creates a **cycle of waiting processes**.

---

### Deadlock Conditions Summary

| Condition        | Meaning                                          |
| ---------------- | ------------------------------------------------ |
| Mutual Exclusion | Resource used by one process at a time           |
| Hold and Wait    | Process holds one resource and waits for another |
| No Preemption    | Resources cannot be forcibly removed             |
| Circular Wait    | Processes form a waiting cycle                   |

All four conditions must exist for **deadlock to happen**.

---

### How Deadlocks Are Handled

1. **Deadlock Prevention** – eliminate one of the four conditions
2. **Deadlock Avoidance** – avoid unsafe states
3. **Deadlock Detection** – detect and recover
4. **Deadlock Recovery** – terminate or restart processes
