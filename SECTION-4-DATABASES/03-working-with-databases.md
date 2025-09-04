# 14. Working with a Database

## Connecting to and Managing Your RDS Database

Creating an RDS instance is just the first step. This lesson covers how to interact with your database once it's running.

## Connection Methods

You typically do not connect to the underlying server running the database. Instead, you connect to the database engine itself using standard tools.

1.  **Command Line:**
    *   **MySQL/MariaDB/Aurora:** Use the `mysql` client.
    *   **PostgreSQL:** Use the `psql` client.
    *   You need the endpoint, port, username, and password from the RDS console.

2.  **Graphical User Interface (GUI):**
    *   Tools like **MySQL Workbench**, **DBeaver**, **pgAdmin**, or **TablePlus** provide a visual interface to manage your database, run queries, and view data.

3.  **Application Connection:**
    *   Your web application (e.g., WordPress, a custom app) will connect to the RDS endpoint using a database connector library in its programming language (e.g., `mysql2` for Node.js, `PHP::PDO` for PHP).

## Key Steps to Connect

1.  **Get Connection Details:** From the RDS Console, select your DB instance. Find the **Endpoint** and **Port**.
2.  **Configure Security:** Ensure your EC2 instance's security group allows outbound traffic to the RDS instance's security group on the database port (e.g., 3306 for MySQL).
3.  **Connect:**
    *   **Example MySQL Command:**
        ```bash
        mysql -h [your-rds-endpoint] -P 3306 -u [master-username] -p
        ```
    *   You will be prompted for the master password.

## Basic Database Operations

Once connected, you can run standard SQL commands:

```sql
-- Show existing databases
SHOW DATABASES;

-- Create a new database for your application
CREATE DATABASE my_wordpress_db;

-- Create a user for your application (don't use the master user!)
CREATE USER 'wp_user'@'%' IDENTIFIED BY 'a-strong-password';

-- Grant privileges to the user on the new database
GRANT ALL PRIVILEGES ON my_wordpress_db.* TO 'wp_user'@'%';

-- Flush privileges to apply changes
FLUSH PRIVILEGES;
Best Practices
Use a dedicated user: Never use the master username/password in your applications. Create a separate user with limited privileges.

Secure your connection: Use SSL/TLS to encrypt data in transit between your application and the database.

Monitor performance: Use Amazon CloudWatch to monitor database metrics like CPU utilization, free storage space, and memory.

Next: Serverless Architecture

