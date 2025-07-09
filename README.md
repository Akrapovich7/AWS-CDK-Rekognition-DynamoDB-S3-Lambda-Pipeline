# AWS-CDK-Rekognition-DynamoDB-S3-Lambda-Pipeline
In this project I am using CDK to setup my cloud infrastructure for real time recognition project using various AWS services(more on that in README)
# 📸 Real-Time Recognition System using AWS CDK, Rekognition, S3, Lambda, and DynamoDB

This project uses **AWS CDK** to provision a real-time recognition pipeline powered by **Amazon Rekognition**, **S3**, **Lambda**, and **DynamoDB**. CDK synthesizes CloudFormation templates to define and deploy the infrastructure as code (IaC).

---

## 📦 Stack Overview

| Service         | Role                                                                 |
|----------------|----------------------------------------------------------------------|
| **AWS CDK**     | Used to define cloud resources using TypeScript/Python               |
| **CloudFormation** | CDK synthesizes resources to CloudFormation templates for deployment |
| **Amazon S3**    | Stores uploaded images that trigger recognition                     |
| **AWS Lambda**   | Invokes Rekognition and writes results to DynamoDB                  |
| **Amazon Rekognition** | Analyzes images for objects, faces, labels                      |
| **Amazon DynamoDB** | Stores recognition results with metadata                          |

---

## 🛠 Architecture Diagram

```text
           +-------------+     S3 Trigger     +------------+
           |             |  ----------------> |            |
           |  Amazon S3  |                   |   Lambda    |
           |             | <---------------- |   Function  |
           +-------------+  Recognition Data +------------+
                                       |
                                       v
                             +--------------------+
                             |  Amazon Rekognition |
                             +--------------------+
                                       |
                                       v
                             +--------------------+
                             |  DynamoDB (Results)|
                             +--------------------+

