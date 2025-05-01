## Amazon EC2

* EC2 is one of the most popular of AWS' offering
* ES2 means Elastic Compute Cloud = Infrastructure as a Service.
* It mainly consists in the capability of:
  * Renting virtual machines (EC2)
  * Storing data on virtual drives (EBS)
  * Distributing load across machines (ELB)
  * Scalling the services using an auto-scalling group (ASG)

### EC2 Sizing & Configuration Options:

* Operating System (OS): Linux, Windows or Mac OS
* How much compute power & cores (CPU)
* How much random access memory ( RAM)
* How much storage:

  * Network-Attached (EBS & EFS)
  * Hardware EC2 Instance Store
* Network Card: speed of the card, Public IP Address
* Firewall Rules: security group
* Bootstrap Script (Configure at first launch): EC2 User Data

### EC2 User Data:

* It is possible to bootstrap our instances using an EC2 User Data Script
* Bootstrapping means launching commands when a machine starts
* That Script is only run once at the instance first start
* EC2 user data is used to automate boot tasks such as:
  * Installing Updates
  * Installing software
  * Downloading common files from the internet
  * Anything you can think of
* Any command run has the SUDO permissions


### EC2 Instance Types:


| Instance    | vCPU | Memory (GiB) | Storage           | Network Performance | EBS Bandwidth (Mbps) |
| ----------- | ---- | ------------ | ----------------- | ------------------- | -------------------- |
| t2.micro    | 1    | 1            | EBS-Only          | Low to Moderate     | -                    |
| t2.xlarge   | 4    | 16           | EBS-Only          | Moderate            | -                    |
| c5d.4xlarge | 16   | 32           | 1 × 400 NVMe SSD | Up to 10 Gbps       | 4,750                |
| r5.16xlarge | 64   | 512          | EBS-Only          | 20 Gbps             | 13,600               |
| m5.8xlarge  | 32   | 128          | EBS-Only          | 10 Gbps             | 6,800                |


* t2.micro is part of AWS free tier (up to 750 hours per month)
