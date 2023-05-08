# IAM


## Access Advisor

Access advisor shows the service permissions granted to a user and when those services were last accessed.
You can use this information to revise your policies. Accordingly.

## IAM Credentials report

You can generate and download a credential report that list all users in your account and the status
of their various credentials, including passwords, access keys and MFA devices. And not use to review permissions.

## IAM permission boundary

It's only atached to Users and Roles.
Cannot atached to gorups.

## Policy Template

```json
{
    "Version": "2012-10-17",
    "Statement": {
        "Effect": "Allow",
        "Principal": {"AWS": "arn:aws:iam::777788889999:user/bob"},
        "Action": [
            "s3:PutObject",
            "s3:PutObjectAcl"
        ]
    },
}
```

```json
{
    "Version": "2012-10-17",
    "Statement": {
        "Effect": "Allow",
        "Resource": "arn:aws:dynamodb:us-east-2:777788889999:table/Books",
        "Action": [
            "dynamodb:*"
        ]
    },
}
```