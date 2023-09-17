# AWS-ETL-Process-v1
![image](https://github.com/prasadanilmore/AWS-ETL-Process-v1/assets/85488185/40c234ea-3d2b-45fd-aeec-de1793e754d3)


This repository contains the code and configuration files for an AWS ETL (Extract, Transform, Load) process. The ETL process involves extracting data from various sources, transforming it, and loading it into an Amazon Redshift data warehouse.

Project Steps
Step 1: Setting up the Environment
Create a Virtual Private Cloud (VPC) endpoint for Amazon S3 to establish a smooth connection.
Create an IAM (Identity and Access Management) role that grants necessary permissions for Redshift, Lambda, S3, CloudWatch, and Glue.
Step 2: Configuring Security
Set up a security group with inbound rules allowing "All TCP" traffic.
Step 3: Data Preparation
Create an S3 bucket and upload the source data, such as the "TestReport.csv" file.
Step 4: Setting up Redshift
Create an Amazon Redshift cluster, applying the security rules defined earlier and ensuring connectivity between AWS Glue and Redshift.
Step 5: Data Cataloging with AWS Glue
Create two AWS Glue Crawlers:
a. One crawler for extracting data from S3 and cataloging it into the Glue Data Catalog.
b. Another crawler for connecting to Redshift via JDBC and cataloging the schema into the Glue Data Catalog, using the same connection name.
Step 6: Data Transformation and Loading
Develop an AWS Glue Job that orchestrates the ETL process by integrating the two previously created crawlers and loading the transformed data into Amazon Redshift.
Step 7: Event-Driven Automation
Create an Amazon CloudWatch Event to define event patterns that monitor changes in the "S3 Crawler State." This event triggers an AWS Lambda function.
Step 8: Lambda Function for Automation
Develop an AWS Lambda function that monitors the CloudWatch Event and, upon detection, initiates the AWS Glue Job for automated ETL processing.
Project Overview
This project establishes an end-to-end ETL pipeline, automating data extraction, transformation, and loading processes, thus enhancing data accessibility and analysis within the Amazon Redshift data warehouse.
