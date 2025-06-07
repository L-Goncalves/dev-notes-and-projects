### Networking Services!

This is an introduction into Networking Services on AWS.

#### Amazon Virtual Private Cloud (VPC)

An **Amazon VP** is a **logically isolated** network in AWS that you  **fully control** . You can:

* Choose your own **IP address range**
* Create **subnets**
* Set  **route tables** ,  **security settings** , and **gateways**

Superficial info:

* Logically isolated section in the cloud to provision resources
* Flexible and secure, allowing you to control almost every aspect of your virtual network

#### Core Components of a VPC:

###### 1. CIDR Block (IP Range):

* Defines the **IPv4 or IPv6 range** of your VPC.
* Example: `10.0.0.0/16` (supports 65,536 IPs).
* You can divide this into smaller  **subnets** .

###### 2. Subnets

* Sub-sections of your VPC's IP range.
* Two types:

  * Public subnet: has a route to internet (via an internet gateway)
  * Private subnet: No direct internet route - used for INTERNAL resources! (db etc..)
* You typically put:

  * Web servers in public subnets
  * App servers or databases in private subnets'

###### 3. Route tables

* Control how traffic is routed within the VPC and outside
* Each subnet is associated with a route table.
* Routes define:
  * Traffic to other subnets
  * Traffic to the internet (via IGW)
  * Traffic to a NAT Gateway

###### 4. Internet Gateway (IGW)

* A gateway to the public internet
* Required for public subnets to allow inbound/outbound internet traffic

###### 5. NAT Gateway / NAT Instance

* Used by private subnets to access the internet without being accessible from it.
* NAT Gateway is managed and scalable (preferred over NAT Instance).

###### Security Groups

* Act like virtual firewalls at the instance level.
* Define allowed/outbound rules by protocol and port

###### 7.Network ACLs (Access Control Lists)

* Optional stateless firewalls at the subnet level.
* You can allow or deny specific IPs or port ranges.
* Useful for extra security layers

###### 8. VPC Peering

* Directly connect two VPCs
* Traffic stays within AWS NETWORK! doesn't go over the internet.

###### 9. VPC Endpoints:

* Private connections to AWS services like S3 or DynamoDB without using the internet.
  * Interface endpoints: Use ENIs.
  * Gateway endpoints: Route table-based (for S3 or DynamoDB).

###### 10. Flow logs:

* Capture IP traffic goign to and from network interfaces
* Great for troubleshooting, compliance, and security analysis.

Architecture: 

```VPC:
├── Public Subnet (10.0.1.0/24)
│   ├── EC2 Web Server
│   └── Internet Gateway
│
├── Private Subnet (10.0.2.0/24)
│   ├── EC2 App Server
│   └── NAT Gateway (in Public Subnet)
│
└── Security Groups + Route Tables
```

#### Best Practices

* Use **multiple Availability Zones** for high availability.
* Apply **least privilege** in security group rules.
* Enable **VPC flow logs** to monitor activity.
* Use  **NAT Gateways** , not NAT instances, for scalability.
* Use **VPC endpoints** for private access to AWS services.
