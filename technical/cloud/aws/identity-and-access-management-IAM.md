# Identity & Access Management (IAM)

In an AWS account, the account root user that creates the account is given _unrestricted_ access to all parts of an AWS account. However, in reality we probably want to grant other entities access to your account. This may be users, groups, or other applications. In general, we want to restrict the access that these entities have.

It is **always** best practice to only give the permissions required for the entities to do what they need to do. We refer to this as the principle of least priviliged access.

IAM is a free service that allows us to better manage identities and access across our AWS account.

## The Basics

Every AWS account comes with an IAM service readily available, essentially a permissions 'database' attached to it. IAM is a _globally resilient_ service. This means that any data is always secure across multiple AWS regions for an account.

IAM, like the account root user, can do anything in the AWS account. Within IAM, we can create multiple identities that have varying levels of permissions.

IAM allows us to create three different types of identity objects:

1. **IAM Users -** Represent humans or applications that need access to your account.
2. **IAM Groups -** Collections of related users. May create a 'development team' group and add all the developer IAM roles.
3. **IAM Roles -** Can be used by AWS services, or for granting external access to your account. An example is creating a role that allows EC2 instances to interact with the simple storage service (S3).

Within IAM, we can also create **IAM Policies**. These are essentially objects or documents which can be used to allow or deny access to AWS services. However, they are able to do this only when _attached to an IAM identity object_.

IAM has three main jobs:

1. Manage Identities
2. Authenticate identities to prove you are who you claim to be
3. Authorise access to AWS resources

IAM also does not have direct control on external accounts or users.

## Best Practices

- Only grant IAM policies for what an IAM identitiy needs to do. Follow the principle of _least priviliged access_
- Never use the account root user to alter an AWS account. You should set up an 'admin' IAM user as a pseudo-root account.
