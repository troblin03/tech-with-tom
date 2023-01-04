# IAM Access Keys

When interacting with IAM using the command line, we do not use username password and MFA. Instead, we use IAM access keys.

Access keys are long-term credentials used in AWS, specifically for an IAM user. They are called 'long term' because they dont regularly change or rotate. The owner of the credentials has to specifically change them.

An IAM user can have _up to two sets of access keys_. These access keys can be created, deleted, made inactive, or made active. They are formed of two parts:

- **Access Key ID -** Can be accessed multiple times
- **Secret Access Key -** Cannot be accessed beyond the first time AWS gives it to you

When making a request to AWS on the command line, you use both these parts. If you forget or wish to change these access keys you must create a new set of access keys.

The second set of access keys is used when rotating access keys. Typically, IAM Users are the only identity object to use access keys. IAM roles do not.
