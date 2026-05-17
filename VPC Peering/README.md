<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Peering

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-peering)

---

## VPC Peering

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-peering_88727bef)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service from Amazon Web Services that allows you to create a private, isolated network within the cloud where you can securely run your applications and resources. It is useful because it gives you full control over your networking environment, including IP address ranges, subnets, routing, and security settings, enabling you to protect your systems, manage traffic flow, and design scalable architectures.

### How I used Amazon VPC in this project

I used Amazon VPC to create different cloud resources that isolated the resources according to the needs I had

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the simplicity in setting up VPC peering

### This project took me...

This project took me about forty five minutes give or take

---

## In the first part of my project...

### Step 1 - Set up my VPC

In this step, I will crate two VPCs from scratch whilst using the VPC resource map to create the VPCs easily

### Step 2 - Create a Peering Connection

In this step, I will create a connection between the two VPCs Ihad launched because it will enable the two VPCs to share the resources without using the internet

### Step 3 - Update Route Tables

In this step, I will update the route table; by setting a way for traffic coming from VPC 1 to get to VPC 2.because this enables the VPCs to share resources to and fro each VPC

### Step 4 - Launch EC2 Instances

In this step, I will launch an EC2 instance in each VPC because we will use them to test your VPC peering connection 

---

## Multi-VPC Architecture

I started my project by launching the first VPC using the resource map. I launched the VPC using only one subnet-public subnet only

The CIDR blocks for VPCs 1 and 2 are different. They have to be unique because having the same IP addresses will have the resources overlapping. Having overlapping IP addresses could cause routing conflicts and connectivity issues!

### I also launched 2 EC2 instances

I didn't set up key pairs for these EC2 instances as we will be using EC2 Instance Connect and AWS actually manages a key pair for us! We don't need to manage key pairs ourselves. 

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-peering_11111111)

---

## VPC Peering

A VPC peering connection is a direct connection between two VPCs. A peering connection lets VPCs and their resources route traffic between them using their private IP addresses. This means data can now be transferred between VPCs without going through the public internet.

VPCs would use peering connections to route traffic of their resources using private IP addresses without using the internet.

The difference between a Requester and an Accepter in a peering connection is the Requester is the VPC that initiates a peering connection. As the requester, they will be sending the other VPC an invitation to connect and the Accepter is the VPC that receives a peering connection request! The Accepter can either accept or decline the invitation

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-peering_1cbb1b88)

---

## Updating route tables

After accepting a peering connection, my VPCs' route tables need to be updated because traffic in VPC 1 won't know how to get to resources in VPC 2 without a route in the route table! 

My VPCs' new routes have a destination of the VPC address of the latter VPC. The routes' target was the peering connection we had created earlier.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-peering_4a9e8014)

---

## In the second part of my project...

### Step 5 - Use EC2 Instance Connect

In this step, I will use EC2 Instance Connect to connect to the first Instance and try fixing any error before trying to set a linkage 

### Step 6 - Connect to EC2 Instance 1

In this step, I will use the EC2 Connnect to connect to the Instance with the firast error solved.

### Step 7 - Test VPC Peering

In this step, I will get instance 1 to send test messages to instance 2, then solve errors in Instance to until it can send messages back

---

## Troubleshooting Instance Connect

Next, I used EC2 Instance Connect to connect ro the Instance because we did not use the key-pair as Amazon handles the key pair 

I was stopped from using EC2 Instance Connect as the Instance did not have a public IP address which is necessary when using EC2 Instance Connect to connect to the instance

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-peering_7685490c)

---

## Elastic IP addresses

To resolve this error, I set up Elastic IP addresses. Elastic IP addresses are static IPv4 addresses that get allocated to your AWS account, and is yours to delegate to an EC2 instance.

Associating an Elastic IP address resolved the error because it gives the instance a public IPv4 address that is necessary when using EC2 Instance Connect to connect to the instance

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-peering_45663498)

---

## Troubleshooting ping issues

To test VPC peering, I ran the command ping and the private IPv4 address of the second instance

A successful ping test would validate my VPC peering connection because it would return new lines on the terminal

I had to update my second EC2 instance's security group because it's security group does not alIow inbound from the first instance. I added a new rule that allows inbound traffic from the first instance

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-peering_7a29d352)

---

---