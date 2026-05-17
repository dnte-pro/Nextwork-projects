<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Monitoring with Flow Logs

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-monitoring)

---

## VPC Monitoring with Flow Logs

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_3e1e79a1)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service from Amazon Web Services that allows you to create a private, isolated network within the cloud where you can securely run your applications and resources. It is useful because it gives you full control over your networking environment, including IP address ranges, subnets, routing, and security settings, enabling you to protect your systems, manage traffic flow, and design scalable architectures.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to monitor FLow logs in a VPC network and visualie them with Log Insights

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the use of various AWS resources that work together

### This project took me...

This project took me about two hours

---

## In the first part of my project...

### Step 1 - Set up VPCs

In this step, I will create two VPCs and connect them by peering and later monitor the traffic in and out with Flow Logs and CloudWatch

### Step 2 - Launch EC2 instances

In this step, I will create  EC2 instances in each VPC so that they can send data to each other later in the project, which gives us network activity to monitor.

### Step 3 - Set up Logs

In this step, I will set up a way to track all inbound and outbound network traffic and set up a space that stores all the records using VPC Flow Logs.

### Step 4 - Set IAM permissions for Logs

In this step, I will give VPC Flow Logs the permission to write logs and send them to CloudWatchand finish setting up your subnet's flow log because VPC Flow Logs doesn't have the permission to write logs and send them to CloudWatch.

---

## Multi-VPC Architecture

I started my project by launching two VPCs each with one public subnet and customised the CIDR blocks for both VPCs to ensure they are not the same. 

The CIDR blocks for VPCs 1 and 2 are.different(10.1.0.0/16 and 10.2.0.0/16 respectively). They have to be unique to prevent the IP addresses from overlapping which can create routing conflicts and connectivity issues.

### I also launched EC2 instances in each subnet

My EC2 instances' security groups allow all ICMP traffic from all IP addresses. This is because we are going to ping the instance which requires the security group to all ICMP traffic from all IP addresses.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_e7fa8775)

---

## Logs

Logs are like a diary for your computer systems. They record everything that happens, from users logging in to errors popping up. It's the go-to place to understand what's going on with your systems, troubleshoot problems, and keep an eye on who’s doing what.

Log groups are a big folder in AWS where you keep related logs together. Usually, logs from the same source or application will go into the same log group, BUT logs are also region-specific. This means log data gets created and saved in the region it was created, although you can use CloudWatch dashboards to bring together logs from different regions.

### I also set up a flow log for VPC 1

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_e8398869)

---

## IAM Policy and Roles

I created an IAM policy because VPC Flow Logs by default don't have the permission to record logs and store them in the CloudWatch log group. Creating the policy makes sure that the VPC can now send log data to your log group

I also created an IAM role in order to assign the IAM policy that I created to the new role. The role is then assigned to VPC Flow Logs

A custom trust policy is used to very narrowly define who can use a role.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_4334d777)

---

## In the second part of my project...

### Step 5 - Ping testing and troubleshooting

In this step, I will set up VPC peering and generate network traffic by trying to get  instance in VPC 1 to send a message to the instance in VPC 2 

### Step 6 - Set up a peering connection

In this step, I will set up a connection link between the two VPCs which will allow the two VPCs to communicate via their private IP addresses.

### Step 7 - Analyze flow logs

In this step, I will review the flow logs recorded aboout VPC 1's public subnet and analyse the flow logs to get some insights 

---

## Connectivity troubleshooting

My first ping test between my EC2 instances had no replies, which means there is no VPC peering connection that directly connects VPCs 1 and 2.


![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_99d4ba42)

I could receive ping replies if I ran the ping test using the other instance's public IP address, which means Instance 2 is correctly configured to respond to ping requests, and Instance 1 can actually communicate with Instance 2 if it traffic goes across the public internet!

---

## Connectivity troubleshooting

Looking at VPC 1's route table, I identified that the ping test with Instance 2's private address failed because there is no VPC peering which allows instances to communicate with their private IP addresses, the reason why we cannot ping to the private IP address.

### To solve this, I set up a peering connection between my VPCs

I also updated both VPCs' route tables so that they allow VPC peering which allows communication of the two VPCs via their private IP addresses

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_7316a13d)

---

## Connectivity troubleshooting

I received ping replies from Instance 2's private IP address! This means that instance 1 can communicate with instance 2 via the private IP address

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_4ec7821f)

---

## Analyzing flow logs

Flow logs tell us about the bytes that were sent successfully from a given IP address and to a destination address using a TCP protocol of a given port and whether the packets were accepted or denied

For example, the flow log I've captured tells us 344 bytes of data were sent successfully from the IP address 147.185.132.233 to 10.1.13.148 using TCP protocol on port 22, with 44 packets transferred and the traffic was allowed ("ACCEPT").

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_d116818e)

---

## Logs Insights

Logs Insights is CloudWatch feature that analyzes your logs. In Log Insights, you use queries to filter, process and combine data to help you troubleshoot problems or better understand your network traffic!

I ran the query Top 10 byte transfers by source and destination IP addresses . This query analyzes the top 10 biggest data transfers between IP addresses in the network! It helps find out which resources are moving the most data, which uncovers the busiest traffic routes in the network.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-monitoring_3e1e79a1)

---

---