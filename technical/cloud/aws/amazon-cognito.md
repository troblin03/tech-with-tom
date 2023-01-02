# Amazon Cognito

Amazon Cognito can be used to add sign-up and sign-in features and control access to web and mobile applications.

It is highly scalable, even to millions of users. It supports social and enterprise identity federations and has advanced security features to help protect your consumers and businesses.

![image](https://user-images.githubusercontent.com/54938676/210267461-88acab9c-7abf-42fa-973d-98b2ef4c40a0.png)

## The Detail

###### User Pools vs Federated Identities

Cognito User Pools will store user information for your web app. Federated Identities is used to manage user access to _AWS Resources_. Examples may be allowing a user to upload a file to an S3 bucket **user of the app**, not someone managing AWS resources. Federated Identities can establish an identity from a number of providers, including a Cognito User Pool:

![image](https://user-images.githubusercontent.com/54938676/210267868-27bf3f04-e702-48d8-b655-a75a8158758f.png)

###### UserInfo endpoint

The Cognito UserInfo endpoint will respond with user attributes when presented with access tokens issued by your Cognito token endpoint. These user attributes are essentially all the account details stored in your web app (think name, address, saved cards etc).

## Architecture Patterns

(https://aws.amazon.com/blogs/architecture/web-application-access-control-patterns-using-aws-services/)

###### 1. Authenticating clients using an Application Load Balancer

![image](https://user-images.githubusercontent.com/54938676/210268033-217c956a-8130-42bf-9525-c5d3733e6d98.png)

1. The client (user) sends an HTTP request (resource request) to the application load balancer (ALB) without authentication cookies.
2. The ALB will direct this authentication request to Amazon Cognito, where Cognito authenticates the user.
3. The succesful authentication generates an authentication code which is returned to the client and subsequently sent to the application load balancer.
4. Using this authentication code, the ALB interacts with Cognito to generate the access token from the Cognito token endpoint, using this token to access the user attributes from the UserInfo endpoint within Cognito.
5. The ALB will then prepare the authentication session cookie and redirects the clients request. This session cookie is used for any further requests. Any validation of this authentication cookie is done through the ALB.
6. Any validated request is passed onto the backend EC2 instances with the ALB adding HTTP headers (additonal context and metadata about the request).
7. The backend server uses the HTTP header for granular level permission controls.

This pattern is suited to low traffic APIs. It is priced on a number if different factors (hence it can add up in high traffic situations). These include hours, new and active connections. A load balancer is better suited to low-cost, non-differentiated applications (apps with a limited number of endpoints), long-running processes, or applications with ultra-high throughput. The ALB is used to distribute across horizontally scaled server instances.

###### 2. Authenticating clients using Amazon API Gateway

![image](https://user-images.githubusercontent.com/54938676/210269273-00f95097-60fc-4c20-aca6-3625e021142e.png)

1. The client starts the authentication with Amazon Cognite, obtaining the token from the token endpoint.
2. The HTTP request is sent to Amazon API gateway with a header containing the access token
3. The API gateway is configured to have either:
   - The Amazon Cognito User Pool as the authoriser to validate the access token in a REST API request
   - A JSON web token authoriser interacting with the Cognito user pool to validate the access token in a HTTP API request
4. Once validated, the REST or HTTP API request is forwarded to the ALB where:
   - The API Gateway can route HTTP API to a private ALB (one inaccesible to a client not on a VPC) via a VPC endpoint.
   - If a public ALB is in use, the API Gateway can route both REST API and HTTP API to the ALB
5. The API gateway cannot directly route REST API to a private ALB. It needs to route it through a private Network Load Balancer via a VPC endpoint which then targets the private ALB.

This pattern is better suited for a microservice architecture because the API gateway can route the authentication request to wherever it needs to go in the architecture.

###### 3. Authenticating at edge locations

![image](https://user-images.githubusercontent.com/54938676/210271132-7f69cb7c-284f-431c-912a-2c0ecb6f79c9.png)
