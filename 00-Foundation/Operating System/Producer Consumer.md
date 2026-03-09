## 🍽 Producer–Consumer Problem

The **Producer–Consumer Problem** is a classic **process synchronization problem** in Operating Systems.

* **Producer:** Produces data (e.g., items)
* **Consumer:** Consumes data

Both share a **common buffer (storage)** of limited size.

---

### Rules:

1. Producer cannot add if buffer is **full**
2. Consumer cannot remove if buffer is **empty**
3. Synchronization is needed to **avoid conflicts**

### Key Points

* Producer waits if buffer is **full**
* Consumer waits if buffer is **empty**

### Summary Table

| Concept   | Description                  |
| --------- | ---------------------------- |
| Producer  | Generates data               |
| Consumer  | Uses data                    |
