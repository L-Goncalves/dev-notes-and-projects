# IAM:

IAM stands for: Identify and Access Management

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

### IAM MFA Overview:

* Strong passwords = higher security for the account
* In AWS, you can setup a password policy:

  * Set a minimum password length
  * Require specific character types
    * Including uppercase letters
    * lowercase letters
    * numbers
    * non-alphabetic characters
  * Allow all IAM users to change their own passworsd
  * Require All users to change their password after some time (password expiration)
  * Prevent password re-use
* Users have access to your account and can possibly change configurations or delete resources in your AWS account
* You want to protect your Root Accounts and IAM users


### IAM Roles for Services

* Some AWS service will need to perform actions on your behalf
* To do so, we will assign permisssions to AWS Sevices with IAM Roles

#### What roles can be created?

* AWS service
* AWS Account
* Web Identity
* SAML 2.0 federation
* Custom Trust Policy

##### AWS Service:

Allow AWS services like EC2, Lambda, or others to perform actions in this account.

##### AWS Account:

Allow entities in other AWS accounts belonging to you or a 3rd party to perform actions in this account.

##### Web Identity:

Allows users federated by the specified external web identity provider to assume this role to perform actions in this account.

##### SAML 2.0 Federation:

Allow users federated with SAML 2.0 from a corporate directory to perform actions in this account.

##### Custom Trust Policy:

Create a custom trust policy to enable others to perform actions in this account.


### IAM Security Tools:

* IAM Credentials Report (account-level)

  * A report that lists all your account's users and their status of various credentials
* IAM Access Advisor (user-level)

  * The Access Advisor shows the service granted permisssions to a user and when those services were last accessed.
  * You can use this information to revise your policies

### IAM Best Pratices:

* Never use Root Account (use account instead)
* 1 AWS user = 1 Physical User
* Assign users to groups and permissions to groups
* Create strong password Policy
* Use and enforce the use of MFA
* Create and use roles to giving permissions to AWS Services
* Don't share access keys
* Use access keys for CLIs and SDKs
