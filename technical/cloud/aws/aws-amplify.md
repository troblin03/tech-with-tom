# AWS Amplify

AWS Amplify allows users to build, ship, and host full-stack applications on AWS. You can create an app backen, build a frontend UI, or just use it to host a web app.

## Hosting a Web App

Amplify allows you to connect to your repository from a list of pre-approved repos. Following this you can configure your build settings for the front and back end.

It is then incredibly easy to deploy your app. Moreover, if it is a static website then Amplify can host it.

###### Setup

1. Add a remote repository containing your code. This is likely to be AWS CodeCommit or GitHub.
2. Select the repository branch
3. Configure your build settings (steps will vary depending on your app)
   a. Pick a name for your app
   b. Select or create the backend environment to support the app
   c. Select an IAM role allowing Amplify Hosting to access resources
4. Save and deploy

## Amplify Authentication UI

By adding `/auth` to our website domain, we can visit the 'sign in' page of our account. Here, we can begin creating an account that will be fully managed and stored using Cognito.

Cognito will then send an automated e-mail containing your verification code.

After logging in, we receive the following error:

![image](https://user-images.githubusercontent.com/54938676/210381926-4bd7727c-dafd-4810-900c-47b202d1165e.png)

This is because our app does not yet know what to do with the authorisation it has received from Cognito.
