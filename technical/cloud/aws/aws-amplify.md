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
