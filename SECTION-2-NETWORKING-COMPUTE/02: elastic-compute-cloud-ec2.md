# 7. Elastic Compute Cloud (EC2)

## Virtual Servers in the Cloud

Amazon EC2 is the core compute service of AWS. It provides resizable **virtual machines**, called **EC2 instances**, that you can launch in minutes.

## Why "Elastic"?

The name comes from its key feature: the ability to **instantly scale capacity up or down** based on demand. You can easily add more instances to handle traffic spikes or remove them to save costs during quiet periods.

## Key EC2 Concepts

*   **Instance Types:** EC2 offers a wide variety of instance types optimized for different use cases.
    *   **General Purpose (e.g., t3, m5):** Balanced compute, memory, and networking. Good for web servers.
    *   **Compute Optimized (e.g., c5):** Ideal for compute-intensive tasks like batch processing.
    *   **Memory Optimized (e.g., r5):** Designed for memory-intensive workloads like databases.
    *   **Storage Optimized (e.g., i3):** Built for workloads that require high, sequential read/write access.

*   **Amazon Machine Image (AMI):** A template that contains the software configuration (OS, application server, applications) needed to launch your instance. It's like a DVD you insert into a blank computer.

*   **Key Pairs:** Used to securely connect to your Linux instances. AWS stores the public key, and you download and keep the private key (.pem file) secret.

*   **Security Groups:** A virtual **firewall** for your EC2 instances. They control inbound and outbound traffic. This is a fundamental security control.

## Pricing Models

*   **On-Demand:** Pay by the second with no long-term commitment. Default and most flexible option.
*   **Savings Plans / Reserved Instances:** Significant discount (up to ~70%) for a commitment to consistent usage for a 1 or 3-year term.
*   **Spot Instances:** Bid on unused EC2 capacity for up to 90% discount. Can be terminated by AWS with little warning. Perfect for fault-tolerant, flexible workloads.

## The EC2 Workflow

1.  Choose an AMI (e.g., Ubuntu Linux, Windows Server).
2.  Choose an Instance Type (e.g., t3.micro for Free Tier).
3.  Configure Network and Security Groups.
4.  Select or Create a Key Pair.
5.  Launch the Instance.

In the next lesson, we will walk through this process in a hands-on demo.

---

**Next:** [EC2 - Demo](./08-ec2-demo.md
