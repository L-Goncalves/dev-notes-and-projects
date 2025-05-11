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
