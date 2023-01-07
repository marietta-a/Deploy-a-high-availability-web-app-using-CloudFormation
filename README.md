# Deploy-a-high-availability-web-app-using-CloudFormation
Udacity DevOps Engineer Nano degree project 2

## Expectations
In this project, you’ll deploy web servers for a highly available web app using CloudFormation. You will write the code that creates and deploys the infrastructure and application for an Instagram-like app from the ground up. You will begin with deploying the networking components, followed by servers, security roles and software. The procedure you follow here will become part of your portfolio of cloud projects. You’ll do it exactly as it’s done on the job - following best practices and scripting as much as possible.
Gather your files and submit them via a zipped folder or a GitHub link.

Be sure you have completed all of the project requirements.

Also, check your work against the rubric [here](https://review.udacity.com/#!/rubrics/2556/view) before submitting!


## Problem Statement
### Scenario
Your company is creating an Instagram clone called Udagram.

Developers want to deploy a new application to the AWS infrastructure.

You have been tasked with provisioning the required infrastructure and deploying a **dummy  application,** along with the necessary supporting software.

This needs to be automated so that the infrastructure can be discarded as soon as the testing team finishes their tests and gathers their results.

**Optional** - To add more challenge to the project, once the project is completed, you can try deploying sample website files located in a public S3 Bucket to the Apache Web Server running on an EC2 instance. Though, it is not the part of the project rubric.


## Project Requirements
### Server specs

1. You'll need to create a Launch Configuration for your application servers in order to deploy four servers, two located in each of your private subnets. The launch configuration will be used by an auto-scaling group.

2. You'll need two vCPUs and at least 4GB of RAM. The Operating System to be used is Ubuntu 18. So, choose an Instance size and Machine Image (AMI) that best fits this spec.

3. Be sure to allocate at least 10GB of disk space so that you don't run into issues. 


### Security Groups and Roles

1. Since you will be downloading the application archive from an **S3 Bucket**, you'll need to create an **IAM Role** that allows your instances to use the S3 Service.

2. Udagram communicates on the default **HTTP Port: 80**, so your servers will need this inbound port open since you will use it with the **Load Balancer** and the **Load Balancer Health Check**. As for outbound, the servers will need unrestricted internet access to be able to download and update their software.

3. The load balancer should allow all public traffic **(0.0.0.0/0)** on **port 80** inbound, which is the default **HTTP port**. Outbound, it will only be using **port 80** to reach the internal servers.

4. The application needs to be deployed into private subnets with a **Load Balancer** located in a public subnet.
One of the output exports of the **CloudFormation script** should be the public URL of the **LoadBalancer. Bonus points** if you add **http://** in front of the load balancer **DNS Name** in the output, for convenience.

# Architecture 
![Architecture](architecure.jpeg "architecture")

# Deployment

1. 
