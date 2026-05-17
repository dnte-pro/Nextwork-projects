<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Access S3 from a VPC

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-s3)

---

## Access S3 from a VPC

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-s3_3e1e79a2)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service from Amazon Web Services that allows you to create a private, isolated network within the cloud where you can securely run your applications and resources. It is useful because it gives you full control over your networking environment, including IP address ranges, subnets, routing, and security settings, enabling you to protect your systems, manage traffic flow, and design scalable architectures.


### How I used Amazon VPC in this project

I used Amazon VPC to create different cloud resources that isolated the resources according to the needs I had. 

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the simplicity of using Amazon CLI

### This project took me...

This project took me about 45 minutes

---

## In the first part of my project...

### Step 1 - Architecture set up

In this step, I will create a VPC from scratch and launch an EC2 instance into the VPC.

### Step 2 - Connect to my EC2 instance

In this step, I will connect with the EC2 instance I had launched earlier

### Step 3 - Set up access keys

In this step, I will create Access keys to give the EC2 instance access to the aws Environment

---

## Architecture set up

I started my project by launching a VPC and then launched an EC2 instance with modified security group

I also set up S3 bucket and uploaded some files to access them in the EC2 instance

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-s3_4334d777)

---

## Running CLI commands

AWS CLI is a special software that is installed and ran on the local computer to control AWS services directly from the command line i.e. the terminal. I have access to AWS CLI to automate tasks and manage AWS resources efficiently using scripts, it is essential for managing your cloud environment in an efficient way.

The first command I ran was "aws s3 ls". This command is used to list all the s3 buckets in the account.

The second command I ran was "aws configure" This command is used to show the credentials of the account: AccessKeys and secret access keys

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-s3_e7fa8776)

---

## Access keys

### Credentials

To set up my EC2 instance to interact with my AWS environment, I configured aws configure with the access keys and the secret access key for the instance to communicate with the AWS applications and services

Access keys are credentials for applications and other servers to log into AWS and talk to the AWS services/resources.

Secret access keys are passwords that pairs with your access key ID (your username) to access AWS services anyone who has it can access your AWS account.

### Best practice

Although I'm using access keys in this project, a best practice alternative is to use IAM role with the necessary permissions and then attaching that role to your EC2 instance.

---

## In the second part of my project...

### Step 4 - Set up an S3 bucket

In this step, I will launch a bucket in S3 to access it from the EC2 instance and check the object in the S3 Bucket

### Step 5 - Connecting to my S3 bucket

In this step, I will setp the EC2 instance to communicate with the S3 bucket 

---

## Connecting to my S3 bucket

The first command I ran was "aws s3 ls". This command is used to list all the s3 buckets in the account.

When I ran the command "aws s3 ls" again, the terminal responded with the S3 buckets in my account. This indicated that the instance can now communicate with the S3 (AWS Services).

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-s3_4334d778)

---

## Connecting to my S3 bucket

Another CLI command I ran was aws s3 ls s3://nextwork-vpc-project-yegon which returned a list of objects in my s3 bucket that I had placed them earlier

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-s3_4334d779)

---

## Uploading objects to S3

To upload a new file to my bucket, I first ran the command "sudo touch /tmp/test.txt". This command creates a file "test.txt" in the tmp folder

The second command I ran was "aws s3 cp /tmp/test.txt s3://nextwork-vpc-project-yegon"This command will copy  the test.txt file to the s3 bucket

The third command I ran was "aws s3 ls s3://nextwork-vpc-project-yegon" which validated that the test.txt file that was created earlier has been uploaded to the S3 bucket

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-s3_3e1e79a2)

---

---