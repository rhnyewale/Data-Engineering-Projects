# Introduction to the Cloud and AWS

Welcome to this lesson on Introduction to the Cloud and AWS. You'll learn about the cloud infrastructure ecosystem and understand how to use essential tools for computing, storage, and analytics through one of the biggest providers of cloud computing, Amazon Web Services.

# What is Cloud Computing?
**Cloud computing: ** the practice of using a network of remote servers hosted on the Internet to store, manage, and process data, rather than a local server or a personal computer.

The arrival of cloud computing completely changed the way we deploy our technology, providing powerful access to instant and scalable computing power to enterprises, startups, and developers alike. Whether you need servers to host a web application, reliable storage for your data, or machines to train machine learning models, it's easy to see the advantage of relying on the cloud rather than utilizing your personal computer or local servers.

## Cloud Computing Advantages
* Eliminate need to invest in costly hardware upfront
* Rapidly provision resources
* Provide efficient global access

For one, you no longer have to invest in lots of hardware upfront. No need to worry about whether you are paying for more than you'll need or what to do if you need to scale a lot more later on. Cloud computing makes this as easy and clicking a few buttons to scale your resources up or down.

It's significantly faster provisioning the resources you need through the cloud versus the time it would take to gather and build up the hardware you'd need to provide the same support. This allows you and your team, or company, to develop and experiment at a much faster rate.

Lastly, you can provide efficient access to your applications around the world by spreading your deployments to multiple regions.

# Amazon Web Services
Amazon Web Services is one of the largest providers in the cloud computing industry, with over 140 services in compute, storage, databases, networking, developer tools, security, and more. In this lesson, we'll learn about a few essential tools and services in AWS and practice using them. These services can be accessed in three different ways: the AWS Management Console, the Command Line Interface (CLI), or Software Development Kits (SDKs), which can be used in combination.

We'll start with the AWS Management Console, which is the web user interface. The AWS CLI is a useful way to control and automate your services with code, and SDKs allow you to easily integrate services with your applications through APIs built around specific languages and platforms.

# Create an IAM Role
Here, you'll create an IAM role that you will later attach to your Redshift cluster to enable your cluster to load data from Amazon S3 buckets.

1. Sign in to the AWS Management Console and open the IAM console at https://console.aws.amazon.com/iam/.
2. In the left navigation pane, choose Roles.
3. Choose Create role.

# Create Security Group
Create a security group you will later use to authorize access to your Redshift cluster.

1. Go to your Amazon EC2 console and under Network and Security in the left navigation pane, select Security Groups
2. Choose the Create Security Group button
3. Enter redshift_security_group for Security group name
4. Enter "authorize redshift cluster access" for Description
5. Select the Inbound tab under Security group rules
6. Click on Add Rule and enter the following values:

* Type: Custom TCP Rule.
* Protocol: TCP.
* Port Range: 5439. The default port for Amazon Redshift is 5439, but your port might be different. See note on determining your firewall rules on the earlier "AWS Setup Instructions" page in this lesson.
* Source: select Custom IP, then type 0.0.0.0/0.
* Important: Using 0.0.0.0/0 is not recommended for anything other than demonstration purposes because it allows access from any computer on the internet. In a real environment, you would create inbound rules based on your own network settings.

7. Choose Create





