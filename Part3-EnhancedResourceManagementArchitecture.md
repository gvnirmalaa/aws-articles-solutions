Welcome to Part 3 of the enhanced solution design(s) - Management & Governance category

`Requirement is to efficiently manage & maintain "Creation/Updation" of Resource Definitions in AWS accounts and below representation is a minimal illustration of one such use case(s). Ideally expecting Tag:Value in any resource that is created in an AWS account.`

**<ins>Part #3 solution break down:</ins>**

1) Create a service control policy to each of the organizational unit(s), as accordingly.
2) Tagging policies are again rules/permissions defined w.r.t tag:value expected or allowed for resources
3) Now, attach the Tagging & SCP policy against the OU under the AWS Organizations. This will together enforce Tagging strategies enforcement for resources and SCPs will ensure the compliance of tags on resources
4) Advantage is that different OUs can have different policies/scp attached as per the environment or account perspective

**<ins>Solution Design for this scenario:</ins>**
![Part3-Architecture-EnhancedResourceManagement](https://github.com/user-attachments/assets/2f2cba24-cc23-4fbf-aec1-4e07d7675d7b)

**<ins>Benefits around this solution:</ins>**

1) Centralized operation, control & execution; There is only one SCP to amend for many accounts under an OU, which is much simplified solution
2) Easy customization as per the requirement for each OUs, for example, DEV, Security, Sandbox etc
3) There aren't any SCPs or policies at individual account level, it is rather retained at OU level
4) If required, a detailed fine grained policies for tags can be defined at individual user/role/group level

If the organization has AWS accounts more than tens or hundreds then obviously they would have been grouped/classified with AWS Organizations and organizational units. This is a most promising way to enforce tagging for organizational units.

As promised, there is yet another part to be shared to finish this series and hence hold on !!
