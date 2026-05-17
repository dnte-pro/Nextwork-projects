<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Creating a Private Subnet

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-private)


---

## Creating a Private Subnet

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-private_afe1fdbd)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a cloud service by Amazon that allows you to create a private, isolated network within the cloud where you can securely run your applications and resources. It is useful because it gives you full control over your networking environment, including IP address ranges, subnets, routing, and security settings, enabling you to protect your systems, manage traffic flow, and design scalable architectures.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a private subnet that does not connect with the internet via the internet gateway

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is the creation of private subnets and private route tables to suppliment the private subnet

### This project took me...

This project took me 2 hours since I had to start all over

---

## Private vs Public Subnets

The difference between public and private subnets is that resources in the public subnet are accessed over the internet whereas the resources in the private subnet are only accessible within the vpc

Having private subnets are useful because they are used to keep resources that are private within a VPC such as the database

My private and public subnets cannot have the same IP address because IP addresses must be unique within a VPC and it prevents CIDR blocks do not overlap

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-private_afe1fdbd)

---

## A dedicated route table

By default, my private subnet is associated with the VPC's main route table

I had to set up a new route table because the private subnet should not access the Internet Gateway

My private subnet's dedicated route table only has one inbound and one outbound rule that allows traffic only from within the VPC, no internet inbound

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-private_b4b904b5)

---

## A new network ACL

By default, my private subnet is associated with the  default network ACL before setting up an explicit association between the private subnet and another network ACL.

I set up a dedicated network ACL for my private subnet because route table configurations might not be great for security. If any part of the VPC gets compromised the attacker could take advantage of your permissive ACL setup to access or attack the resources in your private subnet!

My new network ACL has two simple rules -no inbound traffic and no outbound traffic

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-private_1ed2cb07)

---

---