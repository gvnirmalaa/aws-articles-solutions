### Welcome AWS Cloud Aspirants !!###

Here in this article, I am opening a multi part series of design solutions to requirements & how it got improvised with time & knowledge

Let us see Part 1

Given scenario is a minimal illustration of one of the use cases. Requirement is to notify the admin/team when there is no tag in an EC2 resource.

**<ins>To simplify</ins>**

1. Create an event bridge rule to check for any EC2 instances in the account
2. Create a lambda function to check a given Tag/Value in EC2 instances
3. Create an SNS topic and group/team email id to notify when tag/value doesn't exists
4. Now when event bridge rules(with cron scheduler) assess the EC2 Instance(s), irrespective of the state(RUNNING or STOPPED) and if lambda function doesn't find the Tag Value[Project:Team or Tag:Value, as applicable]
5. Lambda has to trigger SNS email notification to the group id

**<ins>Solution Design for this scenario:</ins>**

![Part1-Architecture-EnhancedResourceManagement](https://github.com/user-attachments/assets/ae3d836d-6b52-499f-94e5-5a00f4dcf1c4)


**<ins>Benefits around this solution:</ins>**

1. Checks resources at defined periodic intervals, in an automated way
2. EC2 is aimed for monitoring to Tags' existence via a schedule
3. Lambda function will check for defined Tag/Value as expected
4. Teams/Admins are notified even when resource(ec2) are created w/o tags or even if tag/values are removed at a later point in time, as well

In conclusion, this is an automated solution using AWS services efficiently

People who are having urge to suggest better & more efficient ways to do this, hold onto that thought and we will get there in the upcoming series !!
