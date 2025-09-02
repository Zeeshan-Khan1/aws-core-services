# 01. Simple Hosting of a WordPress Site

## Leveraging EC2 for Dynamic Websites

While S3 is perfect for static sites, hosting a **dynamic website** like WordPress—which requires a server, a database, and server-side processing (PHP)—requires a compute service. This is where **EC2** comes in.

## The Architecture: LAMP Stack on a Single Instance

For a simple, low-traffic WordPress site, a common approach is to install the entire LAMP stack on a single EC2 instance:

*   **L**inux (The OS, using the Amazon Linux AMI)
*   **A**pache (The web server software)
*   **M**ySQL (The database, often using Amazon RDS for better management, but can be installed on the same instance for simplicity)
*   **P**HP (The programming language WordPress is built on)

This is often called a "all-in-one" setup and is great for learning and development, though not recommended for high-availability production sites.

## Why EC2 for WordPress?

-   **Full Control:** You have root access to the server and can install any software or configuration needed by WordPress and its plugins.
-   **Flexibility:** You can choose the instance size based on your expected traffic and scale vertically (upgrading to a larger instance type) if needed.
-   **Cost-Effective for Learning:** A `t2.micro` or `t3.micro` instance is Free Tier eligible, making it essentially free to run for a year.

## The Simple Hosting Workflow

1.  **Launch an EC2 Instance:** Use an Amazon Linux or Ubuntu AMI.
2.  **Install the Web Server:** Install and start Apache (`httpd`).
3.  **Install the Database:** Install MySQL server (`mariadb`) and create a database for WordPress.
4.  **Install PHP:** Install PHP and the required extensions (`php`, `php-mysqlnd`).
5.  **Download WordPress:** Download and extract the WordPress files into the web server's directory (e.g., `/var/www/html`).
6.  **Configure Security:** Configure the security group to allow HTTP (port 80) traffic.
7.  **Run WordPress Installer:** Navigate to your instance's public IP address in a web browser and complete the famous "5-minute WordPress install".

## Important Considerations

*   **Maintenance:** You are responsible for OS patches, WordPress updates, and database maintenance.
*   **Security:** You must secure your instance (firewall, SSH access) and application.
*   **Backups:** You are responsible for backing up your website files and database.
*   **Not Highly Available:** If this single instance fails, your website goes down.

For a more robust setup, the next lessons will introduce **Amazon RDS** to manage the database separately, which is a much better practice.

---

**Next:** [Relational Database Service (RDS)](./02-relational-database-service-rds.md)
