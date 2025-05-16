## Introduction to Security Groups

* Security Groups are the fundamental of network security in AWS
* They control how traffic is allowed into or out of EC2 Instances
* Security Groups only contain allow rules
* Security groups rules can reference by IP or by security group

What is it? It's a firewall on our EC2 Instances

* They regulate:
  * Access to Ports
  * Authorised IP ranges - IPv4 and IPv6
  * Control of inbound network (from other to the instance)
  * Control of outbound network (from the instance to other)

### Good to know:

* Security groups can be attached to multiple instances
* Locked down to a region / VPC combination
* Does live "outside" the EC2 - if traffic is blocked the EC2 Instance won't see it
* It's good to maintain one separate security group for SSH access
* If your application is not acessible (time out ) then it's a security group issue
* If your application gives a "connection refused" error, then it's an application error or it's not launched
* By default all inbound traffic is blocked

### Classic ports to know:

* 22 = SSH (Secure Shell) - Log into a Linux Instance
* 21 = FTP (File Transfer Protocol) - Upload Files into a file share
* 22 = SFTP = (Secure File Transfer Protocol) - Upload files using SSH
* 80 = HTTP - Access Unsecured Websites
* 443 = HTTPS - Access Secured Websites
* 3389 = RDP (Remote Desktop Protocol) - Log into a Windows Instance


### Outbound Rules:

Outbound rules in an AWS EC2 security group define the **network traffic that is allowed to leave** your EC2 instance. These rules control what destinations your instance can send data to. Each rule specifies:

* **Destination** : The IP address range or security group the traffic is allowed to reach.
* **Protocol** : The type of traffic (e.g., TCP, UDP, ICMP).
* **Port Range** : The specific port or range of ports allowed.
* **Description**  *(optional)* : A note to describe the rule.

By default, security groups allow  **all outbound traffic** , but you can restrict this to limit where the instance can connect.

### Inbound Rules:

Inbound rules in an AWS EC2 security group define the **network traffic that is allowed to reach** your EC2 instance. These rules control who can connect to your instance and on which ports. Each rule specifies:

* **Source** : The IP address range or security group allowed to send traffic.
* **Protocol** : The type of traffic (e.g., TCP, UDP, ICMP).
* **Port Range** : The specific port or range of ports open (e.g., 22 for SSH, 80 for HTTP).
* **Description**  *(optional)* : A note to describe the rule.

By default, security groups allow  **no inbound traffic** , meaning you must explicitly add rules to allow access (e.g., SSH from your IP address).
