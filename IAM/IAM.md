# Identity and Access Management (IAM)
Root account created by default, shouldn't be used or shared.

## Users
Users are people within your organization, and can be grouped. Users don't have to belong to a group, and users can belong to multiple groups.

## Groups
Groups can only contain users, not other groups.

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
