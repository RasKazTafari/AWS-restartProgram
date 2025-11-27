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

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/Launching%20an%20instance.png)


![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/Screenshot%202025-08-06%20175047.png)


Task 2:Logging in to the bastion host 

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/logging%20in%20to%20bastion%20Host%20ec2.png)


Task 3: Launching an EC2 instance using the AWS CLI

Retrieving the AMI to use

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/retreiving%20an%20ami%20for%20bastion%20host.png)

Retrieving the subnet to use

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/public%20subnet%20fo%20bastion%20host.png)

Retrieving the security group to use

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/sg%20.png)

Viewing the contents of the userdata

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/contents%20of%20user%20script.png)

Launched the instance

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/c5a1fb10125a9c3da3ab09dd7e9f85769d5002a9/Project%205%20images/instance%20id%20of%20launched%20instance.png)

## Conclusion
This project provided valuable insights into the various methods of deploying compute resources on AWS, which is fundamental for any cloud professional. I successfully:
- Gained proficiency in launching EC2 instances using both the AWS Management Console and the AWS CLI, understanding the benefits of each approach (quick deployment via console vs. automation via CLI).
- Utilized EC2 Instance Connect for secure and convenient access to instances without managing SSH keys.
- Experienced programmatic control over AWS services by using the AWS CLI to retrieve resource information and launch instances, highlighting its importance for automation and scripting.
- Understood the concept of a bastion host as a secure jump server for managing other instances within a private network.

Overall, this project significantly enhanced my operational skills in EC2 instance management and introduced me to the power of command-line automation in AWS.










