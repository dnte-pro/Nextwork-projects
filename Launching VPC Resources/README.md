<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launching VPC Resources

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-ec2)

---

## Launching VPC Resources

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-ec2_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service from Amazon Web Services that allows you to create a private, isolated network within the cloud where you can securely run your applications and resources. It is useful because it gives you full control over your networking environment, including IP address ranges, subnets, routing, and security settings, enabling you to protect your systems, manage traffic flow, and design scalable architectures.

### How I used Amazon VPC in this project

I used Amazon VPC to create more cloud resources

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the introduction of VPC Resource map which makes the creation of VPC resources easier

### This project took me...

This project took me about 2 hours, "football breaks😂"


---

## Setting Up Direct VM Access

Directly accessing a virtual machine means logging into and managing the operating system or software of the machine as if you were using it in front of you, but over the internet.



### SSH is a key method for directly accessing a VM

SSH traffic means once SSH has established a secure connection between you and the EC2 instance, all data transmitted (including your commands and the responses from the instance) is encrypted. This encryption makes SSH an ideal method for securely exchanging confidential data e.g. login credentials!

### To enable direct access, I set up key pairs

Key pairs help engineers directly access their virtual machines, like EC2 instances.
How key pairs work is that they consist of two cryptographic keys: one private and one public. The public key is installed on the virtual machine, and the private key remains with the user. When you attempt to connect, the machine uses the public key to create an encrypted challenge that can only be decrypted with the private key. Key pairs make sure that access to your EC2 instances is secure and authenticated.

A private key's file format means the format in which key pairs come in. My private key's file format was .pem which stands for Privacy Enhanced Mail, started off as a way to secure emails but has since become the go-to format for managing cryptographic keys because it is supported by many different types of servers e.g. EC2 instances!

---

## Launching a public server

I had to change my EC2 instance's networking settings by choosing the VPC I had earlier created and also the public subnet to launch the EC2 on

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-ec2_88727bef)

---

## Launching a private server

My private server has its own dedicated security group because it has to filter the traffic source from which data packets are sourced

My private server's security group's source is the public security group which means it restricts access to a much smaller group of trusted resources, rather than allowing potentially any IP address on the internet (0.0.0.0/0) to access your instance.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-ec2_4a9e8014)

---

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I used the VPC Resource map. With VPC resource map, you can quickly understand the architectural layout of a VPC, like the number of subnets, which subnets are associated with which route table, and which route tables have routes to an internet gateway.

A VPC resource map is a built-in feature in the console that creates an interactive diagram of your VPC. It provides a visual overview of all your network resources and how they connect, sparing you from the tedious and error-prone task of tracking each piece manually 

My new VPC has a CIDR block of 10.0.0.0/24 it is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because VPCs are isolated networks within AWS, meaning they don’t interact with each other unless you explicitly set up connectivity between them.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-ec2_1cbb1b88)

---

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options:2 or 1 public subnetThis was because public subnets are limited to ensure manageable exposure to the internet.

The set up page also offered to create NAT gateways, which are gateways  that let instances in private subnets access the internet for updates and patches, while blocking inbound traffic

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-ec2_8ee57662)

---

---