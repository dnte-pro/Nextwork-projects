<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Encrypt Data with AWS KMS

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-kms)

**Author:** Kiprono Yegon  
**Email:** kipronoyegon50@gmail.com

---

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-security-kms_w0x1y2z3)

---

## Introducing Today's Project!

In this project, I will demonstrate how to create encryption keys with AWS KMS (Key Management Service), encrypt a DynamoDB database with a KMS key, add and retrieve data from the database to test encryption, observe how AWS stops unauthorized access to the data, give a user encryption access. The goal is to  safeguard cloud environments and set up secure access to resources.

### Tools and concepts

Services I used include AWS Key Management Services, DynamoDB and IAM. Key concepts I learnt include encryption, decryption and user addition

### Project reflection

This project took me approximately forty five minutes.

I chose to do this project today because I want to venture into DevOps. Something that would make learning with NextWork even better is addition of real scenario-based projects

---

## Encryption and KMS

Encryption is the process of using algorithms to convert data to secure format(ciphertext). Companies and developers do this to  secure user data, transactions, files and more. Encryption keys tells the algorithm exactly how it would transform plain text into the jumbled up format called cipher text

AWS KMS is a secure vault for your encryption keys. You use KMS to create, manage, and use encryption keys that protect the data in your AWS resources. 
Key management systems are important because they are used to create, manage and use encryption keys.

Encryption keys are broadly categorized as a single encryption key. I set up a symmetric key because they are generally faster and more efficient for encrypting large amounts of data.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-security-kms_a2b3c4d5)

---

## Encrypting Data

My encryption key will safeguard data in DynamoDB, which makes sure that all data stored in the table is encrypted at rest, adding an extra layer of security

The different encryption options in DynamoDB include: owned by Amazin DynamoDB, AWS key managed and customer managed key. Their differences are based on who manages the encryption key. I selected customer managed key

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-security-kms_q8r9s0t1)

---

## Data Visibility

Rather than controlling who has access to the key, KMS manages user permissions by giving permissions to the user to see that a KMS key is available in the AWS environment, but wouldn't have the permissions to decrypt the data it protects.

Despite encrypting my DynamoDB table, I could still see the table's items because I as a user have permissions to use the encryption key in the KMS. DynamoDB uses transparent data encryption, which means when data is requested by an authorized user or an authorized application, DynamoDB retrieves the encrypted data, decrypts it with the key, then shows you the decrypted format so you can use it instantly

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-security-kms_c0d1e2f3)

---

## Denying Access

I configured a new IAM user to test  the KMS validation. The permission policies I granted this user are the full DynamoDB but not the KMS 

After accessing the DynamoDB table as the test user, I encountered an error stating that the user did not have permissions to decrypt. This confirmed  that a KMS key can be accessible to many users, but only those with the right permissions can use it to do specific actions like encryption or decryption.

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-security-kms_w0x1y2z3)

---

## EXTRA: Granting Access

To let my test user use the encryption key, I added the new user to the key policy at the KMS. My key's policy was updated to allow the new user to encrypt and decrypt the kms

Using the test user, I retried trying to acess the tables, I observed that I could view the tables,which confirmed that I gave access to the nextwork-kms-user and could encrypt and decrypt data in the table

Encryption secures data instead of controlling access to the data. I could combine encryption with access control to ensure that data is safe and encrypted

![Image](http://learn.nextwork.org/inspired_gray_mysterious_dragon/uploads/aws-security-kms_feffb2fb8)

---

---
