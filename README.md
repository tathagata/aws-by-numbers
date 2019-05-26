# AWS by numbers

AWS is an ever growing ecosystem of services which abstract away the underlying building blocks of applications. The [official well architected guide](https://d1.awsstatic.com/whitepapers/architecture/AWS_Well-Architected_Framework.pdf) provides a deeper understanding of how to design fault-tolerant applications. However in the early stages of application design one needs to do quick [back of the envelope](http://highscalability.com/blog/2011/1/26/google-pro-tip-use-back-of-the-envelope-calculations-to-choo.html), shortened as *bote*, to understand the trade offs while designing an application.

This repository intends to be an aggregation of numbers that are fundamental characteristics of each serivce that can help shorten the time for design deicisions, cost estimation, or prevent failures due to default account limits.

## AWS By Numbers

| Specific AWS Services                 | Default Limits                     | Bote                        |
|---------------------------------------|--------------------------------|--------------------------------|
| [ALB](#alb)  | [📉](#alb-default-limits) | [📊](#alb-bote) |
| [AMIs](#amis)  | [📉](#amis-default-limits) | [📊](#amis-bote) |
| [API Gateway](#api-gateway)  | [📉](#api-gateway-default-limits) | [📊](#api-gateway-bote) |
| [Auto Scaling](#auto-scaling)  | [📉](#auto-scaling-default-limits) | [📊](#auto-scaling-bote) |
| [Batch](#batch)  | [📉](#batch-default-limits) | [📊](#batch-bote) |
| [Certificate Manager](#certificate-manager)  | [📉](#certificate-manager-default-limits) | [📊](#certificate-manager-bote) |
| [CLB (ELB)](#clb)  | [📉](#clb-default-limits) | [📊](#clb-bote) |
| [CloudFront](#cloudfront)  | [📉](#cloudfront-default-limits) | [📊](#cloudfront-bote) |
| [CloudFormation](#cloudformation)  | [📉](#cloudformation-default-limits) | [📊](#cloudformation-bote) |
| [CloudWatch](#cloudwatch)  | [📉](#cloudwatch-default-limits) | [📊](#cloudwatch-bote) |
| [Device Farm](#device-farm)  | [📉](#device-farm-default-limits) | [📊](#device-farm-bote) |
| [DirectConnect](#directconnect)  | [📉](#directconnect-default-limits) | [📊](#directconnect-bote) |
| [DynamoDB](#dynamodb)  | [📉](#dynamodb-default-limits) | [📊](#dynamodb-bote) |
| [EBS](#ebs)  | [📉](#ebs-default-limits) | [📊](#ebs-bote) |
| [EC2](#ec2)  | [📉](#ec2-default-limits) | [📊](#ec2-bote) |
| [ECS](#ecs)  | [📉](#ecs-default-limits) | [📊](#ecs-bote) |
| [EKS](#eks)  | [📉](#eks-default-limits) | [📊](#eks-bote) |
| [EFS](#efs)  | [📉](#efs-default-limits) | [📊](#efs-bote) |
| [Elastic Beanstalk](#elastic-beanstalk)  | [📉](#elastic-beanstalk-default-limits) | [📊](#elastic-beanstalk-bote) |
| [Elastic IPs](#elastic-ips)  | [📉](#elastic-ips-default-limits) | [📊](#elastic-ips-bote) |
| [ElastiCache](#elasticache)  | [📉](#elasticache-default-limits) | [📊](#elasticache-bote) |
| [EMR](#emr)  | [📉](#emr-default-limits) | [📊](#emr-bote) |
| [Fargate](#fargate)  | [📉](#fargate-default-limits) | [📊](#fargate-bote) |
| [Glacier](#glacier)  | [📉](#glacier-default-limits) | [📊](#glacier-bote) |
| [IoT](#iot)  | [📉](#iot-default-limits) | [📊](#iot-bote) |
| [Kinesis Firehose](#kinesis-firehose)  | [📉](#kinesis-firehose-default-limits) | [📊](#kinesis-firehose-bote) |
| [Kinesis Streams](#kinesis-streams)  | [📉](#kinesis-streams-default-limits) | [📊](#kinesis-streams-bote) |
| [KMS](#kms)  | [📉](#kms-default-limits) | [📊](#kms-bote) |
| [Lambda](#lambda)  | [📉](#lambda-default-limits) | [📊](#lambda-bote) |
| [Load Balancers](#load-balancers)  | [📉](#load-balancers-default-limits) | [📊](#load-balancers-bote) |
| [Mobile Hub](#mobile-hub)  | [📉](#mobile-hub-default-limits) | [📊](#mobile-hub-bote) |
| [OpsWorks](#opsworks)  | [📉](#opsworks-default-limits) | [📊](#opsworks-bote) |
| [RDS](#rds)  | [📉](#rds-default-limits) | [📊](#rds-bote) |
| [RDS Aurora](#rds-aurora)  | [📉](#rds-aurora-default-limits) | [📊](#rds-aurora-bote) |
| [RDS Aurora MySQL](#rds-aurora-mysql)  | [📉](#rds-aurora-mysql-default-limits) | [📊](#rds-aurora-mysql-bote) |
| [RDS Aurora PostgreSQL](#rds-aurora-postgresql)  | [📉](#rds-aurora-postgresql-default-limits) | [📊](#rds-aurora-postgresql-bote) |
| [RDS MySQL and MariaDB](#rds-mysql-and-mariadb)  | [📉](#rds-mysql-and-mariadb-default-limits) | [📊](#rds-mysql-and-mariadb-bote) |
| [RDS PostgreSQL](#rds-postgresql)  | [📉](#rds-postgresql-default-limits) | [📊](#rds-postgresql-bote) |
| [RDS SQL Server](#rds-sql-server)  | [📉](#rds-sql-server-default-limits) | [📊](#rds-sql-server-bote) |
| [Redshift](#redshift)  | [📉](#redshift-default-limits) | [📊](#redshift-bote) |
| [Route 53](#route-53)  | [📉](#route-53-default-limits) | [📊](#route-53-bote) |
| [S3](#s3)  | [📉](#s3-default-limits) | [📊](#s3-bote) |
| [Security and IAM](#security-and-iam)  | [📉](#security-and-iam-default-limits) | [📊](#security-and-iam-bote) |
| [SES](#ses)  | [📉](#ses-default-limits) | [📊](#ses-bote) |
| [SNS](#sns)  | [📉](#sns-default-limits) | [📊](#sns-bote) |
| [SQS](#sqs)  | [📉](#sqs-default-limits) | [📊](#sqs-bote) |
| [Step Functions](#step-functions)  | [📉](#step-functions-default-limits) | [📊](#step-functions-bote) |
| [WAF](#waf)  | [📉](#waf-default-limits) | [📊](#waf-bote) |
| [VPCs, Network Security, and Security Groups](#vpcs-network-security-and-security-groups)  | [📉](#vpcs-network-security-and-security-groups-default-limits) | [📊](#vpcs-network-security-and-security-groups-bote) |

## ALB Default Limits

## ALB Bote


## AMIs Default Limits

## AMIs Bote


## API Gateway Default Limits

- 30 seconds is the hard limit for API Gateway timeouts.

## API Gateway Bote


## Auto Scaling Default Limits

## Auto Scaling Bote


## Batch Default Limits

## Batch Bote


## Certificate Manager Default Limits

## Certificate Manager Bote


## CLB (ELB) Default Limits

## CLB (ELB) Bote


## CloudFront Default Limits

## CloudFront Bote


## CloudFormation Default Limits

- max resources in a cloudformation template is *200* 

## CloudFormation Bote


## CloudWatch Default Limits

## CloudWatch Bote


## Device Farm Default Limits

## Device Farm Bote


## DirectConnect Default Limits

## DirectConnect Bote


## DynamoDB Default Limits

## DynamoDB Bote


## EBS Default Limits

## EBS Bote


## EC2 Default Limits

- [EC2 instances information](https://www.ec2instances.info)

## EC2 Bote

- [jamsan920](https://www.reddit.com/user/jamsan920/) on [reddit](https://www.reddit.com/r/aws/comments/bt30f7/numbers_every_aws_programmer_should_know/eoufl1y/)  
For Windows instances, general rule of thumb is ~8 months of 24x7 on-demand instance pricing is the equivalent of a full year of no up-front reserved pricing (e.g. if you run 24x7 for more than 8 months, you'll be better off with an RI).   For Linux, that is roughly at the 6 month mark.

- 

## ECS Default Limits

## ECS Bote


## ECR Default Limits

* One registry per account per supported region
* One ECR repository can have *1000* (one thousand) images

## ECR Bote


## EKS Default Limits

## EKS Bote


## EFS Default Limits

## EFS Bote


## Elastic Beanstalk Default Limits

## Elastic Beanstalk Bote


## Elastic IPs Default Limits

## Elastic IPs Bote


## ElastiCache Default Limits

## ElastiCache Bote


## EMR Default Limits

## EMR Bote


## Fargate Default Limits

## Fargate Bote


## Glacier Default Limits

## Glacier Bote


## IoT Default Limits

## IoT Bote


## Kinesis Firehose Default Limits

## Kinesis Firehose Bote


## Kinesis Streams Default Limits

## Kinesis Streams Bote


## KMS Default Limits

## KMS Bote


## Lambda Default Limits

- 1000 concurrent executions

## Lambda Bote

- By [pint](https://www.reddit.com/user/pint/) on [reddit](https://www.reddit.com/r/aws/comments/bt30f7/numbers_every_aws_programmer_should_know/eou5yjj/)
60k calls per dollar assuming 1GB and 1s, and proportional to both. (if your calls are 500ms, you get 120k)

- 512MB maximum ephemeral storage for Lambda (/tmp)
- 1024MB Lambda function gets you a full CPU core
- [EC2 vs API Gateway + Lambda](https://servers.lol/)


## Load Balancers Default Limits

## Load Balancers Bote


## Mobile Hub Default Limits

## Mobile Hub Bote


## OpsWorks Default Limits

## OpsWorks Bote


## RDS Default Limits

- 5 Security groups max per RDS instance
- 60 Security group rules max per security group

## RDS Bote


## RDS Aurora Default Limits

## RDS Aurora Bote


## RDS Aurora MySQL Default Limits

## RDS Aurora MySQL Bote


## RDS Aurora PostgreSQL Default Limits

## RDS Aurora PostgreSQL Bote


## RDS MySQL and MariaDB Default Limits

## RDS MySQL and MariaDB Bote


## RDS PostgreSQL Default Limits

## RDS PostgreSQL Bote


## RDS SQL Server Default Limits

## RDS SQL Server Bote


## Redshift Default Limits

## Redshift Bote


## Route 53 Default Limits

## Route 53 Bote


## S3 Default Limits

## S3 Bote


## Security and IAM Default Limits

- Max number of managed policies attached to an iam user, group or role is *10*

## Security and IAM Bote


## SES Default Limits

## SES Bote


## SNS Default Limits

## SNS Bote


## SQS Default Limits

## SQS Bote


## Step Functions Default Limits

## Step Functions Bote


## WAF Default Limits

## WAF Bote


## VPCs, Network Security, and Security Groups Default Limits

## VPCs, Network Security, and Security Groups Bote


## Inspiration

* The template is taken from [AWS Open Guide](https://github.com/open-guides/og-aws/)