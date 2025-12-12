# 📂 Project 5: Creating Amazon EC2 Instances
## Overview
This project focused on exploring multiple methods for launching Amazon EC2, a core compute service in AWS. The objective was to gain hands-on experience in deploying EC2 instances using both the AWS Management Console and the AWS Command Line Interface, including connecting to them securely. This lab provided practical insights into different deployment strategies and the programmatic control of AWS resources.

## 🎯Project Objectives
- Launch an EC2 instance by using the AWS Management Console: To deploy a virtual server through the graphical user interface.
- Connect to the EC2 instance by using EC2 Instance Connect: To establish a secure browser-based connection to the instance without needing SSH keys.
- Launch an EC2 instance by using the AWS CLI: To deploy a virtual server programmatically, demonstrating automation capabilities.

## Architecture Diagram

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/EC2.png)


Task 1: Launching the Bastion host EC2 instance via the AWS Management Console.

 this task, you launch an EC2 instance by using the AWS Management Console. The instance will be a bastion host from which you can use the AWS CLI.

On the AWS Management Console, in the Search bar, enter and choose EC2 to open the Amazon EC2 Management Console.

From the Launch instance dropdown list, choose Launch instance to open the Launch an instance menu.

Step 1: Choose name and tags
You use tags to categorize your AWS resources in different ways, such as by purpose, owner, or environment. This categorization is useful when you have many resources of the same type; you can quickly identify a specific resource by its tags. Each tag consists of a key and a value, both of which you define.

When you name your instance, AWS creates a key-value pair. The key for this pair is Name, and the value is the name that you enter for your EC2 instance.

In the Name and tags section, for Name, enter Bastion host

 

Step 2: Choose an AMI
In this step, you choose an Amazon Machine Image (AMI). An AMI includes the following:

A template for the root volume for the instance (for example, an operating system or an application server with applications)

Launch permissions that control which AWS accounts can use the AMI to launch instances

A block device mapping that specifies the volumes to attach to the instance when it is launched

The Quick Start list contains the most commonly used AMIs. You can also create your own AMI or select an AMI from the AWS Marketplace, an online store where you can sell or buy software that runs on AWS.

Your bastion host will use Amazon Linux 2.

In the Application and OS Images (Amazon Machine Image) section, for Quick Start, confirm that Amazon Linux is selected. Keep this selection.

Note: This option corresponds to Amazon Linux 2 AMI (HVM) as indicated in the Description. 

Step 3: Choose an instance type
In this step, you choose an instance type, which determines the resources that will be allocated to your EC2 instance. Each instance type allocates a combination of virtual CPU, memory, disk storage, and network performance.

Instance types are divided into families, such as compute optimized, memory optimized, and storage optimized. The name of the instance type includes a family identifier, such as T3 and M5. The number indicates the generation of the instance, so M5 is newer than M4.

Your application uses a t3.micro instance type, which is a small instance that can burst above baseline performance when it is busy. It is suitable for development and testing purposes and for applications that have bursty workloads.

From the Instance type dropdown list, search for and choose t3.micro.

 

Step 4: Configure a key pair
Amazon EC2 uses public key cryptography to encrypt and decrypt login information. To log in to your instance, you must create a key pair, specify the name of the key pair when you launch the instance, and provide the private key when you connect to the instance.

In this lab, you use EC2 Instance Connect to log in to your instance, so you do not require a key pair.

In the Key pair (login) section, from the Key pair name - required dropdown list, choose Proceed without key pair (Not recommended).

 

Step 5: Configure the network settings
You use this pane to configure networking settings.

The virtual private cloud (VPC) indicates which VPC you want to launch the instance into. You can have multiple VPCs, including different ones for development, testing, and production.

You launch the instance in a public subnet within the Lab VPC network.

In the Network settings section, choose Edit.

From the VPC - required dropdown list, choose Lab VPC.

The Lab VPC was created using an AWS CloudFormation template during the setup process of your lab. This VPC includes one public subnet.

In the Subnet dropdown list, notice that Public Subnet is selected by default. Keep this default setting.

In the Auto-assign public IP dropdown list, notice that Enable is selected by default. Keep this default setting.

In the Firewall (security groups) section, notice that Create security group is selected. Configure the following options:

For Security group name - required enter Bastion security group

For Description - required enter Permit SSH connections

A security group acts as a virtual firewall that controls the traffic for one or more instances. When you launch an instance, you associate one or more security groups with the instance. You add rules to each security group that allow traffic to or from its associated instances. You can modify the rules for a security group at any time; the new rules are automatically applied to all instances that are associated with the security group.

 

Step 6: Add storage
You can use this step to add additional Amazon Elastic Block Store (Amazon EBS) disk volumes and configure their size and performance.

You launch the EC2 instance using a default 8 gibibyte (GiB) disk volume. This is your root volume (also known as a boot volume).

In the Configure storage pane, keep the default storage configuration.

 

Step 7: Configure advanced details
Expand the Advanced details pane.

From IAM instance profile dropdown list, choose Bastion-Role.

The Bastion-Role profile grants permission to applications running on the instance to make requests to the Amazon EC2 service. This association of Role is required for the second half of this lab, where you use the AWS CLI to communicate with the Amazon EC2 service.

Leave the default settings for all the other values.

 

Step 8: Launch an EC2 instance
Now that you have configured your EC2 instance settings, it is time to launch your instance.

In the Summary section, review the instance configuration details displayed, and choose Launch instance.

Choose View all instances.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/Launching%20an%20instance.png)


![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/Screenshot%202025-08-06%20175047.png)


Task 2:Logging in to the bastion host 

On the EC2 Management Console, from the list of EC2 instances displayed, choose the  check box for the bastion host instance. 

Choose Connect.

On the EC2 Instance Connect tab, choose Connect to connect to the bastion host.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/logging%20in%20to%20bastion%20Host%20ec2.png)


Task 3: Launching an EC2 instance using the AWS CLI

Retrieving the AMI to use

Run the following script in your EC2 Instance Connect session:

#Set the Region
AZ=`curl -s http://169.254.169.254/latest/meta-data/placement/availability-zone`
export AWS_DEFAULT_REGION=${AZ::-1}
#Retrieve latest Linux AMI
AMI=$(aws ssm get-parameters --names /aws/service/ami-amazon-linux-latest/amzn2-ami-hvm-x86_64-gp2 --query 'Parameters[0].[Value]' --output text)
echo $AMI
Script explanation

The script retrieves the Availability Zone for the running instance using instance metadata.

The script retrieves the Region from the Availability Zone and exports it into the environment for subsequent use.

The script calls the AWS Systems Manager (indicated with the ssm command) and uses the get-parameters command to retrieve the AMI ID from Parameter Store.

The AMI requested was for Amazon Linux 2 (which is the same as the one used for bastion host).

The AMI ID has been stored in an environment variable called AMI.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/Launching%20an%20instance.png)

Retrieving the subnet to use

To retrieve the subnet ID for the public subnet, run the following command:

SUBNET=$(aws ec2 describe-subnets --filters 'Name=tag:Name,Values=Public Subnet' --query Subnets[].SubnetId --output text)
echo $SUBNET
		This script runs the aws ec2 command with the describe-subnets subcommand to retrieve the subnet ID of the subnet named Public Subnet.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/retreiving%20an%20ami%20for%20bastion%20host.png)

Retrieving the security group to use

Run the following command:

SG=$(aws ec2 describe-security-groups --filters Name=group-name,Values=WebSecurityGroup --query SecurityGroups[].GroupId --output text)
echo $SG
		The script runs the aws ec2 command with the describe-security-groups subcommand to retrieve the security group ID of the web security group.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/retreiving%20an%20ami%20for%20bastion%20host.png)

Viewing the contents of the userdata


![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/contents%20of%20user%20script.png)

Launched the instance

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%205%20EC2%20Instances/instance%20id%20of%20launched%20instance.png)

## Conclusion
This project provided valuable insights into the various methods of deploying compute resources on AWS, which is fundamental for any cloud professional. I successfully:
- Gained proficiency in launching EC2 instances using both the AWS Management Console and the AWS CLI, understanding the benefits of each approach (quick deployment via console vs. automation via CLI).
- Utilized EC2 Instance Connect for secure and convenient access to instances without managing SSH keys.
- Experienced programmatic control over AWS services by using the AWS CLI to retrieve resource information and launch instances, highlighting its importance for automation and scripting.
- Understood the concept of a bastion host as a secure jump server for managing other instances within a private network.

Overall, this project significantly enhanced my operational skills in EC2 instance management and introduced me to the power of command-line automation in AWS.










