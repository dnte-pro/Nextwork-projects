<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Testing VPC Connectivity

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-connectivity)

---

## Testing VPC Connectivity

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-connectivity_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service from Amazon Web Services that allows you to create a private, isolated network within the cloud where you can securely run your applications and resources. It is useful because it gives you full control over your networking environment, including IP address ranges, subnets, routing, and
security settings, enabling you to protect your systems, manage traffic flow, and design scalable architectures.

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to test connectivity  of a private and a public server and troubleshooting errors that arise

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the in-depth learning of Network ACLs and security groups and the setup for private and public servers to communicate in a VPC

### This project took me...

This project took me about 3 hours since I had previosly deleted all the resources

---

## Connecting to an EC2 Instance

Connectivity is all about how well different parts of your network talk to each other and with external networks. It's essential because connectivity is how data flows smoothly across your network, powering everything from simple web hosting on the Internet to complex operations. Solid connectivity is the backbone of any system that relies on network interactions, making every communication and operation reliable and efficient.

My first connectivity test was whether I could connect to the Public Server by using the EC2 Instance Connect

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-connectivity_88727bef)

---

## EC2 Instance Connect

I connected to my EC2 instance using EC2 Instance Connect, Instance Connect lets you securely connect to your EC2 instances directly using the AWS Management Console. You're still using SSH, but with all the key management handling it for you. This takes away a lot of the complexity of setting up SSH.

My first attempt at getting direct access to my public server resulted in an error, because the security group associated with NextWork Public Server lets in all inbound HTTP traffic, but this is not how we're trying to access our Public Server!
We're trying to access NextWork Public Server using SSH through EC2 Instance Connect, which is a different traffic type and not the HTTP traffic we had added.

I fixed this error by adding a new rule in the inbound traffic. I added a nw rule that uses SSH traffic and chose "Anywhere IPv4 " as the source

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-connectivity_1cbb1b88)

---

## Connectivity Between Servers

Ping is a common computer network tool used to check whether your computer can communicate with another computer or device on a network. I used ping to test the connectivity between the Public server and the Private server

The ping command I ran was "ping 10.0.1.78"

The first ping returned nothing, the screen was frozen. This meant there was no connectivity between the Public server and the Private server

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-connectivity_defghijk)

---

## Troubleshooting Connectivity

I troubleshooted this by editing the network ACL to allow ICMP inbound from the Public server. Also updated the Private security group inbound rules to allow connection from the Public server

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-connectivity_4a9e8014)

---

## Connectivity to the Internet

Curl is a tool to test connectivity in a network, curl is used to transfer data to or from a server. That means on top of checking connectivity, you can use curl to grab data from, or upload data into other servers on the internet

I used curl to test the connectivity between the Public server and example.com, curl has fetched the complete HTML content of  web app, which is why you now see a large amount of HTML data.

### Ping vs Curl

Ping and curl are different because curl tests connectivity in a network whereas ping checks if one computer can contact another and how long messages take to travel back and forth

---

## Connectivity to the Internet

I ran the curl command curl learn.nextwork.org the command sends an HTTP request to the server that hosts the website. This request tells the server that you want to retrieve the HTML content of the website. The website's server then processes this request and sends back the data as a response.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-networks-connectivity_8ee57662)

---

---