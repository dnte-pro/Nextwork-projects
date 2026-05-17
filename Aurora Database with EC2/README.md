<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Aurora Database with EC2

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-aurora)

---

## Connect a Web App to Amazon Aurora

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-aurora_44443546)

---

## Introducing Today's Project!

### What is Amazon Aurora?

Amazon Aurora is a fully managed relational database service compatible with MySQL and PostgreSQL that combines the performance and availability of high-end commercial databases with the simplicity and cost efficiency of open-source databases. It is useful because it provides automatic backups, high availability, fault tolerance, fast failover, scalable storage, and read replicas for handling large workloads, while reducing the operational overhead of managing database infrastructure manually.

### How I used Amazon Aurora in this project

In today's project, I used Amazon Aurora to create a database that will be used in the oncoming projects and also connected it to an EC2 instance

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the ease of connecting the Amazon Aurora to the EC2 instance

### This project took me...

The project took me about 45 minutes

---

## In the first part of my project...

### Creating an Aurora Cluster

A relational database is a type of database that organizes data into tables, which are collections of rows and columns., the rows relate to the columns and vice-versa

Aurora is a good choice when in need for something large-scale, with peak performance and uptime. This is because Aurora databases use clusters. Ordinary relational databases, like MySQL and Oracle are more generic and cost-effective. They suit smaller databases and less demanding workloads.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-aurora_44443546)

---

## Halfway through I stopped!

I stopped creating my Aurora database because there was no existing running instance. Create the instance so that it connect to the aurora database. 

### Features of my EC2 instance

I created a new key pair for my EC2 instance because the key pair in EC2 is quite literally the keys to access our EC2 instance.
We need keys to our EC2 instance if we want to add, change, or update how our EC2 instance is running.

When I created my EC2 instance, I took particular note of the  Public IPv4 DNS and the Key paiar name

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-aurora_91b9fd1g)

---

## Then I could finish setting up my database

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-aurora_1fddb0b5)

Aurora Database uses clusters because each cluster consists of a primary instance (where all write operations occur) and multiple read replicas as back-ups. If your database's primary instance fails, one of the replicas can be promoted to primary automatically.

---

---