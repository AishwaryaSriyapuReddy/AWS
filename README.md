<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Visualize a Relational Database

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-databases-rds)

**Author:** Aishwarya Sriyapu Reddy  
**Email:** aishwarya.sriyapureddy0@gmail.com

---

## Visualise a Relational Database

![Image](http://learn.nextwork.org/confident_teal_loyal_fennel/uploads/aws-databases-rds_1fddb0b5)

---

## Introducing Today's Project!

### What is Amazon RDS?

Amazon RDS is Relational database Services in AWS and it is useful because it allows users to set up, operate and scale relational databses on cloud easily

### How I used Amazon RDS in this project

In today's project, I used Amazon RDS to create a pipeline where data stored in an RDS database could be queried, analyzed, and visualized through Amazon QuickSight.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was clear step by step implementation of project

### This project took me...

How much time did this project take you? 3hrs

---

## In the first part of my project...

### Creating a Relational Database

I created my relational database by going to RDS and Aurora console and create a MYSQL instance databse in database section on left panel

![Image](http://learn.nextwork.org/confident_teal_loyal_fennel/uploads/aws-databases-rds_43343546)

---

## Understanding Relational Databases

A relational database is a database where data is stored in tables in rows and columns

### MySQL vs SQL

The difference between MySQL and SQL is MYSQL is relational database management system (RDBMS) which is used to to manage databses where SQL is a Structured Query Language used to manage and manipulate the databses and its data in the MYSQL system.

---

## Populating my RDS instance

The first thing I did was make my RDS instance public because to allow connections from outside AWS network to communicate with this RDS instance

I had to update the default security group for my RDS schema because we are allowing sqlworkbench to interact with rds instance in AWS. So we are adding inbound rule to all allow all traffic from local system where sql workbench is present.

![Image](http://learn.nextwork.org/confident_teal_loyal_fennel/uploads/aws-databases-rds_91b9fd1g)

---

## Using MySQL Workbench

![Image](http://learn.nextwork.org/confident_teal_loyal_fennel/uploads/aws-databases-rds_1fddb0b5)

To populate my database I used insert command.
syntax: 
insert into <tablename>(col1,col2)
values
(val1,val2),
(val3,val4);

---

## Connecting QuickSight and RDS

To connect my RDS instance to QuickSight I selected new datasets in Dataset section and set connection to RDS instance to source data from by providing instance details with database credentials

This solution is risky because anyone can access our RDS instance, so it is highly prone to hacking.

### A better strategy

First, I made a new security group so that we are only allowing quicksight access to RDS instance

Next, I connected my new security group to QuickSight by creating VPC connection for QuickSight and also entering security group details there itself

---

## Now to secure my RDS instance

To make my RDS instance secure I made RDS not publicaly available and provided inbound rules so it could communicate with QuickSight alone

I made sure that my RDS instance could be accessed from QuickSight by provinding inbound rules in RDS Security Group of type SQL/Aurora with Quicksight Security group and attached this security group to RDS instance

![Image](http://learn.nextwork.org/confident_teal_loyal_fennel/uploads/aws-databases-rds_1709b26b)

---

## Adding RDS as a data source for QuickSight

![Image](http://learn.nextwork.org/confident_teal_loyal_fennel/uploads/aws-databases-rds_1709b29b)

This data source is different from my initial data source because the data source have different security groups with inbound rules for communication between RDS and QuickSight

![Image](http://learn.nextwork.org/confident_teal_loyal_fennel/uploads/aws-databases-rds_1709b30b)

---

---
