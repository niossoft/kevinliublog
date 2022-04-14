---
author: "Kevin Liu"
title: "AWS Solutions Architect Associate: IAM"
date: 2022-04-14T18:45:06+09:00
description: "IAM: Identity and Access Management"
draft: false
hideToc: false
enableToc: true
enableTocContent: false
author: Kevin Liu
authorEmoji: 👻
series:
- AWS
tags: 
- AWS
- IAM
image: images/logo/amazon-web-services-icon.svg
---
#### AWS has Global Services:
- Identity and Access Management(IAM)
- Route 53(DNS service)
- CloudFront(Content Delivery Network)
- WAF(Web Application Firewall)
#### Most AWS services are Region-scoped:
- Amazon EC2(Infrastructure as a Service)
- Elastic Beanstalk(Platform as a Service)
- Lambda(Function as a Service)
- Rekognition(Software as a Service)

**NOTICE**: Must to make sure region-scoped services are available in your region. In oreder to best peformance, please choice the region geographically close to you.

### IAM Section
>IAM = Identity and Access Management, Global service

Root account created by default, shouldn't be userd or shared.
Users are people within your organization, and can be grouped.
Group only contain user, no other groups.

#### IAM: Permissions
- Users or Groups can be assigned JSON documents called policies. 
- These policies define the permissions of the users
- In AWS you apply the least **privilege principle**: don't give more permissions than a user needs
- root account, it can do anything you want. Therefore, it's a very dangerous account to use.

#### IAM Policies inheritance
- Individual users can inherit the group policy.

#### IAM Policies Structure
+ Consist of 
    + Version: policy language version, always include "2012-10-17"
    + Id: an identifier for the policy(optional)
    + Statement: one or more individual statements(required)

+ Statements consist of
    + Sid: an identifier for the statement(optional)
    + Effect: whether the statement allows or denies access(Allow, Deny)
    + Principal: account/user/role to which this policy applied to
    + Action: list of actions this policy allows or denies
    + Resource: list of resources to which the actions applied to
    + Condition: conditions for when this policy is in effect(optional)

#### IAM - Password Policy
+ Strong passwords = higher security for your account
+ In AWS, you can setup a password policy:
    + Set minimun password length
    + Require specific character types:
        + including uppercasse letters
        + lowercase letters
        + numbers
        + non-alphanumeric characters
+ Allow all IAM users to change their own passwords
+ Require users to change their password after some time(passwrod expiration)

#### Multi Factor Authentication - MFA
+ Users have access to your account and can possibly change configurations or delete resources in your AWS account
+ You want to protect your Root Account and IAM Users
> MFA = password you know + security device you won

**Main benefit** of MFA:
if a password is stolen or hacked, the account is not compromised 

#### IAM Roles for Services
+ Some AWS service wiil need to perform actions on your behalf
+ To do so, we will assign permissions to AWS services with IAM Roles
+ Common roles:
    + EC2 Instance Roles
    + Lambda Function Roles
    + Roles for CloudFormation





