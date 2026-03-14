## Semaphores in Operating Systems

### What is a Semaphore?

A **Semaphore** is a synchronization tool used in operating systems to **control access to shared resources** among multiple processes or threads.

It helps prevent problems like:

* Race conditions
* Data inconsistency

A semaphore is basically an **integer variable** that is accessed using two atomic operations.

---

### Semaphore Operations

There are two main operations used with semaphores.

#### 1. Wait Operation (P Operation)

The **wait()** operation decreases the value of the semaphore.

If the semaphore value becomes negative, the process must **wait (block)** until the resource becomes available.

##### Working

* Process requests access to the resource
* If resource is available → process enters
* If not → process waits

---

#### 2. Signal Operation (V Operation)

The **signal()** operation increases the semaphore value and wakes up a waiting process.

##### Working

* Process finishes using the resource
* It releases the resource
* Another waiting process is allowed to proceed

---

### Types of Semaphores

#### 1. Counting Semaphore

A **counting semaphore** can have **multiple values**.

It is used when multiple instances of a resource are available.

#### Example

If a system has **3 printers**, the semaphore value may start at **3**.

Processes decrease the value when using the printer and increase it when finished.

---

#### 2. Binary Semaphore

A **binary semaphore** has only two values:

* **0** → resource not available
* **1** → resource available

This ensures **only one process enters the critical section at a time**.

---

#### Advantages of Semaphores

* Prevent race conditions
* Provide process synchronization
* Efficient resource management
* Work with multiple processes or threads

---

#### Disadvantages

* Difficult to implement correctly
* Incorrect usage may cause **deadlock**
* Debugging synchronization issues can be complex

---

### Summary

| Concept            | Description                 |
| ------------------ | --------------------------- |
| Semaphore          | Synchronization variable    |
| Wait (P)           | Decrease semaphore value    |
| Signal (V)         | Increase semaphore value    |
| Counting Semaphore | Used for multiple resources |
| Binary Semaphore   | Used for mutual exclusion   |
