# Create-a-Serverless Web Application

## Overview

In this tutorial, I create a simple serverless web application that lets users ride unicorns on WildRydes. The web application provides users with an HTML-based user interface to specify the location where they want to be picked up, and creates an interface on the backend with a RESTful web service to submit the request and provide a nearby unicorn. The application also provides components to allow users to register with the service and sign in before requesting a unicorn ride.

## Application Architecture

For the application architecture, I used AWS Lambda, API Gateway, DynamoDB, Amazon Cognito, and AWS Amplify.

![Serverless_Architecture d930970c77b382db6e0395198aacccd8a27fefb7](https://user-images.githubusercontent.com/122367884/214868606-b6ff9fec-72e4-4b1e-a078-7b8ab7d12add.png)

## Step 1: Static web hosting with continuous provisioning

In the first step, I configure AWS Amplify to host the static resources for your web application with integrated continuous provisioning.

![Amplify_Wild_Rydes 1760839c5336d01cd6ac6eabb5d2ad8a37c3304a](https://user-images.githubusercontent.com/122367884/214870924-f09e816e-32a7-4a7a-ab49-0b5e1389c642.png)

### Select a region

I select eu-central-1 (Frankfurt) as the region in which the web application is to be deployed.

### Create a Git repository

To manage my source code I decided to use AWS CodeCommit. In it I create a new repository called "wildrydes-site" and clone the repository. In the terminal window I then run the following command and HTTPS URL: 

$ git clone https://git-codecommit.us-east1.amazonaws.com/v1/repos/wildrydes-site

### Fill out the Git repository

I change to the directory in my repository and copy the static files from S3:

aws s3 cp s3://wildrydes-us-east-1/WebApplication/1_StaticWebHosting/website ./ --recursive

I then transfer the data to CodeCommit.

### Enable Web Hosting with the AWS Amplify Console

Now I'm deploying the web application with Amplify.

![Amplify App](https://user-images.githubusercontent.com/122367884/214875776-57db436d-7d11-4dae-8275-a1db2fd070f0.jpg)

If everything has worked i can now access this page:

![giddy](https://user-images.githubusercontent.com/122367884/214876345-2fe340d9-2525-4cd5-9873-738c7715f4bf.jpg)


