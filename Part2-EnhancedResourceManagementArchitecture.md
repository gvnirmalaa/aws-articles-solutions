**<ins>AWS Cloud Solutions - Management & Governance</ins>**

`Requirement is to efficiently manage & maintain "Creation/Updation" of Resource Definitions in AWS accounts is a minimal illustration of one of the use cases. Ideally expecting Tag:Value in any resource that is created in an AWS account.`

**<ins>Part #2 solution break down:</ins>**

1) User/Roles is the access mechanism to any resources which holds access definitions in the form of permissions

2) So, attach policy to IAM users/roles/groups(as appropriately) to allow creation/modification of resources like EC2, RDS or S3 or any other resource to have tag value defined mandatorily

3) Just defining IAM permissions and attaching them to appropriate users/roles will enable monitoring & maintaining the resources for the expected tag:values


**Simple policy pseudocode to restrict any resource creation without tag values:**
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyResourceCreationWithoutTags",
      "Effect": "Deny",
      "Action": "*", 
      "Resource": "*",
      "Condition": {
        "Null": {
          "aws:RequestTag/": "true" 
        }
      }
    }
  ]
}
```

**<ins>Solution Design for this scenario:</ins>**

![Part2-Architecture-EnhancedResourceManagement](https://github.com/user-attachments/assets/83c0657c-879f-40e0-be62-ed87069efea8)


**<ins>Benefits around this solution:</ins>**

1) Requirement being efficient way of handling tags' existence in resources, attaching a permissions policy with IAM user or role or group is most efficient as resources are created through these source points
2) In addition, the policy will take care of the Tag's existence both at creation and also at any update that happens(when it is about to remove the existing tag via code/console/CLI)
3) Instead of attaching manual scheduler to EC2(like the previous solution explained in) Part #1, here the policy can take care of the requirement against any resources any time w/o need of scheduler. For example, RDS, S3 are represented here
4) Part #1 solution works & meets up with the requirements, but it is reactive model, that notifies user/group on tag's deletion and later to this, the team needs to take action to have tags back in place but there the solution is more proactive
5) Few AWS services' like AWS Eventbridge Rules, SNS, Lambda (from previous solution design) has been eliminated in this solution thus cost is optimized too :-)

In conclusion, this is an improvised version of solution design compared to the earlier one !!

Yet again folks, please hold on to your invaluable suggestions to the last part of this series(coming soon) and I am willing to learn & know more possibilities from my fellow aspirants !!
