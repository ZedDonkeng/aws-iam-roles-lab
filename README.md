# aws-iam-roles-lab
# AWS IAM: Creating and Assuming Roles

## Overview
This lab demonstrates how to:
- Create IAM policies to restrict S3 access.
- Define an IAM role and allow a user to assume it.
- Test role assumption and permission enforcement.

## Prerequisites
- AWS account with admin access.
- Two IAM users (`user1`, `user2`).
- Four S3 buckets (two `customerdata`, two `appconfigprod`).

## Lab Steps
[View Detailed Guide](./docs/lab-guide.md)

## IAM Policies
- [S3 Restricted Policy](./policies/s3-policy.json)
- [Role Trust Policy](./policies/role-trust.json)
