# 13. Relational Database Service (RDS)

## Managed Relational Databases in the Cloud

Amazon RDS is a web service that makes it easier to set up, operate, and scale a relational database in the cloud. It provides cost-efficient, resizable capacity while automating time-consuming administration tasks like hardware provisioning, database setup, patching, and backups.

## Key Benefits of RDS

*   **Managed Service:** AWS handles routine database tasks (provisioning, patching, backup, recovery, failure detection, repair).
*   **High Availability:** Easy to deploy Multi-AZ (Availability Zone) setups for failover support.
*   **Scalability:** Easily scale your database's compute and storage resources with minimal downtime.
*   **Security:** Offers network isolation using Amazon VPC, encryption at rest and in transit, and integration with AWS IAM.
*   **Multiple Database Engines:** Supports popular engines:
    *   **Amazon Aurora** (AWS-native, MySQL/PostgreSQL compatible)
    *   **PostgreSQL**
    *   **MySQL**
    *   **MariaDB**
    *   **Oracle Database**
    *   **Microsoft SQL Server**

## Core RDS Concepts

*   **DB Instance:** The basic building block of RDS, an isolated database environment in the cloud.
*   **DB Engine:** The specific database software and version running on your DB instance (e.g., MySQL 8.0).
*   **Multi-AZ Deployment:** A standby replica of your DB instance in a different Availability Zone for automatic failover.
*   **Read Replicas:** Read-only copies of your DB instance to elastically scale out beyond the capacity constraints of a single DB instance for read-heavy workloads.

## Use Cases

-   **Web and Mobile Applications:** Store user information, product catalogs, etc.
-   **E-commerce Applications:** Transactional data, order history.
-   **Mobile and Online Games:** Player state, leaderboards.
-   **Replacing On-Premises Databases:** Lift-and-shift of existing applications.

---

**Next:** [Working with a Database](./03-working-with-databases.md)
