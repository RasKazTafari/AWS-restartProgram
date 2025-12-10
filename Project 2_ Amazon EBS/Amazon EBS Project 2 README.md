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
On the AWS Management Console, in the Search bar, enter and choose EC2 to open the EC2 Management Console.

In the left navigation pane, choose Instances.

An EC2 instance named Lab has already been launched for your lab.

Note the Availability Zone for the Lab instance. It looks similar to the following: us-west-2a

Tip: You might have to scroll to the right to see the Availability Zone column.

In the left navigation pane, for Elastic Block Store, choose Volumes.

You see an existing (8 GiB) volume that the EC2 instance is using.

Choose Create volume, and configure the following options:

Volume type: Choose General Purpose SSD (gp2).

Size (GiB): Enter 1. 
Note: You might be restricted from creating large volumes.

Availability Zone: Choose the same Availability Zone as your EC2 instance (which is us-west-2a in this case).

In the Tags -optional section, choose Add tag, and configure the following options:

Key: Enter Name.

Value: Enter My Volume.

Choose Create volume. 
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%202_%20Amazon%20EBS/Task%201%20Creating%20a%20new%20EBS%20volume.png)

Task 2: Attaching the volume to an EC2 instance

Select My Volume.

From the Actions menu, choose Attach volume.

From the Instance dropdown list, choose the Lab instance.

For the Device name field select /dev/sdb. Commands that you run later in this lab include this device identifier. 

Choose Attach volume.

The Volume state of your new volume is now In-use.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%202_%20Amazon%20EBS/task%202%20Attaching%20the%20volume%20to%20an%20EC2%20instance.png)

Task 3: Connecting to the Lab EC2 instance

On the AWS Management Console, in the Search bar, enter and choose EC2 to open the EC2 Management Console.

In the navigation pane, choose Instances.

From the list of instances, select the Lab instance.

Choose Connect.

On the EC2 Instance Connect tab, choose Connect.

This option opens a new browser tab with the EC2 Instance Connect terminal window.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%202_%20Amazon%20EBS/task%203%20connecting%20to%20the%20lab%20ec2%20connect.png)

Task 4: Creating and configuring the file system

To view the storage that is available on your instance, in the EC2 Instance Connect terminal, run the following command:

df -h
You should see output similar to the following:

devtmpfs        464M     0  464M   0% /dev
tmpfs           473M     0  473M   0% /dev/shm
tmpfs           473M  464K  472M   1% /run
tmpfs           473M     0  473M   0% /sys/fs/cgroup
/dev/nvme0n1p1  8.0G  1.7G  6.4G  21% /
tmpfs            95M     0   95M   0% /run/user/0
tmpfs            95M     0   95M   0% /run/user/1000
These results show the original 8 GB disk volume. Your new volume is not yet shown.

To create an ext3 file system on the new volume, run the following command:

sudo mkfs -t ext3 /dev/sdb
To create a directory to mount the new storage volume, run the following command:

sudo mkdir /mnt/data-store
To mount the new volume, run the following command:

sudo mount /dev/sdb /mnt/data-store
echo "/dev/sdb   /mnt/data-store ext3 defaults,noatime 1 2" | sudo tee -a /etc/fstab
The last line in this command ensures that the volume is mounted even after the instance is restarted.

To view the configuration file to see the setting on the last line, run the following command:

cat /etc/fstab
To view the available storage again, run the following command:

df -h
The output now contains an additional line similar to the following: /dev/nvme1n1

Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        464M     0  464M   0% /dev
tmpfs           473M     0  473M   0% /dev/shm
tmpfs           473M  464K  472M   1% /run
tmpfs           473M     0  473M   0% /sys/fs/cgroup
/dev/nvme0n1p1  8.0G  1.7G  6.4G  21% /
tmpfs            95M     0   95M   0% /run/user/0
tmpfs            95M     0   95M   0% /run/user/1000
/dev/nvme1n1    975M   60K  924M   1% /mnt/data-store
To create a file and add some text on the mounted volume, run the following command:

sudo sh -c "echo some text has been written > /mnt/data-store/file.txt"
To verify that the text has been written to your volume, run the following command:

cat /mnt/data-store/file.txt
   The output displays the text that this command copies to the file. 

![image alt]( https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%202_%20Amazon%20EBS/task%204%20added%20some%20text%20on%20mounted%20volume.png)

Task 5: Creating an Amazon EBS snapshot

On the EC2 Management Console, choose Volumes, and select My Volume.

From the Actions menu, choose Create snapshot.

In the Tags section, choose Add tag, and then configure the following options:

Key: Enter Name.

Value: Enter My Snapshot.

Choose Create snapshot.

In the left navigation pane, choose Snapshots.

The Snapshot status of your snapshot is Pending. After completion, the status changes to Completed. Only used storage blocks are copied to snapshots, so empty blocks do not use any snapshot storage space.

In your EC2 Instance Connect terminal window, to delete the file that you created on your volume, run the following command:

sudo rm /mnt/data-store/file.txt
Note: If terminal is unresponsive, refresh the browser or reconnect as needed.

To verify that the file has been deleted, run the following command:

ls /mnt/data-store/file.txt
The following message displays: ls: cannot access /mnt/data-store/file.txt: No such file or directory

Your file has been deleted.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%202_%20Amazon%20EBS/task%205.1%20snapshot%20created.png)

Task 6: Creating a volume by using the snapshot

On the EC2 Management Console, select My Snapshot.

From the Actions menu, choose Create volume from snapshot.

For Availability Zone, choose the same Availability Zone that you used earlier.

In the Tags - optional section, choose Add tag, and then configure the following options:

Key: Enter Name.

Value: Enter Restored Volume.

Choose Create volume.

To see your new volume, in the left navigation, choose Volumes.

The Volume status of your new volume is Available.

When restoring a snapshot to a new volume, you can also modify the configuration, such as changing the volume type, size, or Availability Zone.

Task 6.2: Attaching the restored volume to the EC2 instance

Select Restored Volume.

From the Actions menu, choose Attach volume.

From the Instance dropdown list, choose the Lab instance.

For the Device name field, choose /dev/sdc. You use this device identifier in a later task.

Choose Attach volume.

The Volume status of your volume is now In-use.

Task 6.3: Mounting the restored volume
To create a directory for mounting the new storage volume, in the EC2 Instance Connect terminal, run the following command:

sudo mkdir /mnt/data-store2
To mount the new volume, run the following command:

sudo mount /dev/sdc /mnt/data-store2
To verify that the volume that you mounted has the file that you created earlier, run the following command:

ls /mnt/data-store2/file.txt
You should see the file.txt file.
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%202_%20Amazon%20EBS/creating%20volume%20from%20snapshot.png)

## Conclusion
This project provided a comprehensive understanding of Amazon EBS, a critical component for persistent storage in the AWS ecosystem. I successfully:
- Gained hands-on experience in the full lifecycle of an EBS volume, from initial creation and attachment to an EC2 instance, to file system configuration and data manipulation.
- Learned the importance and practical application of EBS snapshots for data backup and disaster recovery, understanding how they are stored and can be used to restore data to new volumes.
- Reinforced command-line proficiency by performing tasks like creating file systems, mounting volumes, and verifying data integrity directly on the EC2 instance.

This project significantly enhanced my ability to manage and protect data using AWS's block storage solutions, a vital skill for designing resilient and reliable cloud infrastructures.

