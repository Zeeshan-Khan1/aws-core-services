# 04. OpsWorks

## Configuration Management Using Chef and Puppet

AWS OpsWorks is a configuration management service that provides managed instances of Chef and Puppet. These are automation platforms that allow you to use code to automate the configurations of your servers. OpsWorks lets you leverage these tools without the need to install and maintain your own configuration management servers.

## Key Concepts

*   **Stacks:** A stack is a collection of AWS resources that you manage as a single unit. It's the top-level container in OpsWorks.
*   **Layers:** A layer represents a set of EC2 instances that serve a specific purpose (e.g., a "web layer" running Apache, an "application layer" running Node.js, a "database layer"). Layers define how to configure instances and which packages to install.
*   **Instances:** These are the EC2 instances launched into your layers. Their configuration is managed by the layer's recipes/manifests.
*   **Apps:** An app represents the application code you want to deploy to instances in a layer (e.g., your PHP or Node.js application files).
*   **Recipes (Chef) / Manifests (Puppet):** These are the scripts that contain the code (Ruby for Chef, DSL for Puppet) to configure your operating system and applications.

## How OpsWorks Works

1.  You define a **Stack**.
2.  You add **Layers** to the stack (e.g., a load balancer layer, a web server layer).
3.  You assign **Recipes/Manifests** to lifecycle events (Setup, Configure, Deploy, Undeploy, Shutdown) for each layer.
4.  You launch **Instances** into the layers.
5.  OpsWorks runs the Chef/Puppet code on these instances during their lifecycle, ensuring they are configured exactly as specified.
6.  You deploy your **Application** code.

## OpsWorks vs. Other Services

| | **Elastic Beanstalk** | **CloudFormation** | **OpsWorks** |
| :--- | :--- | :--- | :--- |
| **Focus** | Application Deployment | Infrastructure Provisioning | **Server Configuration** |
| **Method** | Platform-based | Declarative Templates | **Imperative Scripts (Chef/Puppet)** |
| **Control** | Limited to platform choices | Full control over resources | **Full control over server state** |

## Use Cases

-   **Complex Application Stacks:** Managing multi-tier applications (web, app, database) with precise configuration requirements.
-   **Existing Chef/Puppet Users:** Migrating existing configuration management scripts to AWS.
-   **Compliance and Auditing:** Ensuring every server is configured identically according to strict security and compliance policies.

## When to Choose OpsWorks

Choose OpsWorks if you have complex server configuration needs and want to use industry-standard tools like Chef or Puppet to manage your infrastructure as code at the OS level.

---

**Next:** [CloudFormation](./05-cloudformation.md)
