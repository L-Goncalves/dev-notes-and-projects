## Types of Cloud Computing

* Infrastructure as a Service (IaaS):
  * Provide building blocks for cloud IT.
  * Provides networking, computers, data storage space.
* Platform as a Service (PaaS)
  * Removes the need for your organization to manage the underlying infrastructure.
* Software as a Service (SaaS)
  * Completed product that is run and managed by the service provider (AWS)

## Example of Cloud Computing Types

* Infrastructure as a Service (IaaS):

  * Amazon EC2 (on AWS)
  * GCP, Azure, Rackspace, Digital Ocean, Linode
* Platform as a Service (PaaS)

  * Elastic Beanstalk (on AWS)
  * Heroku, Google App Engine (GCP), Windows Azure (Microsoft).
* Software as a Service (SaaS):

  * Many AWS services (ex: Rekognition for Machine Learning)
  * Google Apps (Gmail), Dropbox, Zoom

## Pricing of the Cloud - Quick Overview

* AWS has 3 pricing fundamentals, following the pay-as-you-go pricing model
* Compute:
  * Pay for compute time
* Storage:
  * Pay for data stored in the Cloud
* Data transfer OUT of the Cloud
  * Data transfer IN is free

## AWS Cloud Use Cases

* AWS enables you to build sophisticated, scalable applications.
* Applicable to a diverse set of industries.

## AWS Global Infrastructure

AWS is a global service, we have regions, availability zones, data centers and points of presence.

All of this data can be seen at https://infrastructure.aws

## AWS Regions

* AWS has Regions all around the world
* Names can be us-east-I, eu-west-3 ... etc..
* **A Region is a cluster of data centers**
* Most AWS Services are region-scoped

## AWS Availability Zones

* Each region has many availablility zones (usually 3, minimum is 3 and max is 6).
* Each availability zone (AZ) is one or more discrete data centers with redudant power networking, and connectivity
* They're separate from each other, so that they're isolated from disasters
* They're connected with high bandwidth ultra-low lantency networking

## AWS Points of Presence (Edge Locations)

* They are data centers located close to end users to speed up delivery of content and reduce latency.
* AWS uses Edge Locations to cache and deliver content closer to users.

# IAM:
IAM is a global service and no region needs to be selected

## IAM: Users & Groups

* Root account is created by default and should not be used or shared (it is bad practice)
* Users are people within the organization and can be grouped to have same rules.
* Groups: can only contain users, not other groups (subgroups not allowed)
* Users don't have to belong to a group, and can belong to multiple groups

## IAM: Permissions

* Users or Groups can be assigned through JSON documents called Policies.
  Example:
  ```json
  {
   "Version": "2012-10-17", 
   "Statement": [
    {
      "Effect": "Allow",
      "Action": "ec2:Describe"
    },
    {
      "Effect": "Allow",
      "Action": "elatiscloadbalancing:Describe*",
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": [
  	"cloudwatch:ListMetrics",
          "cloudwatch:GetMetricStatistics",
          "cloudwatch:Describe",
       ],
      "Resource": "*"
    },
   ]
  }
  ```

### IAM Policies Structure:

* Consists of
  * Version: Policy language version, always include "2012-10-17".
  * Id (optional): Identifier of Policy
  * Statement (required): Identifier of Policy


* Statements Consists of
  * Sid (optional): an identifier for the statement.
  * Effect (Allow, Deny): wether the statement allows or denies
  * Principal: account/user/role to which this policy is applied to
  * Action: list of actions this policy allows or denies
  * Resource: list of resources to which the actions applied to
  * Condition(optional): conditions for when this policy is in effect 

* These policies define the permissions of the users
* In AWS you apply the least privilege principle: don't give users more permissions than they actually need!

### Inline Policy:
* Attached to only a user


### IAM MFA:
