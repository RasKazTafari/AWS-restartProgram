**Data Protection Using Encryption**

Task 1: Create an AWS KMS key

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/KMS%20Key.png)
**Task 1: Create an AWS KMS key**

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/Configure%20Key.png)

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/AddLabels.png)

**Task 2: Configure the File Server instance**

To open the AWS credentials file, run the following command:

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/ConfigureFileServer.png)

6.  On the **Define key administrative permissions** page, in the **Key
    administrators** section, search for and select the check box for
    voclabs and then choose **Next**.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/Define%20Key.png)

![image alt](****)

**Task 2: Configure the File Server instance**

15. To open the AWS credentials file, run the following command:

vi \~/.aws/credentials

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/ConfigureFileServer.png)

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/ConfigureFileServer2.png)

To view the updated contents of the file, run the following command:

cat \~/.aws/credentials

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/cat.png)

15. To install the AWS Encryption CLI and set your path, run the
    following commands:

pip3 install aws-encryption-sdk-cli

export PATH=\$PATH:/home/ssm-user/.local/bin

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/exportPath.png)

**Task 3: Encrypt and decrypt data**

We first create the demo file:

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/createDemo.png)

Next we encrypt the **secret1.txt** file

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/encrypt.png)

The file has been ecrypted:

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/ecrypted.png)

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Security/symmetricKey.png)




