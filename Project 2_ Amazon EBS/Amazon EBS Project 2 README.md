# 📂 Project 2: Working with Amazon EBS
## Overview
This project delves into the fundamental aspects of Amazon Elastic Block Store (Amazon EBS), a scalable and high-performance block-storage service for Amazon EC2. The objective was to gain practical experience in the lifecycle management of EBS volumes, from creation and attachment to an EC2 instance, to creating snapshots for data protection and restoring volumes from those snapshots. This hands-on lab provided crucial insights into persistent storage solutions in the AWS Cloud.

## Project Objectives
The key objectives for this lab project were:
- Create an EBS volume: To provision a new block storage device in AWS.
- Attach and mount an EBS volume to an EC2 instance: To connect the newly created storage to a running virtual server and make it accessible to the operating system.
- Create a snapshot of an EBS volume: To create a point-in-time backup of the volume's data for durability and recovery purposes.
- Create an EBS volume from a snapshot: To restore data from a previously created snapshot into a new, usable EBS volume.

## Architecture Diagram
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/16abae5dbbe656960bb60c759472f167d70886df/Project%202%3A%20images/Screenshot%202025-07-03%20150608.png)

Task 1: Creating a new EBS volume
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/16abae5dbbe656960bb60c759472f167d70886df/Project%202%3A%20images/Task%201.png)

Task 2: Attaching the volume to an EC2 instance
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/16abae5dbbe656960bb60c759472f167d70886df/Project%202%3A%20images/task%202%20in%20action.png)

Task 3: Connecting to the Lab EC2 instance
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/16abae5dbbe656960bb60c759472f167d70886df/Project%202%3A%20images/task%203%20connecting%20to%20the%20lab%20ec2%20connect.png)

Task 4: Creating and configuring the file system
![image alt]( https://github.com/Nndoza/AWS-re-start-Program/blob/16abae5dbbe656960bb60c759472f167d70886df/Project%202%3A%20images/task%204%20added%20some%20text%20on%20mounted%20volume.png)

Task 5: Creating an Amazon EBS snapshot
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/16abae5dbbe656960bb60c759472f167d70886df/Project%202%3A%20images/Task%205%20creating%20a%20snapshot.png)

Task 6: Creating a volume by using the snapshot
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/16abae5dbbe656960bb60c759472f167d70886df/Project%202%3A%20images/creating%20volume%20from%20snapshot.png)

## Conclusion
This project provided a comprehensive understanding of Amazon EBS, a critical component for persistent storage in the AWS ecosystem. I successfully:
- Gained hands-on experience in the full lifecycle of an EBS volume, from initial creation and attachment to an EC2 instance, to file system configuration and data manipulation.
- Learned the importance and practical application of EBS snapshots for data backup and disaster recovery, understanding how they are stored and can be used to restore data to new volumes.
- Reinforced command-line proficiency by performing tasks like creating file systems, mounting volumes, and verifying data integrity directly on the EC2 instance.

This project significantly enhanced my ability to manage and protect data using AWS's block storage solutions, a vital skill for designing resilient and reliable cloud infrastructures.

