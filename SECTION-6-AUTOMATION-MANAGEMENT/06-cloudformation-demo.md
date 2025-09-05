# 06. CloudFormation - Demo

## Deploying Infrastructure from a Template

This demo will guide you through using a sample CloudFormation template to create a stack, which will automatically provision an S3 bucket.

### Prerequisites

-   An AWS Account.

---

## Step 1: Prepare a Sample Template

1.  Copy the following YAML code into a text editor and save it as `s3-bucket-template.yaml`.
    This is a simple template that creates a single S3 bucket.

    ```yaml
    AWSTemplateFormatVersion: '2010-09-09'
    Description: 'A simple CloudFormation template to create an S3 bucket for demo purposes.'
    Resources:
      MyDemoS3Bucket:
        Type: 'AWS::S3::Bucket'
        Properties:
          BucketName: !Sub 'cf-demo-bucket-${AWS::AccountId}' # Creates a unique name
    Outputs:
      BucketName:
        Description: "The name of the S3 bucket"
        Value: !Ref MyDemoS3Bucket
    ```

## Step 2: Navigate to the CloudFormation Dashboard

1.  Log in to the **AWS Management Console**.
2.  In the search bar, type **"CloudFormation"** and select it under Services.

## Step 3: Create a Stack

1.  Click the orange **"Create stack"** button.
2.  Choose **"With new resources (standard)"**.

3.  **Specify template:**
    *   Select **"Upload a template file"**.
    *   Click **"Choose file"** and select your `s3-bucket-template.yaml` file.
    *   Click **"Next"**.

4.  **Specify stack details:**
    *   **Stack name:** `my-demo-s3-stack`
    *   Click **"Next"**.

5.  **Configure stack options:**
    *   You can skip all these settings for this demo. Click **"Next"**.

6.  **Review:**
    *   Review the stack configuration. At the bottom, you must check the box: **"I acknowledge that AWS CloudFormation might create IAM resources."**
    *   Click **"Submit"**.

## Step 4: Monitor Stack Creation

1.  You are taken to the CloudFormation Stacks page. Your stack will have the status **`CREATE_IN_PROGRESS`**.
2.  Click the stack name to see the detailed events. CloudFormation is now creating the S3 bucket.
3.  Wait for the status to change to **`CREATE_COMPLETE`**. This should only take a minute.

## Step 5: Verify Resources and Outputs

1.  In the stack details, select the **"Outputs"** tab.
2.  You will see the **`BucketName`** output with the value of your newly created S3 bucket. The name will include your AWS Account ID to ensure it's globally unique.
3.  Go to the **S3 service console** to confirm the bucket was created successfully.

## Step 6: Delete the Stack (Cleanup)

The true power of CloudFormation is that it can also clean up everything it created.

1.  In the CloudFormation Stacks list, select your `my-demo-s3-stack`.
2.  Click **"Delete"**.
3.  Confirm deletion by clicking **"Delete stack"**.
4.  The status will change to **`DELETE_IN_PROGRESS`**. CloudFormation will now automatically delete the S3 bucket.
5.  Go to the S3 console to verify the bucket has been removed.

---

## Summary

In this demo, you successfully:
1.  Created a basic CloudFormation template in YAML.
2.  Used the template to create a CloudFormation stack.
3.  Watched CloudFormation automatically provision the defined resource (an S3 bucket).
4.  Viewed the stack outputs.
5.  Demonstrated easy cleanup by deleting the stack, which deleted the resource.

You have now performed the fundamental workflow of AWS CloudFormation.

---

**Next:** [My Application Architecture](./07-my-application-architecture.md)
