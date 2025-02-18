# Oracle Cloud Infrastructure Foundations Associate Notes

## 1. Introduction to Cloud Computing

### Key Concepts

- **Cloud Computing**: A model for service-oriented computing.
- **Benefits**: Scalability, flexibility, cost savings, access to expertise.
- **Use Cases**: Remote work, AI/ML development, web applications.

### Virtualization

- **What is Virtualization?**: The process of creating isolated virtual machines (VMs).
- **Types**:
    - **Full Virtualization**: Each VM has its own OS and resources.
    - **Thin Client Model**: Clients share a single pool of resources.

#### Tools for Virtualization

- **VirtualBox**: Popular for Windows-based virtualization.
- **VMware**: Industry-standard solution.
- **Hyper-V (Windows)**: Built-in virtualization support in Windows operating systems.

### Networking Basics

- **Key Terminology**:
    - **Host ID**: Unique identifier for a physical or virtual machine.
    - **Network Interface Card (NIC)**: Connects a device to the network.
    - **Subnet Mask**: Defines which part of an IP address belongs to the network and host.
    - **Gateway/Router**: Manages data packet routing.

#### Networking in Virtualization

- **Isolated Virtual NICs**: Each VM has its own NIC, ensuring independence from other VMs on the same host.

### Database Overview

- **Cloud Databases**:
    - **Amazon RDS (Redshift)**: SQL-based relational database service.
    - **Azure SQL Database**: Offers managed and custom databases.
    - **PostgreSQL in AWS**: Open-source relation database with Amazon Web Services.

#### Key Concepts

- **NoSQL Databases**: For unstructured data, e.g., MongoDB on AWS.
- **Elasticsearch**: Search engine for NoSQL documents.
- **Kafka**: Real-time streaming platform.

### Security and Compliance

- **Security best practices**:
    - **Encrypted Storage**: Always use encryption for sensitive data.
    - **Rate Limiting**: Prevent brute force attacks by capping request rates.
    - **Authentication & Authorization (AAA)**: Implement strong security measures.

#### Compliance Standards

- **ISO/IEC 27001**: Information Security Management System.
- **GDPR**: Data privacy regulation for EU citizens.

### Cloud Automation and CI/CD

- **Automation Tools**:
    - **Powershell/VMware Tools**: Used in VirtualBox or VMware Workstation.
    - **Ansible/Cloud Make**: Manage infrastructure provisioning.

#### CI/CD Pipelines

- **Popular Solutions**:
    - **AWS CodePipeline**: Automates application deployment and testing.
    - **OrbitCI for Azure**: Manages CI/CD workflows.

### Oracle Cloud Services

- **Core Services**:
    - **Compute**: EC2 (Linux), VPC, Auto Scaling.
    - **Storage**: S3, EBS, EBFS.
    - **Networking**: Elastic IPs, Route Tables.

#### Key Tools in Oracle Cloud

- **Keyfindings**: Helps identify critical components of the cloud environment.

