# AWS Accounts

When starting with AWS, you may start with only one AWS account. However, as projects get larger and more complex, you are likely to be using _many_ accounts to manage your infrastructure.

> An AWS Account is a container for identities (users) and Resources

In leyman's, an AWS account contains users that you log in with and resources that you distribute throughout these users.

Every AWS account must have a unique e-mail address. The e-mail address is used to create an **account root user**. Initial creation makes the account root user with nothing contained within it. 
The root user has complete control over the account and resources within it - it cannot be restricted.

###### Managing Identities

There's likely to be a seperate md file for Identity and Access Management (IAM), but here it is used to manage the identities within an AWS account.

Within your account IAM Users, Groups, and Roles can be creates and given full or limited permissions. This is defined by the account root user. All of these IAM identities start with no access to resources within the account and remain this way until otherwise specified.

###### Account Boundary

AWS is excellent at retaining _account boundaries_. This is important to contain the impact caused by bad actors or admin errors. As such, AWS infrastucture will often be architected to have seperate accounts for seperate things (dev, prod, test etc).

By default, access to AWS resources within an account are denied from outside the account. However, this can be changed to explicitly allow external access.

## Best Practices

- Use multiple AWS accounts to manage your infrastructure, allowing containerised fault management.
- Set up MFA on your AWS Accounts to increase their security
- Explicitly set AWS Budgets on Accounts to protect against unintended costs
- Create IAM identities within your AWS accounts to manage parts of the AWS account. (E.g. IAMADMIN with admin permissions).
- We can view AWS accounts as disposable because they operate as containers, isolating resources within them. Hence, we can make as many as we need.
