
# Singleton Design Pattern

The Singleton Pattern is a **creational design pattern** that ensures a class has **only one instance** and provides a **global point of access** to that instance. It is commonly used when exactly one object is needed to coordinate actions across the system.



### Real-World Example:

Think of a **printer spooler** in an operating system. You want to ensure that there is only one spooler handling all the print jobs to prevent conflicts.


### Use Cases:

* Database connections
* Caching
* Logging services

Pros:

* Controlled access to sole instance
* Reduced memory footprint

### Cons:

* Global state can lead to code that’s hard to test
* Violates the Single Responsibility Principle

---
