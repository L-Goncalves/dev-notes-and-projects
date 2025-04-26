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
