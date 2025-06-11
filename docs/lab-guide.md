# Lab Guide: Create and Assume IAM Roles

. Create the S3RestrictedPolicy IAM Policy
Navigate to S3 and review the four buckets:

Two with customerdata in the name.

Two with appconfigprod in the name.

You will restrict access to the appconfigprod buckets.

Open IAM in a new tab.

Under Access Management, select Policies > Create Policy.

Under Service, select S3.

Under Actions, select All S3 actions (s3:*).

Under Resources:

For bucket, manually add the ARNs of the two appconfigprod buckets.

For object, select Any.

Click Next, name the policy S3RestrictedPolicy, and Create Policy.

Attach the policy to user1:

Go to Users > user1 > Add permissions > Attach policies directly.

Select S3RestrictedPolicy and confirm.
