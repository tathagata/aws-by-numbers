# AWS by numbers

AWS is an ever growing ecosystem of services which abstract away the underlying building blocks of applications. The official well architected guide provides a deeper understanding of how to design fault-tolerant applications. However in early stages of application design one needs to do quick **back of the envelope**, or [BOTE calculation](http://highscalability.com/blog/2011/1/26/google-pro-tip-use-back-of-the-envelope-calculations-to-choo.html), to understand the trade offs while designing an application.

This repository intends to be an aggregation of numbers that are fundamental characteristics of each serivce that can help shorten the time for design deicisions, or get a cost estimate, or prevent failures due to default account limits.

## AWS By Numbers

| Specific AWS Services                 | Default Limits                     | Benchmarks                        |
|---------------------------------------|--------------------------------|--------------------------------|
| [ALB](#alb)  | [📉](#alb-default-limits) | [📊](#alb-benchmarks) |
| [AMIs](#amis)  | [📉](#amis-default-limits) | [📊](#amis-benchmarks) |
| [API Gateway](#api-gateway)  | [📉](#api-gateway-default-limits) | [📊](#api-gateway-benchmarks) |
| [Auto Scaling](#auto-scaling)  | [📉](#auto-scaling-default-limits) | [📊](#auto-scaling-benchmarks) |
| [Batch](#batch)  | [📉](#batch-default-limits) | [📊](#batch-benchmarks) |
| [Certificate Manager](#certificate-manager)  | [📉](#certificate-manager-default-limits) | [📊](#certificate-manager-benchmarks) |
| [CLB (ELB)](#clb)  | [📉](#clb-default-limits) | [📊](#clb-benchmarks) |
| [CloudFront](#cloudfront)  | [📉](#cloudfront-default-limits) | [📊](#cloudfront-benchmarks) |
| [CloudFormation](#cloudformation)  | [📉](#cloudformation-default-limits) | [📊](#cloudformation-benchmarks) |
| [CloudWatch](#cloudwatch)  | [📉](#cloudwatch-default-limits) | [📊](#cloudwatch-benchmarks) |
| [Device Farm](#device-farm)  | [📉](#device-farm-default-limits) | [📊](#device-farm-benchmarks) |
| [DirectConnect](#directconnect)  | [📉](#directconnect-default-limits) | [📊](#directconnect-benchmarks) |
| [DynamoDB](#dynamodb)  | [📉](#dynamodb-default-limits) | [📊](#dynamodb-benchmarks) |
| [EBS](#ebs)  | [📉](#ebs-default-limits) | [📊](#ebs-benchmarks) |
| [EC2](#ec2)  | [📉](#ec2-default-limits) | [📊](#ec2-benchmarks) |
| [ECS](#ecs)  | [📉](#ecs-default-limits) | [📊](#ecs-benchmarks) |
| [EKS](#eks)  | [📉](#eks-default-limits) | [📊](#eks-benchmarks) |
| [EFS](#efs)  | [📉](#efs-default-limits) | [📊](#efs-benchmarks) |
| [Elastic Beanstalk](#elastic-beanstalk)  | [📉](#elastic-beanstalk-default-limits) | [📊](#elastic-beanstalk-benchmarks) |
| [Elastic IPs](#elastic-ips)  | [📉](#elastic-ips-default-limits) | [📊](#elastic-ips-benchmarks) |
| [ElastiCache](#elasticache)  | [📉](#elasticache-default-limits) | [📊](#elasticache-benchmarks) |
| [EMR](#emr)  | [📉](#emr-default-limits) | [📊](#emr-benchmarks) |
| [Fargate](#fargate)  | [📉](#fargate-default-limits) | [📊](#fargate-benchmarks) |
| [Glacier](#glacier)  | [📉](#glacier-default-limits) | [📊](#glacier-benchmarks) |
| [IoT](#iot)  | [📉](#iot-default-limits) | [📊](#iot-benchmarks) |
| [Kinesis Firehose](#kinesis-firehose)  | [📉](#kinesis-firehose-default-limits) | [📊](#kinesis-firehose-benchmarks) |
| [Kinesis Streams](#kinesis-streams)  | [📉](#kinesis-streams-default-limits) | [📊](#kinesis-streams-benchmarks) |
| [KMS](#kms)  | [📉](#kms-default-limits) | [📊](#kms-benchmarks) |
| [Lambda](#lambda)  | [📉](#lambda-default-limits) | [📊](#lambda-benchmarks) |
| [Load Balancers](#load-balancers)  | [📉](#load-balancers-default-limits) | [📊](#load-balancers-benchmarks) |
| [Mobile Hub](#mobile-hub)  | [📉](#mobile-hub-default-limits) | [📊](#mobile-hub-benchmarks) |
| [OpsWorks](#opsworks)  | [📉](#opsworks-default-limits) | [📊](#opsworks-benchmarks) |
| [RDS](#rds)  | [📉](#rds-default-limits) | [📊](#rds-benchmarks) |
| [RDS Aurora](#rds-aurora)  | [📉](#rds-aurora-default-limits) | [📊](#rds-aurora-benchmarks) |
| [RDS Aurora MySQL](#rds-aurora-mysql)  | [📉](#rds-aurora-mysql-default-limits) | [📊](#rds-aurora-mysql-benchmarks) |
| [RDS Aurora PostgreSQL](#rds-aurora-postgresql)  | [📉](#rds-aurora-postgresql-default-limits) | [📊](#rds-aurora-postgresql-benchmarks) |
| [RDS MySQL and MariaDB](#rds-mysql-and-mariadb)  | [📉](#rds-mysql-and-mariadb-default-limits) | [📊](#rds-mysql-and-mariadb-benchmarks) |
| [RDS PostgreSQL](#rds-postgresql)  | [📉](#rds-postgresql-default-limits) | [📊](#rds-postgresql-benchmarks) |
| [RDS SQL Server](#rds-sql-server)  | [📉](#rds-sql-server-default-limits) | [📊](#rds-sql-server-benchmarks) |
| [Redshift](#redshift)  | [📉](#redshift-default-limits) | [📊](#redshift-benchmarks) |
| [Route 53](#route-53)  | [📉](#route-53-default-limits) | [📊](#route-53-benchmarks) |
| [S3](#s3)  | [📉](#s3-default-limits) | [📊](#s3-benchmarks) |
| [Security and IAM](#security-and-iam)  | [📉](#security-and-iam-default-limits) | [📊](#security-and-iam-benchmarks) |
| [SES](#ses)  | [📉](#ses-default-limits) | [📊](#ses-benchmarks) |
| [SNS](#sns)  | [📉](#sns-default-limits) | [📊](#sns-benchmarks) |
| [SQS](#sqs)  | [📉](#sqs-default-limits) | [📊](#sqs-benchmarks) |
| [Step Functions](#step-functions)  | [📉](#step-functions-default-limits) | [📊](#step-functions-benchmarks) |
| [WAF](#waf)  | [📉](#waf-default-limits) | [📊](#waf-benchmarks) |
| [VPCs, Network Security, and Security Groups](#vpcs-network-security-and-security-groups)  | [📉](#vpcs-network-security-and-security-groups-default-limits) | [📊](#vpcs-network-security-and-security-groups-benchmarks) |

## ALB Default Limits

## ALB Benchmarks


## AMIs Default Limits

## AMIs Benchmarks


## API Gateway Default Limits

## API Gateway Benchmarks


## Auto Scaling Default Limits

## Auto Scaling Benchmarks


## Batch Default Limits

## Batch Benchmarks


## Certificate Manager Default Limits

## Certificate Manager Benchmarks


## CLB (ELB) Default Limits

## CLB (ELB) Benchmarks


## CloudFront Default Limits

## CloudFront Benchmarks


## CloudFormation Default Limits

## CloudFormation Benchmarks


## CloudWatch Default Limits

## CloudWatch Benchmarks


## Device Farm Default Limits

## Device Farm Benchmarks


## DirectConnect Default Limits

## DirectConnect Benchmarks


## DynamoDB Default Limits

## DynamoDB Benchmarks


## EBS Default Limits

## EBS Benchmarks


## EC2 Default Limits

## EC2 Benchmarks


## ECS Default Limits

## ECS Benchmarks


## EKS Default Limits

## EKS Benchmarks


## EFS Default Limits

## EFS Benchmarks


## Elastic Beanstalk Default Limits

## Elastic Beanstalk Benchmarks


## Elastic IPs Default Limits

## Elastic IPs Benchmarks


## ElastiCache Default Limits

## ElastiCache Benchmarks


## EMR Default Limits

## EMR Benchmarks


## Fargate Default Limits

## Fargate Benchmarks


## Glacier Default Limits

## Glacier Benchmarks


## IoT Default Limits

## IoT Benchmarks


## Kinesis Firehose Default Limits

## Kinesis Firehose Benchmarks


## Kinesis Streams Default Limits

## Kinesis Streams Benchmarks


## KMS Default Limits

## KMS Benchmarks


## Lambda Default Limits

## Lambda Benchmarks


## Load Balancers Default Limits

## Load Balancers Benchmarks


## Mobile Hub Default Limits

## Mobile Hub Benchmarks


## OpsWorks Default Limits

## OpsWorks Benchmarks


## RDS Default Limits

## RDS Benchmarks


## RDS Aurora Default Limits

## RDS Aurora Benchmarks


## RDS Aurora MySQL Default Limits

## RDS Aurora MySQL Benchmarks


## RDS Aurora PostgreSQL Default Limits

## RDS Aurora PostgreSQL Benchmarks


## RDS MySQL and MariaDB Default Limits

## RDS MySQL and MariaDB Benchmarks


## RDS PostgreSQL Default Limits

## RDS PostgreSQL Benchmarks


## RDS SQL Server Default Limits

## RDS SQL Server Benchmarks


## Redshift Default Limits

## Redshift Benchmarks


## Route 53 Default Limits

## Route 53 Benchmarks


## S3 Default Limits

## S3 Benchmarks


## Security and IAM Default Limits

## Security and IAM Benchmarks


## SES Default Limits

## SES Benchmarks


## SNS Default Limits

## SNS Benchmarks


## SQS Default Limits

## SQS Benchmarks


## Step Functions Default Limits

## Step Functions Benchmarks


## WAF Default Limits

## WAF Benchmarks


## VPCs, Network Security, and Security Groups Default Limits

## VPCs, Network Security, and Security Groups Benchmarks


