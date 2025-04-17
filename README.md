# 🌐 AWS Setup with Highly Available Web Application and Load Balancing

### 📜 Project Overview

This AWS CloudFormation template sets up a highly available web application using:
- Two EC2 instances spread across two Availability Zones in the same region.
- One Virtual Private Cloud (VPC) with two public subnets.
- An Internet Gateway for internet access.
- An Application Load Balancer to distribute traffic between EC2 instances.
- Security Groups to allow access via HTTP (port 80).

The goal of this setup is to provide high availability, load balancing, and redundancy across multiple Availability Zones for a scalable web application.

![AWS (2025) horizontal framework (1)](https://github.com/user-attachments/assets/92fa3292-69da-4edb-9f67-65d18334183c)



### 🛠️ Resources Created

- **VPC**: A Virtual Private Cloud to isolate and organize your resources.
- **Subnets**: Two public subnets across two different Availability Zones (AZ-A and AZ-B).
- **Internet Gateway**: Provides access to the internet for the VPC.
- **Security Groups**: Defines rules for HTTP traffic access (port 80).
- **EC2 Instances**: Two EC2 instances running Apache HTTP server in separate Availability Zones.
- **Application Load Balancer**: Distributes traffic between the EC2 instances to ensure high availability.
- **Target Group**: Monitors the health of the EC2 instances and routes traffic accordingly.
- **Listener**: Listens on port 80 to forward traffic to the instances.

### 🔧 Parameters

- **AMI**: The ID of the Amazon Machine Image (AMI) used for the EC2 instances. By default, it is set to the latest Amazon Linux 2 AMI.

### 🚀 How to Deploy

1. **Create a CloudFormation Stack**:
   - Open the AWS Management Console and navigate to CloudFormation.
   - Create a new stack and upload the `cloudformation-template.yaml.txt` file.

2. **Launch the Stack**:
   - Follow the instructions in the CloudFormation Console to deploy the stack.
   - CloudFormation will automatically create and configure the necessary resources.

3. **Access the Application**:
   - Once the stack is deployed, go to the "Outputs" tab in CloudFormation.
   - Copy the DNS name of the Load Balancer and paste it into your browser to access the application.

### 🧐 How It Works

- The application is hosted on two EC2 instances, each located in different Availability Zones.
- The Load Balancer automatically distributes incoming traffic between the instances, ensuring the application remains available even if one instance or Availability Zone fails.
- Each EC2 instance runs an Apache HTTP server that serves a simple HTML page displaying the Availability Zone the application is running in.

### 🧹 Cleanup

To delete all resources:
- Go to the CloudFormation Console.
- Select the stack you created and choose to delete it. CloudFormation will automatically clean up the resources.

---

**Thank you for using this template!**
