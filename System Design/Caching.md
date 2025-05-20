
### Cache

When talking about caching, we need to understand the underlying **algorithm** we will use.

### Redis

* The information below only happens when the max of memory is achived (the input and output of items.)

For example, with Redis, we can choose between the following  **algorithms** :

* **LRU** (Least Recently Used)
* **LFU** (Least Frequently Used)
* **FIFO** (First In, First Out)

### **LRU (Least Recently Used)**

---

Evicts the item that  **hasn't been used for the longest time**.

Example:  You open 5 files, and the cache can only store 3. If you keep switching between the last 3, the first 2 will be removed as they haven’t been used recently.

### LFU (Least Frequently Used)

---

Evicts the item that is  **used the least number of times** .

Example: If one item is accessed 100 times and another only once, the one accessed once will be evicted first.

### FIFO (First In, First Out)

---

Evicts the **oldest added** item, regardless of how often it’s used.

Example: Like a queue, the first item that entered will be the first to go out.
