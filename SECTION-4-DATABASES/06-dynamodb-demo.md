# 17. DynamoDB - Demo

## Creating a Table and Managing Items

This demo will guide you through creating your first DynamoDB table and performing basic operations using the AWS Management Console.

### Prerequisites

-   An AWS Account.

---

## Step 1: Navigate to the DynamoDB Dashboard

1.  Log in to the **AWS Management Console**.
2.  In the search bar, type **"DynamoDB"** and select it under Services.

## Step 2: Create a Table

1.  Click the orange **"Create table"** button.

2.  **Specify table details:**
    *   **Table name:** `Users`
    *   **Partition key:** `UserID` (Type: `String`)
    *   Leave the sort key empty. We are using a simple primary key for this demo.
    *   Leave all other settings at their **default** values.
        *   **Table settings:** *Default settings*
        *   **Capacity mode:** *Provisioned* (with auto-scaling). This is billable but will stay within Free Tier if you leave the capacity low.

3.  Click the orange **"Create table"** button.

## Step 3: Explore the Table

1.  In the Tables list, click on your new `Users` table.
2.  Explore the different tabs:
    *   **Items:** View, create, and manage the data in your table.
    *   **Metrics:** Monitor the performance and capacity of your table.
    *   **Capacity:** Configure your read/write capacity settings.
    *   **Exports and streams:** Configure advanced features.

## Step 4: Create Items

1.  Go to the **"Items"** tab and click **"Create item"**.
2.  Notice the interface. You can add attributes dynamically.
3.  Add the first attribute:
    *   The `UserID` (partition key) is already there. Set its value to `USR001`.
4.  Click the **"Add new attribute"** button.
    *   Choose type **"String"**.
    *   For attribute name, type `Name`.
    *   For value, type `Alice`.
5.  Add another attribute:
    *   Type **"String"**.
    *   Name: `Email`.
    *   Value: `alice@example.com`.
6.  Click **"Create item"**.

7.  Repeat the process to create a second item:
    *   `UserID`: `USR002`
    *   `Name`: `Bob`
    *   `Email`: `bob@example.com`
    *   `Age` (Number): `28` (This shows the flexible schema - Bob has an attribute Alice doesn't).

## Step 5: Query the Table

1.  In the "Items" tab, switch from "Scan" to **"Query"**.
2.  Since our partition key is `UserID`, we can query for a specific user.
3.  Enter `USR001` for the `UserID` value and click **"Run"**.
4.  You will see only the item for Alice. Query is efficient and fast because it uses the primary key.

## Step 6: Scan the Table

1.  Switch back to **"Scan"**.
2.  Click **"Run"**.
3.  You will see *all* items in the table. A scan operation examines every item in the table, which is less efficient and can be costly on large tables. Use queries whenever possible.

## Step 7: Cleanup

To avoid any potential costs, delete the table.

1.  From the DynamoDB Tables list, select the `Users` table.
2.  Click **"Delete table"**.
3.  Confirm deletion by typing `delete` and click **"Delete"**.

---

## Summary

In this demo, you successfully:
1.  Created a DynamoDB table with a simple primary key.
2.  Added items with a flexible schema.
3.  Experienced the difference between a fast **Query** and a slower **Scan** operation.
4.  Cleaned up by deleting the table.

You have now performed the fundamental workflow of Amazon DynamoDB.

---

**Next Section:** [Section 5: Serverless](../SECTION-5-SERVERLESS/README.md)
