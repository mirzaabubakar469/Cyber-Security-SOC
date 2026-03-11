## Critical Section Problem in Operating Systems

The **Critical Section Problem** occurs when multiple processes access **shared resources** at the same time.

The **critical section** is the part of a program where a process **accesses shared data or resources**.

If more than one process enters this section simultaneously, it may cause **data inconsistency or race conditions**.

---

## Structure of a Process
* Entry Section
* Exit Section
* Mutual Exclusion
* Progress
* Bounded Waiting
* No assumption related to hardware and speed

## Summary

| Concept          | Description                                              |
| ---------------- | -------------------------------------------------------- |
| Critical Section | Part of code accessing shared resources                  |
| Mutual Exclusion | Only one process executes critical section               |
| Progress         | Waiting process should be allowed to enter               |
| Bounded Waiting  | Process should not wait forever                          |
