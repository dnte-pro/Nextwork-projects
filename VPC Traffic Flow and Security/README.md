<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# VPC Traffic Flow and Security

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-security)

---

## VPC Traffic Flow and Security

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-security_92b0b0b4)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is an isolated cloud network and it is useful because it helps isolate resources and restrict the access

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create security groups and network Access Control Lists to control inbound and outbound traffic. 

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was how using the EC2 global View simplifies the monitoring of resources that have been deployed in multiple regions

### This project took me...

This project took me about an hour to complete

---

## Route tables

Route tables acts  as a GPS for the resources in your subnet. They determine where data packets should go based on their destination IP address

Routes tables are needed to make a subnet public because they direct the internet-bound traffic to the internet gateway

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-security_0a07b191)

---

## Route destination and target

Routes are defined by their destination and target, which means the destination is the IP address the data is to reach and the target is the path that the traffic will have to take to get to its destination.

The route in my route table that directed internet-bound traffic to my internet gateway had a destination of 0.0.0.0/0 and a target of the internet gateway

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-security_0a07b191)

---

## Security groups

Security groups are responsible for checking who comes in and out. They have strict rules about what kind of traffic can enter or leave the resource based on its IP address, protocols and port numbers. Every resource must be associated with a security group. This means security groups don't attach to a VPC or a subnet, they attach to a specific resource within that VPC/subnet. If you don't specify a security group when you launch a resource, it will use the default security group that AWS creates whenever you set up a VPC.



### Inbound vs Outbound rules

Inbound rules control the data that can enter the resources in your security group,  I  configured an inbound rule that allows any IP address to access the public resources

Outbound rules are control that data that your resources can send out. By default, my security group's outbound rule allows all trafic to any destination

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-security_92b0b0b4)

---

## Network ACLs

Network ACLs are the entry point of the subnet, checking each data packet against a table of ACL rules before allowing them through.

### Security groups vs. network ACLs

The difference between a security group and a network ACL is that network ACL's are used to set broad traffic rules that apply to an entire subnet while Security groups allow for more granular control, managing access to individual resource.

---

## Default vs Custom Network ACLs

### Similar to security groups, network ACLs use inbound and outbound rules

By default, a network ACL's inbound and outbound rules will allow all inbound and outbound traffic

In contrast, a custom ACL’s inbound and outbound rules are automatically set to "Deny" - all inbound and outbound traffic are denied until you add rules about the kind of traffic you'll allow.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-security_4faeb056)

---

## Tracking VPC Resources

I created additional VPC resources : VPC, Internet Gateway and security group. Instead of my usual region, I used a different region. Teams would use multiple regions to deloy resources to ensure high availability.

The EC2 Global View is a feature that lets you see and manage your EC2 and VPC resources across all AWS Regions from a single dashboard. Instead of switching between Regions to track your resources, this view gives you a single view at everything you have running, which is super useful for multi-region deployments. I could even narrow down my search by. filtering using the region option. Without EC2 Global View, you'd have to manually switch and search in different regions.

Now that I've learnt about EC2 Global View, I'd use it again to view resources that I have created over multiple regions

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-security_b03ea6162)

---

---