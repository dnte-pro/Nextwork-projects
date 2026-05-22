<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Query Data with DynamoDB

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-query)

**Author:** Kiprono Yegon  
**Email:** kipronoyegon50@gmail.com

---

## Query Data with DynamoDB

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-query_733d9399)

---

## Introducing Today's Project!

### What is Amazon DynamoDB?

Amazon DynamoDB is a fully managed NoSQL database service that stores and retrieves large amounts of data quickly and efficiently it is important because of its speed and flexibility


### How I used Amazon DynamoDB in this project

In today's project, I used Amazon DynamoDB to create tables and load data into the attributes in the tables. I also did a transaction.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is the ease of using the AWS CLI to carry out tasks in the DynamoDB

### This project took me...

This project took me about an hour

---

## Querying DynamoDB Tables

A partition key is the filter that DynamoDB will use to split up and find data. Partition key values don't have to be unique.

A sort key is a secondary key used to filter your query results again! Sort keys work after the partition key i.e. you still have to use the partition key to split up your data first, and then the sort key partitions your data again.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-query_d105b0b0)

---

## Limits of Using DynamoDB

I ran into an error when I queried for the data PostedBy user Abdulrahman. This was because it did not have a partition key.


Insights we could extract from our Comment table includes the comments posted by a user in a given range of time. Insights we can't easily extract from the Comment table includes the posts a user posted.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-query_cb3e260c)

---

## Running Queries with CLI

A query I ran in CloudShell was to find the consistent reads. This query will return consistent reads

Query options I could add to my query are the table name, key, project expression and the consumed capacity.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-query_733d9399)

---

## Transactions

A transaction is a group of operations that all have to succeed - if any of the operations in the group fails, none of the changes get applied. This makes sure that any change to your database is consistent across all your tables!

I ran a transaction using the AWS CLI. This transaction did two things, it updated the Forum and and comments section 

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-query_2f65f83e)

---

---
