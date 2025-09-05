# 03. Elastic Beanstalk - Demo

## Deploying a Sample Web Application

This demo will guide you through deploying a pre-built sample application using Elastic Beanstalk to experience its automation capabilities.

### Prerequisites

-   An AWS Account.

---

## Step 1: Navigate to the Elastic Beanstalk Dashboard

1.  Log in to the **AWS Management Console**.
2.  In the search bar, type **"Elastic Beanstalk"** and select it under Services.

## Step 2: Create a New Application

1.  Click the orange **"Create Application"** button.

2.  **Configure application:**
    *   **Application name:** `my-demo-app`

3.  **Configure environment:**
    *   **Environment tier:** `Web server environment` (default).
    *   Click **"Create"**.

4.  **Configure environment details:**
    *   **Environment name:** `my-demo-app-env`
    *   **Domain:** Leave the auto-generated prefix.

5.  **Platform:**
    *   **Platform:** `Node.js`
    *   **Platform branch:** Keep the default recommended version.
    *   **Platform version:** Keep the default.

6.  **Application code:**
    *   Select **"Sample application"**.
    *   This will deploy a simple "Hello World" Node.js app provided by AWS.

7.  **Presets:**
    *   Leave as **"Single instance"** for cost-saving. (Not highly available but fine for a demo).

8.  Click the orange **"Create environment"** button.

## Step 3: Watch the Magic Happen

Elastic Beanstalk now automatically:
-   Launches an EC2 instance.
-   Creates a security group.
-   Creates an Auto Scaling group.
-   Creates a CloudWatch alarms for monitoring.
-   Deploys the sample application code to the instance.
-   Provides a URL to access your application.

This process will take **5-10 minutes**. Watch the events stream in the console.

## Step 4: Access Your Application

1.  Once the environment status changes to **"OK"** and is **"Healthy"**, your application is live!
2.  Find the **URL** at the top of the environment dashboard (e.g., `my-demo-app-env.abc123.us-east-1.elasticbeanstalk.com`).
3.  Click the URL or copy it into a new browser tab. You should see the message: **"Congratulations! Your AWS Elastic Beanstalk environment is now running."**

## Step 5: Explore the Environment

1.  In the left-hand navigation pane, explore the different sections:
    *   **Dashboard:** Overview of environment health and resources.
    *   **Logs:** Request and view instance logs.
    *   **Monitoring:** View key metrics like CPU utilization and request count.
    *   **Configuration:** See and edit the infrastructure configuration Beanstalk created for you.

## Step 6: Cleanup

To avoid incurring charges, you must terminate the Elastic Beanstalk environment.

1.  Go to the Elastic Beanstalk **Applications** page.
2.  Select the `my-demo-app` application.
3.  Click **"Actions"** > **"Delete application"**.
4.  A dialog will appear. **Ensure the box for "Terminate resources" is checked.** This will delete the EC2 instance and all other associated resources.
5.  Confirm by typing the application name and click **"Delete"**.

---

## Summary

In this demo, you successfully:
1.  Created an Elastic Beanstalk application and environment.
2.  Deployed a sample application with zero manual infrastructure configuration.
3.  Accessed the live, running application.
4.  Explored the managed environment dashboard.
5.  Practiced proper cleanup by deleting the entire application stack.

You have now experienced the core value proposition of AWS Elastic Beanstalk.

---

**Next:** [OpsWorks](./04-opswork.md)
