# AWS 3-Tier Web Application

## Project Overview

Highly available and scalable 3-tier architecture using AWS.

### Architecture Flow

```text
User
 ↓
Route 53
 ↓
AWS WAF
 ↓
Web ALB
 ↓
Nginx
 ↓
Internal App ALB
 ↓
Tomcat
 ↓
RDS MySQL
```

## AWS Services

* **VPC** – Network isolation
* **Route 53** – DNS
* **AWS WAF** – Web security
* **ALB** – Load balancing
* **EC2** – Nginx & Tomcat
* **Auto Scaling** – Scalability
* **RDS MySQL** – Database
* **IAM** – Access control
* **CloudWatch** – Monitoring
* **SNS** – Email alerts
* **VPC Flow Logs** – Network monitoring
* **NAT Gateway** – Private subnet internet access

## Network Design

```text
Public Subnets
 └── Web ALB → Nginx

Private App Subnets
 └── Internal ALB → Tomcat

Private DB Subnets
 └── RDS MySQL
```

## Security

* Separate Security Groups for each tier
* Application and database tiers are private
* WAF protects the public ALB
* IAM roles control AWS access
* RDS accepts MySQL traffic only from Tomcat

## High Availability

* Multiple Availability Zones
* Web Tier Auto Scaling
* App Tier Auto Scaling
* Load Balancers
* RDS Multi-AZ (if enabled)

## Monitoring

```text
EC2 / ALB / RDS
      ↓
 CloudWatch
      ↓
    Alarm
      ↓
     SNS
      ↓
    Email
```

VPC Flow Logs are used for network traffic monitoring.

## Deployment

The infrastructure is created manually using the **AWS Management Console** and configured using EC2/Linux commands.
