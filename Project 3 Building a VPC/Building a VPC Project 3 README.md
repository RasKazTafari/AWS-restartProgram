# 📂 Project 3: Build Your VPC and Launch a Web Server
## Overview
This project focused on building a customized and secure network infrastructure on AWS using Amazon Virtual Private Cloud, and then deploying a web server within this custom network. The core objective was to understand and implement fundamental networking and security concepts in a cloud environment, culminating in the successful launch of a functional web server accessible via the internet. This hands on exercise provided crucial experience in creating isolated network environments and controlling traffic flow.

## Project Objectives
The key objectives for this lab project were:
- Create a Virtual Private Cloud : To establish a logically isolated section of the AWS Cloud where resources can be launched.
- Create subnets: To segment the VPC into public and private subnets across multiple Availability Zones for high availability and controlled access.
- Configure a security group: To act as a virtual firewall, controlling inbound and outbound traffic for the EC2 instance.
- Launch an Amazon EC2 instance into a VPC: To deploy a web server within the custom network and configure it for public access.

## Architecture Diagram

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/01510de5c1ace699f193ce77651712c69b32fa6d/Project%203%20images/Screenshot%202025-08-05%20232109.png)

Task 1: created a VPC
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/511da98c7e59141da4c37f65da69a57c9104ab0f/Project%203%20images/task%201%20creating%20a%20vpc%20in%20action.png)

Task 2: Created additional subnets
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/0720e2a10c2c25857bf7d8fffa6cb7810871de5b/Project%203%20images/task%202%20creating%20a%20subnet.png)

Task 3: Associated the subnets and added routes
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/0720e2a10c2c25857bf7d8fffa6cb7810871de5b/Project%203%20images/task%203.png)








## Conclusion
This project was fundamental in building a strong understanding of AWS networking and security, which are cornerstones of cloud architecture. I successfully:
- Designed and implemented a custom VPC, including public and private subnets across multiple Availability Zones, demonstrating proficiency in network segmentation and high availability.
- Configured crucial networking components like Internet Gateways and Route Tables, understanding how traffic is routed within and outside the VPC.
- Applied robust security measures using Security Groups to control access to the web server, reinforcing the principle of least privilege in cloud environments.
- Deployed and configured an Amazon EC2 instance as a functional web server within the custom VPC, validating the entire network setup from end to end.
Overall, this project significantly enhanced my ability to create secure, scalable, and well-architected network infrastructures on AWS, a critical skill for any aspiring Solutions Architect.

