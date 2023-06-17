# Kafka-Stream-Pipeline
This project involves an end to end pipeline which simulates a stock market dataset, consumes the data in real time in Kafka and enables real time analytics on AWS environment

The high level design looks like this :
CSV -> Kafka -> AWS S3 -> AWS GLUE Crawler -> AWS Athena

You need to perform the following steps -
i. Initiate Kafka Zookeeper, producer and consumer on your local machine or an EC2 server 
  i.i. For local dev environment setup, these steps should be followed : https://docs.google.com/document/d/e/2PACX-1vR_mva3l81HrvbGeJOimo0MtssVVSGi4at3WYeRCHBeBAm319t3XivQCV97dhkpK1a5cSCUN7cdO3Sd/pub?urp=gmail_link
  i.ii. For ec2 initialisation, Mac users would need to just download foreign key .pem file and ssh into AWS EC2 VM using that. Windows users should install Putty and PuttyGen to create .ppk from .pem file and ssh using that

ii. Access these services using a Python IDE or notebook for easier interaction
iii. Create an S3 bucket and write files from consumer onto the bucket
iv. Set up a GLUE crawler to crawl all the streaming files in json from S3 to create a structured table, you can also create Lakeformation resources to store the dump
v. Once done, consume the table in Athena, build queries and if required, create visualisations in AWS Quicksight on top of this

Pre-requisites -
Need all property files for Kafka on local dev. Use the frameworks directory objects mentioned here in root 
AWS Account

