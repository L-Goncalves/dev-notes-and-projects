# What are AWS services?

AWS (Amazon Web Services) provides a broad set of cloud-based products and services including computing, storage, databases, networking, developer tools, and more. Below are brief descriptions of two commonly used AWS services:

## AWS CloudShell:

i'ts a browser-based, pre-authenticated terminal available directly within the AWS Management Console

Basically a terminal in the cloud free to use. (Not available in all regions)

* All files created in cloud shell remain created
* Very configurable (styling)
* You can download and upload files

## AWS EC2 Instance:

It's a service that provides resizable virtual servers in the cloud. Think of it as renting a computer that runs in AWS data centers, where you can run applications, host websites, and perform computing tasks.

## Amazon EKS:

Amazon EKS is AWS's way of letting you  **run Kubernetes clusters easily** , with less manual setup and more integration with AWS tools.

Amazon EKS is a **managed Kubernetes service** that makes it easy to run Kubernetes on AWS **without having to install, operate, or maintain** your own Kubernetes control plane or nodes.

## Amazon Lightsail:

* For quick setup of small websites

## Database Services:

* Fully managed relational and NoSQL databases
* Also offers fully managed scalable petabyte-scale warehouse serivce
* Highly scalable and cost efficient crunch data at fraction of the cost on-site database servers.

### Amazon Aurora:

* **High-performance relational database** built for the cloud
* Compatible with **MySQL** and **PostgreSQL** , offering up to **5x the performance of standard MySQL** and **3x for PostgreSQL**
* **Highly available and durable** , with data replicated across multiple Availability Zones
* **Auto-scaling storage** up to 128 TB per database instance
* Ideal for **enterprise-grade applications** needing speed, reliability, and minimal maintenance

### Elastic Cache:

* In-memory data store and cache service for real-time applications
* Supports Redis!
* Great for gaming session storage and real-time analytics
* Fully managed, with autoscaling, failover support

### AWS S3 (Bucket):

AWS S3 is a service that saves objects such as archives, images,PDFs and more. It's highly scalable safe and low cost.

### AWS SQS:
 
AWS SQS (Amazon Simple Queue Service) is a fully managed message queueing service by Amazon Web Services.

##### Use Case Example:
Imagine you have a web app where users upload images. You don’t want to process images immediately on the main server because it’s slow. Instead:

The server puts a message like “User123 uploaded image.png” into the SQS queue.

A background worker (another server) reads that message from the queue and processes the image.

After processing, the worker deletes the message from the queue.

##### Why use SQS?
Decoupling: Separates components so they don't need to talk to each other directly.

Scalability: Lets you handle spikes in traffic without crashing.

Reliability: Messages stay in the queue until processed (or timeout).

Retries: Automatically tries again if processing fails.


 
