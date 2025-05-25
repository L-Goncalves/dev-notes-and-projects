### Load Balancing Concept

Before diving into Elastic Load Balancing, it's important to understand **what a load balancer is** and  **why it's so commonly discussed in Software Engineering** .

A **load balancer** is a system that automatically distributes incoming network traffic across multiple servers or resources. Its primary goal is to ensure that no single server becomes overwhelmed with too much traffic, which helps improve

* Scalability: Easily handle growing traffic
* Availability: If one server fails, traffic is redirected to a healthy server!
* Performance: Balance workloads to reduce latency and improve user experience.

In modern software systems, especially AWS and other cloud based architectures load balancing is critical. it's a foundational concept behind building reliable, fault-tolerant and scalable applications

Now that we understand the concept of load balancing, let's look at **Elastic Load Balancing (ELB)**

### Elastic Load Balancing (ELB)

Now that we understand the concept of load balancing, let's look at **Elastic Load Balancing (ELB)** by Amazon Web Services (AWS)


Elastic Load Balancing automatically distributes incoming application traffic across multiple targets such as:

* EC2 Instances
* Containers
* IP Addresses
* Lambda Functions

The word **“Elastic”** means that the load balancer can automatically scale to handle changes in traffic, wether it increases or decreases without manual intervention.


### Why use?

**High Availability:** ELB monitors the health of targets and routes traffic only to healthy ones.

**Fault Tolerance:** If a server goes down, ELB reroutes traffic instantly

**Automatic Scaling:** Handles varying loads dynamically.

**Security Integration:** Works with AWS security features like SSL/TLS, AWS Certificate Manager, and IAM.

**Cost-Effective:** Pay only for what you use.

### Types of Elastic Load Balancers

#### Application Load Balancer (ALB)

* Works at Layer 7 (HTTP/HTTPS).
* Smart routing based on content (URL path, hostname, query parameters)
* Best for microservices and web applications.

#### Network Load Balancer (NLB)

* Works at Layer 4 (TCP/UDP).
* Ultra-high performance and low latency.
* Best for millions of requests per second or real-time systems.

#### Gateway Load Balancer (GWLB)

* For deploying, scaling, and managing third-party virtual appliances (like firewalls or intrusion detection).

#### **Classic Load Balancer (CLB)**

* Works at both Layer 4 and Layer 7 but is mostly outdated in favor of ALB and NLB.


### How does it work?

* **Client sends a request.**
* **DNS resolves to the ELB endpoint.**
* ELB checks the health of all registered targets.
* ELB forwards the request to one of the healthy targets based on its algorithm (round robin, least connections, or IP-hash depending on the load balancer type).
* The target processes the request and responds to the client (either through the ELB or directly, depending on the setup).
