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

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Building%20a%20VPC/Screenshot%202025-08-05%20232109.png)

Task 1: created a VPC

In this task, i used the VPC Wizard to create a VPC, an internet gateway, and two subnets in a single Availability Zone. An internet gateway is a VPC component that allows communication between instances in your VPC and the internet.

After creating a VPC, i then added subnets. Each subnet resides entirely within one Availability Zone and cannot span zones. If a subnet's traffic is routed to an internet gateway, the subnet is known as a public subnet. If a subnet does not have a route to the internet gateway, the subnet is known as a private subnet.

The wizard also creates a NAT gateway, which is used to provide internet connectivity to EC2 instances in private subnets.

At the upper-right of these instructions, choose AWS. The AWS Management Console opens in a new tab.

Once you are in the AWS console, type and search for VPC in the search bar at the top. Select VPC from the list.

You are now in the Amazon VPC dashboard. You use the Amazon Virtual Private Cloud (Amazon VPC) service to build your VPC.

Choose Create VPC and configure the following options:

Resources to create: Choose VPC and more

Name tag auto-generation: UnCheck the box Auto-generate

IPv4 CIDR: Enter 10.0.0.0/16

IPv6 CIDR block: Choose No IPv6 CIDR block.

Tenancy: Choose Default.

Number of Availability Zones (AZs) :  1

Number of public subnets:  1

Number of private subnets:  1

Expand Customize subnets CIDR blocks

Public subnet CIDR block in us-west-2a: 10.0.0.0/24
Private subnet CIDR block in us-west-2a: 10.0.1.0/24
NAT gateways: Choose In 1 AZ

VPC endpoints: Choose None

On the Preview pane, name the resources as follows:

VPC: Lab VPC

Subnets (2)

First box, Public subnet one without name tag: Public Subnet 1
Second box, Private subnet one without name tag: Private Subnet 1
Route tables (2)

First box, Public route table without name tag: Public Route Table
Second box, Private route table without name tag: Private Route Table
Choose Create VPC.

On the next screen, Success message is displayed with VPC details. 

Choose View VPC. 

Lab VPC details are displayed as per configuration.


![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Building%20a%20VPC/task%201%20creating%20a%20vpc%20in%20action.png)

Task 2: Created additional subnets

In this task, iz create two additional subnets in a second Availability Zone. This option is useful for creating resources in multiple Availability Zones to provide high availability.

In the left navigation pane, choose Subnets.

To configure the second public subnet, choose Create subnet and configure the following options:

VPC ID: From the dropdown list, choose Lab VPC.
Subnet name: Enter Public Subnet 2    
Availability Zone: No preference
IPv4 CIDR block: Enter 10.0.2.0/24
Choose Create subnet.

The subnet will have all IP addresses starting with 10.0.2.x.

To configure the second private subnet, choose Create subnet and configure the following options:

VPC ID: From the dropdown list, choose Lab VPC.
Subnet name: Enter Private Subnet 2
Availability Zone: No preference
IPv4 CIDR block: Enter 10.0.3.0/24
Choose Create subnet.

The subnet will have all IP addresses starting with 10.0.3.x.

 
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Building%20a%20VPC/task%202%20creating%20a%20subnet.png)

Task 3: Associated the subnets and added routes

In the left navigation pane, choose Route Tables.

Choose Public Route Table

In the lower pane, choose the Subnet associations tab.

Under Subnets without explicit associations, choose Edit subnet associations.

Select the check boxes for Public Subnet 2.

Choose Save associations.

 You now configure the route table that is used by the private subnets.

Choose Private Route Table

In the lower pane, choose the Subnet associations tab.

Under Subnets without explicit associations, choose Edit subnet associations.

Select the check boxes for Private Subnet 2.

Choose Save associations.

 Your VPC now has public and private subnets configured in two Availability Zones:

 
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Building%20a%20VPC/task%203.png)








## Conclusion
This project was fundamental in building a strong understanding of AWS networking and security, which are cornerstones of cloud architecture. I successfully:
- Designed and implemented a custom VPC, including public and private subnets across multiple Availability Zones, demonstrating proficiency in network segmentation and high availability.
- Configured crucial networking components like Internet Gateways and Route Tables, understanding how traffic is routed within and outside the VPC.
- Applied robust security measures using Security Groups to control access to the web server, reinforcing the principle of least privilege in cloud environments.
- Deployed and configured an Amazon EC2 instance as a functional web server within the custom VPC, validating the entire network setup from end to end.
Overall, this project significantly enhanced my ability to create secure, scalable, and well-architected network infrastructures on AWS, a critical skill for any aspiring Solutions Architect.

