## Process Synchronization in Operating Systems

### What is Process Synchronization?

**Process Synchronization** is a mechanism used to **control the execution of multiple processes** that access **shared resources**.

It ensures that processes **do not interfere with each other** when accessing shared data.

The goal is to maintain **data consistency and system stability**.

---

### Why Process Synchronization is Needed

In multitasking systems, many processes may try to access the **same resource** at the same time.

Examples of shared resources:

* Files
* Memory
* Printers
* Databases

Without synchronization, this can cause **incorrect results or data corruption**.

### Problems Without Synchronization

#### Race Condition

A **race condition** occurs when multiple processes access shared data **simultaneously**, and the final result depends on the **execution order**.

Example:

Two processes update a bank balance at the same time.

Possible result → incorrect balance.

---

### Advantages of Process Synchronization

* Prevents race conditions
* Ensures data consistency
* Enables safe resource sharing
* Improves system reliability
