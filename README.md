# AWS Auto Scaling Infrastructure Using CloudFormation

## Project Overview

In this project, I deployed a scalable AWS web infrastructure using AWS CloudFormation to automate the provisioning of cloud resources.

The infrastructure includes an Amazon VPC, public and private subnets across two Availability Zones, an Application Load Balancer (ALB), and an EC2 Auto Scaling Group.

The Auto Scaling Group was configured with a desired capacity of two EC2 instances, a minimum of one instance, and a maximum of three instances.

The purpose of this project was to gain practical experience with Infrastructure as Code (IaC), automated EC2 provisioning, load balancing, and building infrastructure designed for scalability and high availability.

I also used the AWS CLI to verify the deployment, confirm that the EC2 instances were healthy, and remove the infrastructure after completing the project to avoid unnecessary AWS charges.

## AWS Services Used

- **AWS CloudFormation:** Used to provision and manage the infrastructure through a YAML template.
- **Amazon VPC:** Provided an isolated network environment for the infrastructure.
- **Amazon EC2:** Hosted the web server instances.
- **EC2 Auto Scaling:** Managed the number of EC2 instances based on the configured capacity.
- **Application Load Balancer (ALB):** Distributed incoming HTTP traffic across the web server instances.
- **EC2 Launch Template:** Defined the configuration used to launch EC2 instances.
- **Security Groups:** Controlled inbound and outbound network traffic.
- **AWS CLI:** Used to deploy, verify, monitor, and delete the infrastructure.

## Infrastructure Configuration

The Auto Scaling Group was configured with:

- **Minimum capacity:** 1 EC2 instance
- **Desired capacity:** 2 EC2 instances
- **Maximum capacity:** 3 EC2 instances
- **Instance type:** t3.micro
- **AWS Region:** eu-west-2 (London)
- **Availability Zones:** eu-west-2a and eu-west-2b


Architecture Overview

The infrastructure was designed to support a scalable web application across two AWS Availability Zones in the London region (eu-west-2).

An Application Load Balancer (ALB) distributes incoming HTTP traffic across EC2 instances managed by an Auto Scaling Group.

The Auto Scaling Group maintains the configured number of EC2 instances and can adjust capacity within the defined minimum and maximum limits.

How the Architecture Works

1. A user sends an HTTP request to the Application Load Balancer.
2. The Application Load Balancer routes the request to a healthy EC2 instance in its target group.
3. The EC2 instance processes the request and returns a response.
4. The Auto Scaling Group maintains the desired number of instances and replaces unhealthy instances when required.
5. The infrastructure uses two Availability Zones to improve resilience and reduce dependence on a single location.

Scalability and High Availability

The Auto Scaling Group was configured with a minimum capacity of one instance, a desired capacity of two instances, and a maximum capacity of three instances.

This configuration provides a foundation for scaling the application as demand changes.

Distributing resources across two Availability Zones also helps improve availability by reducing the impact of an individual Availability Zone failure.

Deployment Process

I used AWS CloudFormation to provision the infrastructure through Infrastructure as Code (IaC), rather than manually creating each resource in the AWS Management Console.

The infrastructure was defined in a YAML template named asg.yaml, which describes the AWS resources and their configurations.

1. Create the CloudFormation Template

I created a YAML template to define the infrastructure resources, including:

* Amazon VPC and networking components
* Public and private subnets across two Availability Zones
* Application Load Balancer and target group
* EC2 Launch Template
* EC2 Auto Scaling Group
* Security Groups

Using CloudFormation allowed me to define the infrastructure in code and deploy the resources as a stack.

2. Deploy the Infrastructure

I used the AWS CLI to deploy the CloudFormation template.

CloudFormation processed the YAML template and created the resources defined within it.

This approach helped me practise automated infrastructure provisioning and understand how AWS resources can be managed together.

3. Verify the Deployment

After deployment, I used the AWS Management Console and AWS CLI to inspect the infrastructure.

I checked the CloudFormation stack status and reviewed the EC2 instances created by the Auto Scaling Group.

I also inspected the Auto Scaling configuration to confirm the minimum, desired and maximum instance capacities.

4. Clean Up AWS Resources

After completing the deployment and verification, I removed the infrastructure to avoid leaving unnecessary AWS resources running and generating additional charges.

This reinforced the importance of managing cloud resources throughout their lifecycle.

Verification and Testing

After deploying the infrastructure using AWS CloudFormation, I used the AWS Management Console and AWS CLI to inspect the resources and verify the deployment.

1. CloudFormation Stack Verification

I reviewed the CloudFormation stack to check its deployment status and confirm that the infrastructure resources had been provisioned.

This helped me understand how CloudFormation manages resources as part of a single stack.

2. EC2 Auto Scaling Group Verification

I inspected the EC2 Auto Scaling Group to review its capacity configuration:

* Minimum capacity: 1 EC2 instance
* Desired capacity: 2 EC2 instances
* Maximum capacity: 3 EC2 instances

The desired capacity specifies how many instances the Auto Scaling Group attempts to maintain under normal conditions.

3. EC2 Instance Verification

I used the AWS CLI to inspect the EC2 instances associated with the deployment.

This allowed me to review their operational status and practise verifying AWS resources from the command line.

4. Application Load Balancer Verification

I reviewed the Application Load Balancer configuration and its relationship with the EC2 Auto Scaling Group.

The load balancer was configured to distribute incoming HTTP traffic to registered targets.

5. Infrastructure Clean-up

After completing the project, I removed the deployed infrastructure to avoid unnecessary AWS charges.

This provided practical experience with the infrastructure lifecycle, including deployment, verification and resource clean-up.

Deployment Screenshots

The following screenshots show the CloudFormation deployment, Auto Scaling Group configuration and EC2 instance verification.

1. CloudFormation Deployment

This screenshot shows the CloudFormation stack deployment and the infrastructure resources created through the YAML template.

2. Auto Scaling Group Configuration

This screenshot demonstrates the Auto Scaling Group configuration, including the minimum, desired and maximum instance capacities.

3. EC2 Instance Health

This screenshot shows the EC2 instances registered with the Auto Scaling Group and their health status.

Both instances were confirmed as InService and Healthy.

4. CloudFormation YAML Configuration

This screenshot highlights the CloudFormation configuration used to define the EC2 Launch Template and Auto Scaling Group.



