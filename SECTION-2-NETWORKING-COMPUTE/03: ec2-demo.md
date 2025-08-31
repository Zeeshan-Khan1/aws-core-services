# 8. Elastic Compute Cloud - Demo

## Launching Your First Virtual Server

This demo will guide you through launching, connecting to, and terminating an Amazon EC2 instance using the AWS Management Console.

### Prerequisites

-   An AWS Account with access to the Free Tier.
-   A key pair created in your preferred AWS Region. If you don't have one, we'll create it in this demo.

---

## Step 1: Navigate to the EC2 Dashboard

1.  Log in to the **AWS Management Console**.
2.  In the search bar at the top, type **"EC2"** and select **EC2** under Services to open the EC2 Dashboard.

## Step 2: Launch an Instance

1.  On the EC2 Dashboard, click the orange **"Launch instance"** button.

2.  **Name and Tags:**
    -   Enter a descriptive name for your instance (e.g., `My-First-Server`).

3.  **Application and OS Images (AMI):**
    -   Leave the **"Quick Start"** tab selected.
    -   Choose the **Amazon Linux** AMI (usually the top option). This is Free Tier eligible and perfect for learning.

4.  **Instance Type:**
    -   Ensure **`t2.micro`** is selected. This is the instance type eligible for the Free Tier.
    -   Click **"Next: Configure Instance Details"**. We can skip the advanced configuration for this first demo.

5.  **Key Pair (Login):**
    -   This is the most critical step for securing your server.
    -   Select **"Create new key pair"**.
    -   **Key pair name:** Enter a name (e.g., `my-key-pair`).
    -   **Key pair type:** Leave as `RSA`.
    -   **Private key file format:** Leave as `.pem` (for use with SSH on Linux/Mac).
    -   Click **"Create key pair"**. A `.pem` file will automatically download to your computer.
        -   **⚠️ Warning:** This file is your private key. **Never share it** and store it in a secure location. Without it, you cannot connect to your instance.

6.  **Network Settings:**
    -   AWS will create a basic security group for you.
    -   Ensure **"Allow SSH traffic from"** is checked. This allows you to connect to the instance.
    -   For learning, you can also check **"Allow HTTP traffic from the internet"** so we can use this instance as a web server later.

7.  **Configure Storage:**
    -   Leave the default settings (**`8 GiB`** of GP2 storage, which is Free Tier eligible).

8.  **Review and Launch:**
    -   Review all your choices.
    -   Click the orange **"Launch Instance"** button.

9.  **Launch Status:**
    -   Click **"View all instances"** to go back to the EC2 dashboard. Your instance will now be in the **`pending`** state before transitioning to **`running`**.

## Step 3: Connect to Your Instance

1.  In the EC2 Instances list, select your new instance (e.g., `My-First-Server`).

2.  Click the **"Connect"** button at the top.

3.  **SSH Client Tab:**
    -   Follow the example command provided. It will look like this:
        ```bash
        ssh -i "my-key-pair.pem" ec2-user@<your-instance-public-ip>
        ```
    -   **On Mac/Linux:** Open Terminal, navigate to the directory where your `.pem` file is downloaded, and run the command. You may need to run `chmod 400 my-key-pair.pem` first to secure the key's permissions.
    -   **On Windows using Git Bash:** The process is the same as Mac/Linux.
    -   **On Windows using PuTTY:** You will need to use PuTTYgen to convert the `.pem` file to a `.ppk` file first. The Connect dialog provides instructions.

4.  Type **`yes`** when prompted about the authenticity of the host. You are now logged into your virtual server in the cloud!

## Step 4: Run a Basic Command

1.  Once connected, you will see a bash prompt: `[ec2-user@ip-XX-XX-XX-XX ~]$`.

2.  Update the software packages on your server:
    ```bash
    sudo yum update -y
    ```

3.  Install a simple web server (Nginx):
    ```bash
    sudo amazon-linux-extras install nginx1 -y
    sudo systemctl start nginx
    ```

4.  In your web browser, navigate to your instance's **Public IPv4 address** (found in the instance details in the AWS console). You should see the "Welcome to nginx!" page!

## Step 5: Termination (Cleanup)

**⚠️ Important:** Always terminate instances you are no longer using to avoid unexpected charges, especially if they are not Free Tier eligible.

1.  In the EC2 Instances list, select your instance.
2.  Click **"Instance state"** > **"Terminate instance"**.
3.  Confirm the termination. The instance will enter the `shutting-down` and then `terminated` state.

---

## Summary

In this demo, you successfully:
1.  Launched an EC2 instance from the Amazon Linux AMI.
2.  Created and downloaded a key pair for secure access.
3.  Connected to your instance via SSH.
4.  Ran basic commands to update software and install a web server.
5.  Cleaned up by terminating the instance.

This is the foundational workflow for working with virtual servers in AWS.

---

**Next:** [Simple Storage Service (S3)](../SECTION-3-STORAGE/09-simple-storage-service-s3.md)
