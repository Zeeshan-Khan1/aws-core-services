# 03. Simple Storage Service - Demo

## Creating Your First S3 Bucket and Uploading Files

This demo will guide you through creating an S3 bucket, configuring it, and uploading your first file using the AWS Management Console.

### Prerequisites

-   An AWS Account.

---

## Step 1: Navigate to the S3 Dashboard

1.  Log in to the **AWS Management Console**.
2.  In the search bar, type **"S3"** and select **S3** under Services.

## Step 2: Create a Bucket

1.  Click the orange **"Create bucket"** button.

2.  **General Configuration:**
    *   **Bucket name:** Choose a unique, DNS-compliant name (e.g., `my-unique-bucket-name-2024`). Use lowercase letters, numbers, and hyphens.
    *   **AWS Region:** Select the region closest to you or your users for lower latency.

3.  **Object Ownership:**
    *   Leave as **ACLs disabled (recommended)**. This simplifies permissions by using only AWS Identity and Access Management (IAM) policies.

4.  **Block Public Access:**
    *   **⚠️ For this demo, we will make the bucket public.**
    *   **UNCHECK** the box that says **"Block all public access"**.
    *   Acknowledge the warning by checking the box below.

5.  **Bucket Versioning:**
    *   Leave **"Versioning"** disabled for now. This is a powerful feature for protecting against accidental deletions.

6.  **Tags & Default Encryption:**
    *   You can skip these for this demo.

7.  **Review and Create:**
    *   Review your settings.
    *   Click **"Create bucket"**.

## Step 3: Upload an Object

1.  Click on the name of your new bucket in the S3 dashboard list.

2.  Click the **"Upload"** button.

3.  **Add files:**
    *   Click "Add files" and select a file from your computer (e.g., a `cat.jpg` image or a `test.txt` document).

4.  **Permissions (Crucial Step):**
    *   Under "Permissions", choose **"Edit"** manually.
    *   In the "Predefined ACLs" section, select **"Grant public-read access"**. This will make the file downloadable by anyone on the internet.

5.  **Upload:**
    *   Click the **"Upload"** button at the bottom of the page.

## Step 4: Access Your Public Object

1.  Once uploaded, click on the filename inside your bucket.

2.  In the object overview, find the **"Object URL"** field. It will look like:
    `https://my-unique-bucket-name-2024.s3.amazonaws.com/cat.jpg`

3.  Copy this URL and paste it into a new browser tab. You should see your file!

## Step 5: Cleanup (Important!)

To avoid any potential future costs, especially if you uploaded a large file, let's clean up.

1.  Go back to your bucket.
2.  Select the checkbox next to the file you uploaded.
3.  Click **"Delete"** and confirm by typing `permanently delete`.
4.  Navigate back to the main S3 dashboard.
5.  Select the checkbox next to your bucket name.
6.  Click **"Delete"**.
7.  Type the bucket name to confirm deletion and click **"Confirm"**.

---

## Summary

In this demo, you successfully:
1.  Created a globally unique S3 bucket.
2.  Understood the critical security setting for public access.
3.  Uploaded a file and made it publicly accessible.
4.  Accessed the file via its public URL.
5.  Practiced proper cleanup by deleting the object and the bucket.

You have now performed the fundamental workflow of Amazon S3.

---

**Next:** [Static Website Hosting in S3](./03-static-website-hosting-s3.md)
