**<ins>Journey of Enhanced & Mindful Architecture - Part 4</ins>**

Welcome to Part 4, the final part of this series of enhanced solution design(s) - Management & Governance category
Requirement is to efficiently manage & maintain "Creation/Updation" of Resource Definitions in AWS accounts is a minimal illustration of one of the use cases. Ideally expecting Tag:Value in any resource that is created in an AWS account.

**<ins>Part #4 solution break down:</ins>**

1) Enable AWS Config in the required accounts & regions
2) Now activate the AWS Config Rule "Required-Tags" for the resources that will be used in an AWS account
3) Add in an Remediation to enforce compliance against a resource that becomes non-compliant
4) Optionally, a Tagging Policy & SCP can be defined if AWS Organization is active which is an excellent way to maintain & track the resources in an account

**<ins>Solution Design for this scenario:</ins>**
![Part4-Architecture-EnhancedResourceManagement](https://github.com/user-attachments/assets/33881a94-5f5a-4e5d-9d22-21dd8ec24cc1)

**<ins>Benefits around this solution:</ins>**

1) AWS Config provides full history of resource configuration in an AWS account across all regions
2) Once enabled, AWS Config's Required Tags rule, helps in evaluating the tag definition compliance against the expected resources
3) While AWS Organizations SCP are defined & applied at OU level for multiple accounts, a Proactive mechanism, enabling AWS Config Rule - Required Tags is Reactive mechanism to ensure compliance on resources, as per the definition in SCP or Tag policies
4) Advantage of using AWS Config Rule is that a remediation can also be applied when compliance isn't met with

To conclude, Using of solutions from Part #3 & Part #4, which is, defining Tag Policies and/or SCP at OU Level to enforce tagging & also having AWS Config Rule in place for compliance, as a detective operation together ensures the resources are tagged & right definitions are in place

When looked at from a bird's view, Tagging or Grouping resources might like a CouldHave design solution compared to the hard core design of Applications or Products on Cloud. But once all components are requirements are on Cloud, then comes the need for visibility & classification from Cost Optimization, Finops, Observability, Compliance perspectives. Hence having them in place earlier phase of cloud enablement is the real win !!

Hope this series was interesting & informative !!
