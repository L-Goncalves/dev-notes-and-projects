### EC2 Instance Types

* You can have different types of EC2 instances that are optmised for any use case you might need.

#### Naming Conventions:

Example: m5.2xlarge

* m: stands for instance class
* 5: is the generation (AWS improves over time)
* 2xlarge: size within the instance class

#### General Purpose

* Great for diversity of workloads such as web servers or code repositories
* Balance between:

  * Compute
  * Memory
  * Networking

#### Compute Optimized (Starts with C)

* Great for compute intensive tasks that require high performance processors:
  * Batch processing workloads
  * Media transcoding
  * High performance web servers
  * High performance computing (HPC)
  * Scientific Modeling & Machine Learning
  * Dedicated Gaming servers

#### Memory Optimized (Starts with R)

* Fast performance for workloads that process large data sets in memory
* Use cases:
  * High performance, relational/non-relational databases
  * Distributed web scale cache stores
  * In-memory databases optimized for BI (Business Inteligence)
  * Applications performing real-time processing of big unstructured data

#### Storage Optimized

* Great for storage-intensive tasks that require high, sequential read and write access to large data sets on local storage
* Use cases:
  * High frequency online transaction processing (OLTP) systems
  * Relational & NoSQL databases
  * Cache in-memory databases (for example Redis)
  * Data warehousing applications
  * Distributed file systems

#### Accelerated Computing:

* Good for functions that require high processing capabilities
