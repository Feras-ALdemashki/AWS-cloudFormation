# AWS CloudFormation Infrastructure as Code Practice

This repository is a hands-on AWS CloudFormation learning project focused on building cloud infrastructure as code using YAML templates. It demonstrates the progression from simple AWS resource creation to a more complete web application infrastructure stack.

## Project Overview

The goal of this project is to practice defining, deploying, and managing AWS infrastructure through CloudFormation templates instead of creating resources manually in the AWS Management Console.

The templates in this repository cover foundational AWS infrastructure concepts, including:

- Amazon S3 bucket provisioning
- Amazon EC2 instance provisioning
- Parameterized CloudFormation templates
- CloudFormation metadata for better parameter organization
- Amazon VPC and subnet creation
- Application Load Balancer configuration
- Auto Scaling Group configuration
- Amazon Route 53 DNS configuration
- Amazon CloudWatch Logs and alarms
- Amazon SNS email notifications

## Repository Structure

```text
AWS-cloudFormation/
├── Resources/
│   ├── ResourcesS3.YAML
│   ├── ResourcesS3-and-EC2.YAML
│   ├── ResourcesS3-and-EC2-with-parameters.YAML
│   ├── Resources-with-metaData.YAML
│   ├── ResourcesVPC.YAML
│   └── full-template.YAML
├── web-Application/
│   └── webApplication.YAML
└── README.md
```

## Templates

### `Resources/ResourcesS3.YAML`

Creates a basic Amazon S3 bucket using CloudFormation.

### `Resources/ResourcesS3-and-EC2.YAML`

Creates an Amazon S3 bucket and an Amazon EC2 instance in the same CloudFormation stack.

### `Resources/ResourcesS3-and-EC2-with-parameters.YAML`

Adds parameters to make the template more reusable. The template allows the user to define the EC2 instance type and S3 bucket name during stack creation.

### `Resources/Resources-with-metaData.YAML`

Adds CloudFormation interface metadata to organize parameters into clear groups. This improves readability and usability when launching the stack from the AWS Management Console.

### `Resources/ResourcesVPC.YAML`

Creates a custom Amazon VPC with DNS hostnames enabled.

### `Resources/full-template.YAML`

Combines multiple infrastructure components into one CloudFormation template, including:

- Amazon VPC
- Subnet
- Amazon S3 bucket
- Amazon EC2 instance
- Parameters for CIDR blocks, names, instance type, and bucket name
- Metadata for organized parameter input

### `web-Application/webApplication.YAML`

Defines a web application infrastructure stack that includes:

- EC2 Launch Template
- Auto Scaling Group
- Application Load Balancer
- Target Group and Listener
- Security Groups
- Route 53 Hosted Zone and DNS record
- CloudWatch Log Group
- CloudWatch CPU alarm
- SNS topic and email subscription
- Stack outputs for the Load Balancer DNS name, Route 53 record name, and SNS topic ARN

The EC2 instances install Apache HTTP Server through user data and serve a simple web page showing the instance ID and public IPv4 address.

## Skills Demonstrated

This project demonstrates practical experience with:

- Infrastructure as Code using AWS CloudFormation
- Writing CloudFormation templates in YAML
- Defining AWS resources declaratively
- Using parameters to make templates reusable
- Organizing CloudFormation inputs with metadata
- Creating networking, compute, storage, monitoring, and notification resources
- Building a basic scalable web infrastructure using an Application Load Balancer and Auto Scaling Group
- Using stack outputs to expose deployed resource information
- Understanding the difference between simple resource templates and multi-resource application stacks
