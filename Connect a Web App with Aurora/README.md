<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Connect a Web App with Aurora

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-webapp)

---

## Connect a Web App to Amazon Aurora

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-webapp_1709b26b)

---

## Introducing Today's Project!

### What is Amazon Aurora?

Amazon Aurora is a fully managed relational database service compatible with MySQL and PostgreSQL that combines the performance and availability of high-end commercial databases with the simplicity and cost efficiency of open-source databases. It is useful because it provides automatic backups, high availability, fault tolerance, fast failover, scalable storage, and read replicas for handling large workloads, while reducing the operational overhead of managing database infrastructure manually.

### How I used Amazon Aurora in this project

In today's project, I used Amazon Aurora to store data that we served from the web page we had created

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was the keeness needed when creating folders and the time it takes to debug a single error

### This project took me...

It took me 45 minutes to complete the task

---

## Creating a Web App

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-webapp_b7999168)

To connect to my EC2 instance, I ran the command ssh -i NextWorkAuroraApp.pem ec2-user@35.90.177.150

To help me create my web app, I first updated the instance and then installed the prerequisites to serve the web server: Apache web server(httpd), php, php-mysqli and mariadb105

---

## Connecting my Web App to Aurora

I set up my EC2 instance's connection details to my database by creating a file "dbinfo.inc" which contains the setings for the connection

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-webapp_1709b25b)

---

## My Web App Upgrade

Next, I upgraded my web app by creating a new file "SamplePage.php" and a ddinfo.inc toconnect the database information to the web page

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-webapp_2709b25b)

---

## Testing my Web App

To make sure my web app was working correctly, I installed mySQL CLI and then checked the database if it contained the contents I had earlier added via the web page

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-webapp_1409z22b)

---

--- 