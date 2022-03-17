# Identity and Access Management (IAM)
Root account created by default, shouldn't be used or shared.

## Users
Users are people within your organization, and can be grouped. Users don't have to belong to a group, and users can belong to multiple groups.

## Groups
Groups can only contain users, not other groups.

## Roles
Some AWS services will need to perform actions on your behalf. To do so, we will assign permissions to AWS services with IAM Roles. <br>
Common roles:
* EC2 Instance roles <br>
* Lambda function roles <br>
* Roles for CloudFormation <br>

## Permissions
Users or groups can be assigned JSON documents called policies. These policies define the permissions of the users. <br>
In AWS you apply the **least privilege principle**: Don't give more permissions than a user needs.

```json
{
	"Version": "2012-10-17",
	"statement": [
		{
			"Effect": "Allow",
			"Action": "ec2:Describe*",
			"Resource": "*"
		},
		{
			"Effect": "Allow",
			"Action": "elasticloadbalancing:Describe*",
			"Resource": "*"
		},
		{
			"Effect": "Allow",
			"Action": [
				"cloudwatch:ListMetrics",
				"cloudwatch:GetMetricStatistics",
				"cloudwatch:Describe*"
			],
			"Resource": "*"
		}
	]
}
```

## IAM Policy Structure
Consists of: 
* Version<br>
* Id (Optional) <br>
* Statements (Required) <br>
	* Sid: Id for the statement (Optional).
	* Effect: Whether the statement allows or denies access (Allow or Deny).
	* Principal: Account/User/Role to which this policy is attached to.
	* Action: List of actions this policy allows or denies.
	* Resource: List of resources to which the actions applied to.
	* Condition: Conditions for when this policy is in effect. (Optional)

## IAM Password Policy
Strong passwords lead to higher security for your account. <br>
In AWS, you can set up a password policy:
* Set a minimum password length
* Require specific character types
	* Uppercase
	* Lowercase
	* Numbers
	* Non-Alphanumeric
* Allow all IAM users to change their own passwords
* Require users to change their password after some time (Password expiration)
* Prevent password re-use

## Multi Factor Authentication (MFA)
Users have access to your account and can possibly change configurations or delete resources in your AWS account. <br>
You want to protect your root accounts and IAM users.

### Main benefit of MFA:
If a password is stolen or compromised, the account is not compromised.

### MFA devices options in AWS
* Virtual MFA device (Support for multiple tokens on a single device) <br>
* Universal 2nd Factor (U2F) Security key (Support for multiple root and IAM users using a single security key) <br>
	* E.G. YubiKey by Yubico (3rd party). 
* Hardware Key Fob MFA device or Hardware Key Fob MFA device for AWS GovCloud <br>

## How can users access AWS?
To access AWS, you have three options:
* AWS management console (Password + MFA) <br>
* AWS CLI (Access Keys) <br>
* AWS SDK (Access Keys) <br>

Access keys are generated through the AWS console. Users manage their own access keys

## What is the AWS CLI?
A tool that enables you to interact with AWS services using commands in your command line shell. <br>
Direct access to the public APIs of AWS services. You can develop scripts to manage your resources.

## What is the AWS SDK?
AWS software development kit. Language-specific APIs. Enables you access and manage AWS services programatically. <br>
Embedded within your application. Supports:
* SDKs (JavaScript, PHP, Go) <br>
* Mobile SDKs (Android, iOS) <br>
* IoT Device SDKs (Embedded C, Arduino) <br>
