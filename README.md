# Create and Assume Roles in AWS

## Introduction
AWS Identity and Access Management (IAM) is a service that allows AWS customers to manage user access and permissions for the accounts and available APIs/services within AWS. IAM can manage users, security credentials (such as API access keys), and allow users to access AWS resources.

In this lab, we discover how security policies affect IAM users and groups. We implement our own policies while also learning what a role is, how to create a role, and how to assume a role as a different user.

By the end of this lab, you will understand IAM policies and roles, and how assuming roles can assist in restricting users to specific AWS resources.

---

## 🔐 Solution

### 1. Log in to the AWS Console
- Use the credentials provided.
- Region: `N. Virginia (us-east-1)`.

---

### 2. Create the `S3RestrictedPolicy` IAM Policy

- Navigate to S3 → review buckets:
  - `customerdata...`
  - `appconfigprod...` → these will be restricted.
- Navigate to IAM → `Policies` → `Create Policy`.
  - **Service:** S3
  - **Actions:** All S3 actions
  - **Resources:** 
    - All: checked
    - Bucket/Object: Specific ARNs only

- Add the ARNs for:
  - `appconfigprod1`
  - `appconfigprod2`

- **Name the policy:** `S3RestrictedPolicy`
- Create the policy
- Attach it to `user1` under **Users → user1 → Add permissions**

---

### 3. Create the IAM Role

- IAM → `Roles` → `Create role`
- **Trusted entity:** This AWS account
- **Policy:** Attach `S3RestrictedPolicy`
- **Name:** `S3RestrictedRole`

---

### 4. Allow `user2` to Assume the Role

- IAM → Users → `user2` → Copy ARN
- IAM → Roles → `S3RestrictedRole` → Trust Relationships → Edit

```json
"Principal": {
  "AWS": "arn:aws:iam::<account-id>:user/user2"
}
