# 6. What is a Virtual Private Cloud (VPC)?

## Your Private Network in the AWS Cloud

An Amazon VPC is your very own **virtual data center** in the cloud. It is a logically isolated section of the AWS network where you can launch your resources (like EC2 instances) in a virtual network *you define and control*.

## Key VPC Concepts

*   **Isolation:** Your VPC is private and isolated from all other VPCs and users on AWS by default.
*   **IP Addressing:** You define an IP address range for your VPC (e.g., `10.0.0.0/16`). Everything inside your VPC gets an IP address from this range.
*   **Subnets:** You divide your VPC into smaller network segments called **subnets**. A subnet is often tied to a specific **Availability Zone (AZ)**.
    *   **Public Subnet:** Has a route to the internet. Used for resources that need direct public access (e.g., a web server).
    *   **Private Subnet:** No direct route to the internet. Used for resources that should not be publicly accessible (e.g., a database).
*   **Internet Gateway (IGW):** The door between your VPC and the public internet. It's attached to a VPC to enable communication.

## The Default VPC

For getting started quickly, AWS automatically creates a **default VPC** in every region for your account. It comes with:
- A pre-configured public subnet in each AZ.
- An Internet Gateway already attached.
- Everything you need to launch a public-facing EC2 instance immediately.

While great for learning, production applications should use a custom VPC for precise control over networking and security.

## Why VPC is Fundamental

You cannot launch an EC2 instance without a VPC. It is the foundational networking layer for almost all AWS services. Understanding VPCs and subnets is crucial for building secure and well-architected applications.

---

**Next:** [Elastic Compute Cloud (EC2)](./07-elastic-compute-cloud-ec2.md)
