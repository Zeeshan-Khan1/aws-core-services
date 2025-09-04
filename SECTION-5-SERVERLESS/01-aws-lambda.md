# 01. AWS Lambda

## Run Code Without Thinking About Servers

AWS Lambda is a compute service that lets you run code without provisioning or managing servers. You pay only for the compute time you consume—there is no charge when your code is not running. You can run code for virtually any type of application or backend service with zero administration.

## How Lambda Works

1.  **Upload Your Code:** You supply your code (in supported languages like Node.js, Python, Java, etc.) as a .zip file or container image.
2.  **Set a Trigger:** You configure a Lambda function to be invoked in response to an event (e.g., an HTTP request, a new file in S3, a database update).
3.  **Lambda Runs Your Code:** When triggered, Lambda executes your function by allocating compute resources based on the incoming event.
4.  **Automatic Scaling:** Lambda automatically scales your application by running code in response to each trigger, from a few requests per day to thousands per second.

## Key Features

*   **No Servers to Manage:** AWS automatically manages the underlying compute resources.
*   **Continuous Scaling:** Functions scale automatically and precisely with the size of the workload.
*   **Subsecond Metering:** You are billed for every 1ms of compute time and the number of times your code is executed.
*   **Integrated with AWS:** Can be directly triggered by over 200 AWS services.

## Common Use Cases

-   **Real-time File Processing:** Trigger a Lambda function when a file is uploaded to S3 (e.g., to create thumbnails).
-   **Real-time Stream Processing:** Process data streams from Amazon Kinesis.
-   **Web Backends:** Create RESTful APIs using Lambda and API Gateway.
-   **Scheduled Tasks (Cron):** Run functions on a schedule using Amazon EventBridge.
-   **Chatbots:** Power conversational bots for Slack, Facebook, etc.

## The Lambda Function Handler

The `handler` is the method in your code where Lambda execution begins. It processes input event data and returns a response.

```javascript
// Example Node.js handler
exports.handler = async (event) => {
    console.log('Event:', JSON.stringify(event, null, 2));
    const response = {
        statusCode: 200,
        body: JSON.stringify('Hello from Lambda!'),
    };
    return response;
};
Next: AWS Lambda - Demo
