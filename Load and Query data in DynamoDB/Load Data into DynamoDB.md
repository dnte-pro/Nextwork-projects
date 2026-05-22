<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Load Data into DynamoDB

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-dynamodb)

**Author:** Kiprono Yegon  
**Email:** kipronoyegon50@gmail.com

---

## Load Data into a DynamoDB Table

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-dynamodb_b481c730)

---

## Introducing Today's Project!

### What is Amazon DynamoDB?

Amazon DynamoDB is a fully managed NoSQL database service that stores and retrieves large amounts of data quickly and efficiently it is important because of its speed and flexibility

### How I used Amazon DynamoDB in this project

In today's project, I used Amazon DynamoDB to create tables and load data into the attributes in the tables

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is the Ease of loading data to the tables

### This project took me...

This project took me about thiry minues

---

## Create a DynamoDB table

DynamoDB tables organises data using a list, each item with their own list of attributes

An attribute is a piece of data about an item and can have multiple attributes.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-dynamodb_a3cefee0)

---

## Read and Write Capacity

Read capacity units (RCUs)  gives a way to measure how many engines DynamoDB is using to operate.
and write capacity units (WCUs) give the DynamoDB tables the engines to edit/update/delete data!

Amazon DynamoDB's Free Tier gives you 25GB of data storage, plus 25 Write and 25 Read Capacity Units (WCU, RCU). This is enough to handle 200M requests per month I turned off auto scaling because it has the power to boost your table's processing power increasing the costs

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-dynamodb_ef47dd8f)

---

## Using CLI and CloudShell

AWS CloudShell is shell in your AWS Management Console,  which comes with pre-installed AWS CLI

AWS CLI  is a software that lets you create, delete and update AWS resources with commands instead of clicking through your console.

I ran a CLI command in AWS CloudShell that created four tables, each with specific attributes and settings.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-dynamodb_81e0258b)

---

## Loading Data with CLI

I ran a CLI command in AWS CloudShell that loads multiple items into DynamoDB tables 

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-dynamodb_791c600b)

---

## Observing Item Attributes

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-dynamodb_b481c731)

I checked a ContentCatalog item, which had the following attributes:Authors, ContentType, Difficulty, Price, ProjectCategory, Published, Title and URL

I checked another ContentCatalog item, which had a different set of attributes from the first table, it has no StudentsComplete

---

## Benefits of DynamoDB

A benefit of DynamoDB over relational databases is flexibility, because every item having their own unique set of attributes is a huge advantage when items in a table could look different from each other.

Another benefit over relational databases is speed, because they use partition keys to split up a table and quickly find the items they're looking for.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-databases-dynamodb_b481c730)

---

---
