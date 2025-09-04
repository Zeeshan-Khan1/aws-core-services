# 1. DynamoDB

## Fast and Flexible NoSQL Database Service

Amazon DynamoDB is a fully managed, serverless, NoSQL database designed to run high-performance applications at any scale. It offers built-in security, continuous backups, automated multi-region replication, in-memory caching, and data export tools.

## Key Characteristics

*   **NoSQL Database:** Does not use the traditional relational table model with SQL. Instead, it is a key-value and document database.
*   **Serverless:** No servers to manage. You create tables and automatically get read/write performance and storage.
*   **Predictable Performance:** You can specify the required read and write throughput capacity, and DynamoDB will deliver single-digit millisecond performance.
*   **Massively Scalable:** Can handle more than 10 trillion requests per day and peaks of over 20 million requests per second.

## Core Concepts

*   **Tables:** A collection of data (like in RDBMS).
*   **Items:** A single data record in a table (similar to a *row*).
*   **Attributes:** A single data element on an item (similar to a *column*).
*   **Primary Key:** Uniquely identifies each item in a table. It can be:
    *   **Simple Primary Key:** A single attribute (partition key).
    *   **Composite Primary Key:** Two attributes (partition key + sort key). This allows for powerful querying patterns.

## When to Use DynamoDB vs. RDS

| DynamoDB (NoSQL) | RDS (SQL) |
| :--- | :--- |
| **Flexible Schema:** Each item can have different attributes. | **Fixed Schema:** Requires a predefined schema. |
| **Scale-Out Architecture:** Designed for massive, horizontal scaling. | **Scale-Up Architecture:** Primarily scaled by increasing instance size. |
| **Microsecond Latency:** Optimized for fast, predictable performance. | **Millisecond Latency:** Performance depends on query complexity and instance size. |
| **Use Case:** High-traffic web apps, gaming, IoT, ad tech. | **Use Case:** Traditional applications, complex queries, transactions. |

## Use Cases

-   **Serverless Web Apps:** With AWS Lambda and API Gateway.
-   **Microservices:** As a persistent, shared state for stateless services.
-   **Mobile Backends:** Storing user profile data, session data, etc.
-   **Gaming:** Storing player state, leaderboards, and session data.

---

**Next:** [DynamoDB - Demo](./06-dynamodb-demo.md)
