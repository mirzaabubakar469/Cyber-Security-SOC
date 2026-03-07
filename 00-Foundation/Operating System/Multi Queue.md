## Multilevel Queue Scheduling

* 1. System Processes
* 2. Interactive Processes
* 3. Batch Processes

* Easy to organize different process types
* Efficient for systems with different workloads
* **Starvation problem** may occur
* Lower priority queues may **never get CPU time**

## Multilevel Feedback Queue Scheduling

* 1. New process enters **highest priority queue (Q1)**
* 2. If it finishes quickly → stays in higher queue
* 3. If it uses too much CPU → moved to lower queue
* 4. Lower queues get longer time slices

* Prevents starvation
* More flexible than multilevel queue
* Good for interactive systems
* More complex to implement
* Requires careful tuning of parameters

## Multilevel Queue vs Multilevel Feedback Queue

| Feature          | Multilevel Queue | Multilevel Feedback Queue |
| ---------------- | ---------------- | ------------------------- |
| Process Movement | Not allowed      | Allowed                   |
| Flexibility      | Low              | High                      |
| Starvation       | Possible         | Less likely               |
| Complexity       | Simple           | Complex                   |
