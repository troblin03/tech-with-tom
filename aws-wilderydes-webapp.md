# AWS Wild Rydes Serverless - Web Application
## Background
A document to record what I do in the web application portion of the AWS serverless workshop.

Wild Rydes Serverless workshops can be found at: https://github.com/aws-samples/aws-serverless-workshops

Web app workshop in question: https://webapp.serverlessworkshops.io/

## Architecture
###### Diagram
<img width="1312" alt="wildrydes-complete-architecture" src="https://user-images.githubusercontent.com/54938676/207636226-33e2eb02-0405-49d3-864c-bbd8db35d721.png">

###### Explanation
AWS Amplify
Amazon Cognito
Amazon API Gateway
AWS Lambda
Amazon DynamoDB

## Set-Up
###### Region Set-Up
Due to the workshop requirements, I connected to the Frankfurt (eu-central-1) AWS Region.

###### IDE
We'll also be coding in an AWS Cloud9 IDE. Cloud9 is a cloud-based IDE giving you an environment to write code as with any other IDE.
The key benefits of Cloud9 are:
- **Code with just a browser -** Cloud9 allows a user to code within the browser only, removing the requirement of installing and maintaining a desktop IDE
- **Code together in realt time -** Within Cloud9 your development environment can be shared with you team quickly and efficiently. This allows real time collaboration and pair programming.
- **Start new projects quickly -** You can immediately provision EC2 server space, allowing support for over 40 programming languages
- **Builde serverless applications with ease -** Definitely should be useful for this workshop! Essentially Cloud9 is an extremely easy space to develop serverless applications, allowing you to define resources, debug, and switch between local and remote execution of your code.

###### Dev Environment Set-Up
Once we enter the start-up screen, we use the following settings:
- _Environment Type_ - New EC2 instance. Specifies what the IDE will use to run the code. The alternative option is using existing compute space. perhaps a user would have spare capacity on an EC2 instance that they may want to use.
- _Instance type_ - t2.micro. As an extension of the above, we need to specify instance sizes. The three default options are micro, small, and large. However, there are more available.

Once the Cloud9 IDE has been spun up, the first code we run (ever) in AWS is:
```
aws sts get-caller-identity
```
And the output indicates my Account, UserID, and Arn(?)

## Static Web Hosting
Here, we'll be using AWS Amplify to host the static resources for our web application. Over the course of the workshop, additional dynamic functionality is brought in.
###### AWS Amplify
AWS Amplify essentially allows developers to create a full stack app quickly. There are three main bits of functionality:
1. Create an app backend - Giving the app real-time and offline functionality in a few clicks
2. Build a frontend UI - Low-code solution to building UI and connecting it to a Cloud Backend
3. Host a web app - Easy to deploy your web app to the AWS Content Delivery Network

###### Repository
Within Cloud9, we can call on AWS CodeCommit to host the web app's repo.

We start by creating a new repository in CodeCommit
```
aws codecommit create-repository \--repository-name wild-rydes
```
Then we clone the workshop repo from GitHub
```
git clone https://github.com/aws-samples/aws-serverless-webapp-workshop.git
```
Then navigate into the workshop repo directory using cd:
```
cd aws-serverless-webapp-workshop
```
Then we split out the WildRydesVue code into its own branch:
```
sudo yum install git-subtree -y
git subtree split -P resources/code/WildRydesVue -b WildRydesVue
```
The first line is a workaround since subtree as a command isn't installed by defoult with git in Cloud9 environments
###### Deploy
Now we get to use AWS Amplify to deploy our code.

We click 'get started', we can choose from a number of different git providers from which to deploy. As detailed in the last section, we used AWS CodeCommit. Likely for personal projects I'll use GitHub but since this is just a part of this workshop I'll proceed with AWS CodeCommit.

We can then select from the repos we have stored in AWS CodeCommit. Here, ours is called wild-rydes (as defined in the previous section).

Once we have made the selection, we can see that Amplify automatically recognises our backend and frontend frameworks
```
Frontend framework
Vue
Backend framework
Amplify
```
Then, we need to create a new backend environment for the app within amplify. Here, we call it prod.

In a world where this were in a larger organisation, we wouldn't want anyone associated with our AWS Root User to be able to deploy the backend. As such, we create a new service role and name it wildrydes-backend-role.

Once this is created, we attach an IAM policy giving it CodeCommit Read-Only permissions. This follows the AWS principle of giving users the least amount of permissions required to do their role. Thus, we have a IAM role that has permissions to deploy the Amplify backend from reading a CodeCommit repo.

We select this role and finally click 'save and deploy' in AWS Amplify.
###### Modify
One of the great things about AWS Amplify is its ability for continuous deployment (CD).

In this example, I modified the html title and pushed the new index.html file into the CodeCommit repo and almost immediately, the AWS Amplify console was building the website again.
