<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Build a Virtual Private Cloud

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-vpc)


---

## Build a Virtual Private Cloud (VPC)

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-vpc_2facf927)

---

## Introducing Today's Project!

In this project, I will demonstrate setting up and managing a PC. I'm doing this project to learn cloud networking on AWS

### What is Amazon VPC?

Amazon VPC is a virtual private network and it is useful because it is used to keep resources isolated

In today's project, I used Amazon VPC to create a private virtual network with subnets and internet gateways for internet connection

### Personal reflection

This project took me less then 1 hour to complete

One thing I didn't expect in this project was the depth of the information on the VPCs and the Internet Gateways

---

## Virtual Private Clouds (VPCs)

### What I did in this step

In this step, I will get into the VPC console in AWS because I will use the console to create the VPC

### How VPCs work

VPCs are isolated virtual network hosted by a cloud provider for users to manage their resources and connectivity

### Why there is a default VPC in AWS accounts

There was already a default VPC in my account ever since my AWS account was created. This is because some AWS services require the VPC for them to be funtional; like the EC2 and some databases services, the VPC helps in the connection of services.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-vpc_2facf927)

### Defining IPv4 CIDR blocks

To set up my VPC, I had to define an IPv4 CIDR block, which is a way to assign a whole block of IP addresses.

---

## Subnets

### What I did in this step

In this step, I will laaunch a subnet in the VPC because subnets are used to group resources with similar access rules and restrictions.

### Creating and configuring subnets

Subnets are groupings of resources that have similar access rules and restrictions. There are already subnets existing in my account, one for every Availability Zone.

### Public vs private subnets

The difference between public and private subnets are resources inside the public subnet can comminicate with external resources whereas for private subnet the resources the resources are not to be accesses publicly. For a subnet to be considered public, it has to have access to the internet via the internet gateway

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-vpc_157c4219)

### Auto-assigning public IPv4 addresses

Once I created my subnet, I enabled auto-assign public IPv4 address This setting makes sure that any EC2 instance launched in that subnet will instantly get a public IP address so that it is accessible via the internet and you don't have to create one manually

---

## Internet gateways

### What I did in this step

In this step, I will connect my VPC to the internet using an  internet gateway because the internet gateway will make the applications in the VPC available on the internet.

### Setting up internet gateways

Internet gateways are key to making applications available on the internet. By attaching an internet gateway, your instances can access the internet and be accessible to external users.

Attaching an internet gateway to a VPC means that my VPC is now connected to the internet. If I missed this step then my VPC will not be connected to the internet and cannot be accessed over the internet

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-vpc_4ae90410)

---

## Using the AWS CLI

### What I'm doing in this extension

In this project extension, I will use the AWS CLI (AWS CloudShell) to launch VPC's resources 

### Exploring CloudShell and CLI

VPC resources could also be created with CloudShell, which is a space to run code which has AWS CLI pre-installed. CLI is a command line interface that lets you create, delete and update AWS resources with commands instead of clicking through your console.

### Debugging my setup

To set up a VPC or a subnet, you can use the command "aws ec2 create-subnet --vpc-id VPC-ID --cidr-block ADD-CIDR-BLOCK-HERE" Make sure to avoid errors by including the VPC ID and the CIDR BLOCK

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-vpc_9b2465411)

### Comparing CloudShell vs AWS Console

Compared to using the AWS Console, an advantage of using commands is the CLI can be used for writing scripts. An advantage of using the Console is it has AWS CLI pre-installed Overall, I preferred using the AWS Cloudshell

---

---