# 📂 Project 4: Introduction to AWS Identity and Access Management

## Overview
This project provided a comprehensive introduction to AWS IAM, a fundamental service for securely controlling access to AWS resources. The core objective was to explore and apply IAM concepts such as users, user groups, and policies to manage permissions effectively. This hands-on lab simulated a real-world scenario of assigning different levels of access based on job functions, reinforcing the importance of security and access control in the cloud.

## Project Objectives
- Create and apply an IAM password policy: To enforce security best practices for user authentication across the AWS account.
- Explore pre-created IAM users and user groups: To understand the structure and benefits of organizing users into groups for easier permission management.
- Inspect IAM policies as applied to the pre-created user groups: To analyze how policies define specific permissions (Allow/Deny actions on resources).
- Add users to user groups with specific capabilities active: To practically assign permissions to users by associating them with relevant user groups.
- Locate and use the IAM sign-in URL: To understand and utilize the dedicated login portal for IAM users.
- Experiment with the effects of policies on service access: To verify that the assigned permissions correctly restrict or allow access to AWS services (e.g., S3, EC2).

## Architecture Diagram
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/5b861243cb7510e168849718aa3b609ca32696be/Project%204%3A%20images/Arictechect%20diagram.png)

Task 1: Created an account password policy

In this task, I created a custom password policy for my AWS account. This policy affects all the users associated with the account.
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/password%20rest.png)

Task 2: Explored users and user groups

The S3 Support group has the AmazonS3ReadOnlyAccess policy attached
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/task%202.png)

Task 3: Added users to user groups

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/task%203%20adding%20users.png)

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/all%20user%20groups%20have%201%20user%20task%202.png)

Task 4: Signed in and tested user permissions

User 1 is not authorized to perform this operation  because the user has not been assigned any permissions to use Amazon EC2.
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/all%20user%20groups%20have%201%20user%20task%202.png)

User 1 is an S3-Support group in IAM, and has permission to view a list of S3 buckets and their contents.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/user%201-%20has%20s3%20permissions.png)

User 2 has read only permissions

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/user%202%20had%20ec2%20permissions.png)

I received a message stating Access Denied because user-2 does not have permissions for Amazon S3.
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/user%202%20had%20ec2%20permissions.png)

User 2 only has read permissions and can not stop the instance that is running.
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/IAM%20Project%204%20README.md)

User 3 has Admin permissions
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/user%203%20had%20permissions%20to%20stop%20ec2%20instance%20as%20an%20admin.png)

User 3 has Admin permissions and can stop running instance.
![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project%204_%20IAM/user%203%20stopping%20an%20instance.png)

## Conclusion
This project was critical for building a foundational understanding of AWS Identity and Access Management, a cornerstone of cloud security. I successfully:
- Configured and applied a custom IAM password policy, reinforcing the importance of strong authentication.
- Explored and understood the hierarchy of IAM users, user groups, and policies, learning how to efficiently manage permissions at scale.
- Gained practical experience in assigning permissions by adding users to specific groups and observing the immediate effects on their access to AWS services.
- Validated permission boundaries through hands-on testing, observing how different users were restricted or allowed to perform actions based on their assigned policies.

Overall, this project significantly enhanced my ability to implement robust security controls and manage access effectively within the AWS Cloud, a fundamental skill for designing secure and compliant cloud solutions.






























