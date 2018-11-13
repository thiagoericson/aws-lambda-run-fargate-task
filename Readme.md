# Boilerplate AWS Lambda - ECS Trigger - via Console

## Description

A simple code in Python 3.6 for running on AWS Lambda that trigger ECS (Fargate).

## How setup

1. Access [Lambda Management Console](https://console.aws.amazon.com/lambda);

2. Click on **Create function**;

3. Select **Author from scratch**;

4. Put **Name** for the function;

5. Select **Python 3.6** on Runtime Select-box;

6. On Role, select/create a role with the *inline policy* recommended below;

7. Then, click on **Create function**;

8. Now, we are on Lambda Function;

9. Copy the code on handle.py, on this repo, and Paste on lambda_function.py, inside the Function code.

## Inline Policy recommended

```js
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1512361420000",
            "Effect": "Allow",
            "Action": [
                "ecs:RunTask"
            ],
            "Resource": [
                "*"
            ]
        },
        {
            "Sid": "Stmt1512361593000",
            "Effect": "Allow",
            "Action": [
                "iam:PassRole"
            ],
            "Resource": [
                "arn:aws:iam::************:role/ecsTaskExecutionRole" // replace (******) with your Account ID
            ]
        }
    ]
}
```