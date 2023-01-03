# Create an Amazon Cognito User Pool using AWS Amplify CLI

We can configure tghe AWS Amplify CLI to interact and manage the cloud services for our web app. Within this, the authentication module provides Authentication APIs and building blocks for developers who want to create authentication experiences.

###### Setup

Within Cloud9 We need to first install the CLI using

```
npm install -g @aws-amplify/cli
```

Following this you initialise the Amplify CLI.

###### How to do it

First, we specify that we want to add a user pool using

```
amplify add auth
```

Following this we configure to our liking and then simply commit our changes. This will provision the amplify backend resources and kick off a new build.
