### Containers (Core Concept)

Containers are lightweight, portable units of software that package an application along with everything it needs to run, including code, libraries, and configurations. They allow applications to run consistently across different computing environments by isolating them from the underlying system.

* **Definition:** Containers are lightweight, portable, and self-sufficient software units that package an application along with its dependencies (code, libraries, configs) to run consistently across different environments.
* **Key Idea:** "Package once, run anywhere" — solves the “it works on my machine” problem.
* **How:** Containers use OS-level virtualization to share the host OS kernel while isolating the application processes.
* **Popular Tools:** Docker, Podman, containerd.
* **Difference from VMs:** Containers share the OS kernel (lighter, faster), whereas VMs have their own OS (heavier).
* **Common Use:** Microservices, DevOps, CI/CD, scalable deployments.

In AWS we have 2 Services that take care of Containers!

* Amazon ECS
* Amazon EKS
