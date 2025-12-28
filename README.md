# Creating a Basic Lambda Function to Shut Down an EC2 Instance

This project demonstrates how to stop a running Amazon EC2 instance using an AWS Lambda function.
It helps understand basic automation using AWS services for cost and resource management.

---

## Objective
- To automate the shutdown of an EC2 instance using AWS Lambda.
- To understand the use of IAM roles and permissions for secure service access.

---

## Prerequisites
- An active AWS account
- Basic knowledge of AWS Console
- A running EC2 instance

---

## Step 1: Login to AWS Management Console

- Open a web browser and go to the AWS Management Console.
- Login using valid AWS account credentials.



---

## Step 2: Select Trusted Entity for IAM Role

- Navigate to **IAM → Roles → Create role** and select **AWS service** as the trusted entity.
- Choose **Lambda** as the use case so the Lambda function can assume this role.

![Select Trusted Entity](screenshots/01-iam-select-trusted-entity.png)


## Step 3: Create Custom IAM Policy

- Navigate to **IAM → Policies → Create policy** and switch to the **JSON** tab.
- Paste a custom policy that allows CloudWatch logging and EC2 stop actions.

![Create IAM Policy JSON](screenshots/02-create-iam-policy-json.png)

## Step 4: Review and Create IAM Policy

- Review the policy permissions and provide a policy name (for example, **ec2lambdapolicy**).
- Confirm the permissions and click **Create policy** to save it.

![Review and Create IAM Policy](screenshots/03-review-and-create-iam-policy.png)

## Step 5: Attach IAM Policy to Role

- Navigate to **IAM → Roles**, create a role for **Lambda**, and proceed to the **Add permissions** step.
- Search for the custom policy (**ec2lambdapolicy**) and attach it to the role.

![Attach IAM Policy to Role](screenshots/04-attach-policy-to-role.png)

## Step 6: Review and Create IAM Role

- Provide a role name (for example, **ec2role**) and review the trusted entity and attached permissions.
- Confirm the configuration and click **Create role** to complete the IAM role setup.

![Review and Create IAM Role](screenshots/05-review-and-create-iam-role.png)



