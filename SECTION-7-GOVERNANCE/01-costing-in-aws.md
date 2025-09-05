# 01. Costing in AWS

## Understanding the AWS Pricing Philosophy

AWS uses a **pay-as-you-go** pricing model for most of its services. You pay only for the individual services you need, for as long as you use them, without requiring long-term contracts or complex licensing.

## Fundamental Pricing Concepts

*   **Pay for what you use:** You are billed based on your consumption of resources (e.g., per second of EC2 compute time, per GB of S3 storage per month, per million Lambda requests).
*   **Pay less when you reserve:** For services like EC2 and RDS, you can commit to a 1 or 3-year term (Reserved Instances / Savings Plans) to receive a significant discount compared to On-Demand pricing.
*   **Pay less by using more:** As your usage increases, the price per unit (e.g., per GB) often decreases due to volume tiered pricing (e.g., S3).

## What Drives Your Bill?

Your AWS bill is primarily determined by:
1.  **Compute:** Cost of EC2 instances, Lambda functions, etc.
2.  **Storage:** Cost of data stored in S3, EBS volumes, etc.
3.  **Data Transfer:** Cost of data moving **OUT** of AWS to the internet. Data transfer **IN** to AWS is usually free.
4.  **Number of Requests:** Cost of API requests (e.g., S3 PUT requests, DynamoDB read/write requests).

## Key Tools for Cost Management

*   **AWS Pricing Calculator:** Estimate the cost of your architecture before you build it.
*   **AWS Cost Explorer:** Visualize, understand, and manage your AWS costs and usage over time. Create custom reports and forecasts.
*   **AWS Budgets:** Set custom budgets to track your costs and usage. Get alerts via email or SNS when you exceed (or are forecasted to exceed) your budgeted amount.
*   **Cost Allocation Tags:** Apply tags (e.g., `Project:Website`, `Environment:Production`) to your resources. You can then organize and track costs by tag in the Cost Explorer.

## Best Practices for Cost Control

1.  **Use the Free Tier:** Understand its limits and use it for learning and experimentation.
2.  **Set Up Billing Alarms:** Create CloudWatch alarms to alert you when your estimated charges exceed a threshold.
3.  **Terminate Resources You Aren't Using:** This is the easiest way to save money. Regularly review your running EC2 instances, unused EBS volumes, and old S3 buckets.
4.  **Right-Size Your Services:** Don't over-provision. Choose instance types and storage sizes that match your actual workload requirements.
5.  **Use Reserved Instances/Savings Plans:** If you have predictable, steady-state usage, commit to reservations to save up to 72%.

## The Shared Responsibility Model for Cost

*   **AWS's Responsibility:** Providing pricing information and billing tools.
*   **Your Responsibility:** Monitoring your usage, choosing the most cost-effective options, and cleaning up unused resources.

---

**Next:** [Misconceptions](./02-misconceptions.md)
