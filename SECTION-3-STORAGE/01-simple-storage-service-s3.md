# 01. Simple Storage Service (S3)

## Unlimited, Durable Cloud Object Storage

Amazon S3 (Simple Storage Service) is AWS's flagship object storage service. It is designed to store and retrieve any amount of data from anywhere on the internet, offering industry-leading scalability, data availability, security, and performance.

## Key Concepts

*   **Object Storage:** Unlike block storage (hard drives) or file storage (network drives), S3 manages data as **objects**. An object consists of:
    *   The **data** itself (the file).
    *   **Metadata** (information about the file, e.g., type, date created).
    *   A globally unique **Key** (the full path and filename).
    *   A **Version ID** (if versioning is enabled).

*   **Buckets:** A bucket is a **container for objects** (files). Think of it as the top-level folder. Bucket names must be globally unique across all AWS accounts.

*   **Durability and Availability:**
    *   **99.999999999% (11 9's) Durability:** Designed to sustain the loss of data in two facilities concurrently. You are incredibly unlikely to ever lose a file.
    *   **99.99% Availability:** Designed to be ready and accessible when you need it.

## Common Use Cases

-   **Backup and Archiving:** A secure place for long-term data retention.
-   **Static Website Hosting:** Hosting websites made of HTML, CSS, JS, and images.
-   **Data Lakes:** A central repository to store all your structured and unstructured data.
-   **Application Data:** Storing user uploads, images, videos, and documents.
-   **Software Delivery:** Hosting and distributing software packages and updates.

## Why It's "Simple"

S3 provides a very straightforward, web-based interface and a simple API (`GET`, `PUT`, `DELETE`) to manage your data, making it easy to integrate into any application.

---

**Next:** [S3 - Demo](./02-s3-demo.md)
