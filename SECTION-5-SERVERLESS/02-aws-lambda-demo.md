# 02. AWS Lambda - Demo

## Creating and Testing Your First Serverless Function

This demo will guide you through creating a simple AWS Lambda function using the AWS Management Console and testing it immediately.

### Prerequisites

-   An AWS Account.

---

## Step 1: Navigate to the Lambda Dashboard

1.  Log in to the **AWS Management Console**.
2.  In the search bar, type **"Lambda"** and select it under Services.

## Step 2: Create a Function

1.  Click the orange **"Create function"** button.

2.  **Choose options:**
    *   **Author from scratch:** Selected by default.
    *   **Function name:** `hello-world`
    *   **Runtime:** Choose `Python 3.12` (or any supported runtime you prefer).
    *   **Architecture:** `x86_64`
    *   Leave all other settings as default.

3.  Click the orange **"Create function"** button.

## Step 3: Examine the Function

AWS creates a basic function for you. You are now in the function's **Code tab**.

*   The `lambda_function.py` file is open in the inline code editor.
*   You can see the default code, which includes a `lambda_handler` function. This is the entry point.

## Step 4: Test the Function

1.  Click the bright orange **"Test"** button.
2.  A dialog will appear to configure a test event.
    *   **Event name:** `HelloWorldTest`
    *   Keep the default JSON template. This represents the `event` object passed to your function.
3.  Click **"Save"** and then click **"Test"** again.

4.  **View Results:**
    *   The **Execution result** panel will open at the bottom of the screen.
    *   You should see a green box with the message **"Status: Succeeded"**.
    *   Expand the **Details** section to see the function's output: `"Hello from Lambda!"` and the logs from the execution.

## Step 5: Modify the Code

Let's personalize the function.

1.  In the code editor, replace the default code with the following:

    ```python
    import json

    def lambda_handler(event, context):
        # Extract a name from the test event, use "World" as default
        name = event.get('name', 'World')
        
        # Construct the response
        message = f"Hello, {name}! This is AWS Lambda."
        
        # Return a response
        return {
            'statusCode': 200,
            'body': json.dumps(message)
        }
    ```

2.  Click **"Deploy"** to save your changes.

## Step 6: Test the Updated Function

1.  Click the **"Test"** button again.
2.  In the test event dialog, choose **"Configure test event"** from the dropdown.
3.  Replace the default JSON with the following to pass a name:
    ```json
    {
      "name": "Cloud Explorer"
    }
    ```
4.  Click **"Save"** and then click **"Test"**.
5.  You should now see the response: `"Hello, Cloud Explorer! This is AWS Lambda."`

## Step 7: Cleanup

To avoid any potential future costs, delete the function.

1.  From the Lambda Functions list, select the `hello-world` function.
2.  Click **"Actions"** > **"Delete"**.
3.  Confirm deletion by typing `delete` and click **"Delete"**.

---

## Summary

In this demo, you successfully:
1.  Created a serverless Lambda function from the console.
2.  Understood the basic structure of a Lambda handler.
3.  Tested the function with a test event.
4.  Modified the code and deployed the changes.
5.  Cleaned up by deleting the function.

You have now performed the fundamental workflow of AWS Lambda.

---

**Next Section:** [Section 6: Automation & Management](../SECTION-6-AUTOMATION-MANAGEMENT/README.md)
