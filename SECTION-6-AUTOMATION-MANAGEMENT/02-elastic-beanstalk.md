# 02. Elastic Beanstalk

## The Easiest Way to Deploy Web Applications

AWS Elastic Beanstalk is a Platform-as-a-Service (PaaS) that simplifies the process of deploying and scaling web applications. You simply upload your code (e.g., Java, .NET, PHP, Node.js, Python, Ruby, Go, Docker), and Elastic Beanstalk automatically handles the deployment—from capacity provisioning, load balancing, and auto-scaling to application health monitoring.

## How It Works

1.  **You Provide:** Your application code.
2.  **You Choose:** The preconfigured platform (e.g., "Python 3.12", "Node.js", "Docker").
3.  **Elastic Beanstalk Handles:**
    *   Creates and configures the underlying AWS resources (EC2 instances, ASG, ELB, RDS if needed).
    *   Deploys your application.
    *   Sets up monitoring and logging via Amazon CloudWatch.
    *   Manages capacity, load balancing, and automatic scaling.

## Key Benefits

*   **Developer Productivity:** Focus on writing code, not managing infrastructure.
*   **Full Control:** You retain full access to the underlying AWS resources (EC2 instances, etc.) for customization.
*   **Built-in Best Practices:** Automatically configures environments following AWS best practices for security and high availability.
*   **Easy Scaling:** Easily adjust scaling triggers through the console or configuration files.

## Core Concepts

*   **Application:** A logical collection of Elastic Beanstalk components (environments, versions, configurations).
*   **Application Version:** A specific, labeled iteration of your deployable code.
*   **Environment:** The live, running instance of your application version. An application can have multiple environments (e.g., `my-app-prod`, `my-app-dev`).
*   **Environment Tier:** Defines the infrastructure used:
    *   **Web Server Tier:** Handles HTTP(S) requests.
    *   **Worker Tier:** Handles background processing tasks, often using an Amazon SQS queue.

## Use Cases

-   **Quick Prototyping:** Get a web app online in minutes.
-   **Standard Web Applications:** Deploy common web frameworks with minimal configuration.
-   **Microservices:** Deploy individual services that are part of a larger architecture.

---

**Next:** [Elastic Beanstalk - Demo](./22-elastic-beanstalk-demo.md)
