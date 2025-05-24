### Deploying (Conceptual)

AWS users can create and manage resources into AWS in three ways:

* By utilizing AWS Management Console
* By utilizing AWS CLI (Command Line Interface)
* By utilizing AWS Software Development Kits (SDKs)

### AWS Management Console

This is basically the AWS Console Interface (console.aws.amazon.com)

* Graphical Interface that supports most AWS Services
* Can access billing statements, launch new services, check out health of web apps and more..
* "It's user friendly and easy to navigate"

### AWS Command Line Interface

* Access AWS services via the command line
* Command line: access and charge resources via text-based command entry
* Programming-language agnostic
* Create scripts to run on AWS.

You can also install AWS CLI with this tutorial: [Install CLI](../Setup/InstallCLI.md)

### AWS SDK

It's a programming interface so you can use AWS resources in existing projects.

Well this is already explained in this repository in [another file](../Setup/Sdk.md)  

### Connecting to the Cloud:

You can connect to the Cloud through some options:

* Virtual Private Network (VPN)
* **AWS Direct Connect**
* Public Internet

### What is a VPN (Virtual Private Network)?

A **VPN (Virtual Private Network)** is a secure, encrypted connection between your device (computer, phone, etc.) and the internet. It works by creating a  **private tunnel over a public network (the internet)** .

### AWS Direct Connect:

* Creates a secure, private connection from your local network directly to AWS Cloud. Which is great for hybrid Infrastructure
* Considered the shortest path between local network and AWS, providing lower latency and reducing bandwidth costs
* Bypasses the public internet

### Public Internet

* The default connection method for most daily use of the internet is probably through the public internet for most people
* Data transferred is not secured, private or encrypted.
* You should utilize more private and secure ways to access the AWS Cloud to keep your resources secured

### Cloud and Cloud-Native Deployment:

* All parts of the IT infrastructure "lives" and run in the Cloud Provider.
* All apps and resources are migrated to or created in the cloud.
* It relies on the internet and cloud computing services providers for computational/IT requirements.

### Hybrid Deployments

Hybrid deploys are done in infrastructure that lives both in the cloud and in on-premises (local?) data centers

It connects on-premises technology and with cloud bases resources

It might be in the process of migrating infrastructure over to the cloud and it allows organizations to scale even further into the cloud while maintaining access to on premises resources

Could be usage as backup for disaster of on-premises infra and for recovery solution

### On-premises deploying

* Orgs use virtualization technologies and apps management to increase effiency
* The resources are never accessed through public internet because they're all on-site and don't require travel through the internet
* It has very low latency because resources are all on-site.
* The setup does not provide many of the benefits of cloud computing.
