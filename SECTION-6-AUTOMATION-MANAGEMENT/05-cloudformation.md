# 24. CloudFormation

## Infrastructure as Code (IaC) on AWS

AWS CloudFormation is a service that helps you model and set up AWS resources so you can spend less time managing those resources and more time focusing on your applications. You create a template that describes all the AWS resources you need, and CloudFormation takes care of provisioning and configuring those resources for you.

## The Power of Templates

A CloudFormation template is a JSON or YAML file that serves as a blueprint for your cloud environment.

**Example Snippet (YAML):**
```yaml
Resources:
  MyEC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId: ami-0abcdef1234567890
      InstanceType: t2.micro
      KeyName: my-key-pair
  MyS3Bucket:
    Type: AWS::S3::Bucket
    Properties:
      BucketName: my-unique-bucket-name-2024
Key Benefits
Automation & Repeatability: Deploy your entire infrastructure (VPCs, EC2, RDS, S3, etc.) consistently and repeatedly with a single command.

Infrastructure as Code (IaC): Your infrastructure is defined in code, which can be version-controlled, reviewed, and shared.

Dependency Management: CloudFormation automatically handles the order of resource creation and deletion based on dependencies.

Drift Detection: CloudFormation can detect if someone manually changes a resource it manages and alert you to the configuration "drift".

Safety: You can preview changes to your infrastructure (using change sets) before executing them.

Core Concepts
Template: The JSON or YAML file that defines your infrastructure.

Stack: The set of AWS resources that are created and managed as a single unit when you deploy a CloudFormation template. If you delete a stack, CloudFormation deletes all the resources it created.

Change Set: A summary of the proposed changes to a stack (e.g., add, modify, remove resources) before you actually make them.

Use Cases
Production Environments: Create identical staging and production environments.

Disposable Environments: Quickly spin up and tear down test environments.

Compliance: Ensure infrastructure is deployed following organizational policies every time.

Complex Architectures: Manage intricate systems with many interconnected resources reliably.

Next: CloudFormation - Demo
