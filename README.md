# Building and Securing a Scalable VPC with AWS CLI

## Project Overview
Automated the creation and configuration of a secure, scalable Virtual Private Cloud (VPC) in AWS using CLI commands, ensuring seamless internet connectivity and resource isolation for cloud applications.

## Technologies Used
- AWS CLI
- Amazon VPC (Virtual Private Cloud)
- Internet Gateway
- Subnets
- Route Tables
- Security Groups

## Project Details
**Status**: Completed

### Architecture Overview
This project leverages Amazon VPC and AWS CLI to create a secure and scalable cloud environment with internet access. The automated setup includes:

- **VPC**: Acts as a private network to house your resources in a secure environment.
- **Subnets**: A public subnet for resources that need internet access (like EC2 instances).
- **Internet Gateway**: Enables communication between the resources in the VPC and the internet.
- **Route Table**: Directs traffic within the VPC and allows internet access through the Internet Gateway.
- **Security Groups**: Provides security and access controls for resources within the VPC.

This architecture, automated through AWS CLI, allows for rapid deployment and efficient management of cloud networks while ensuring security and scalability.

### Implementation Steps
1. **Create a Virtual Private Cloud (VPC)**
    - Command:
    ```bash
    aws ec2 create-vpc --cidr-block 10.0.0.0/16
    ```
    - Result: Successfully created VPC with ID `vpc-0a407c238e2a3c8aa`.

2. **Set Up a Subnet**
    - Command:
    ```bash
    aws ec2 create-subnet --vpc-id vpc-0a407c238e2a3c8aa --cidr-block 10.0.1.0/24
    ```
    - Result: Successfully created Subnet with ID `subnet-01ae8fc8816f25db1`.

3. **Attach an Internet Gateway**
    - Command:
    ```bash
    aws ec2 create-internet-gateway
    aws ec2 attach-internet-gateway --internet-gateway-id igw-046fc5bc242644a8a --vpc-id vpc-0a407c238e2a3c8aa
    ```
    - Result: Successfully attached Internet Gateway with ID `igw-046fc5bc242644a8a`.

4. **Update Route Table for Internet Access**
    - Command:
    ```bash
    aws ec2 create-route --route-table-id rtb-xxxxx --destination-cidr-block 0.0.0.0/0 --gateway-id igw-046fc5bc242644a8a
    ```
    - Result: Internet access for the VPC is now configured.

5. **VPC Fully Connected to the Internet**
    - Result: Your VPC is now fully internet-enabled, allowing seamless communication with external resources.

## Project Results
The automated VPC setup using AWS CLI successfully created a secure and scalable cloud network. With subnets, an Internet Gateway, and route table updates, the environment supports seamless communication for cloud resources while maintaining security and scalability.

