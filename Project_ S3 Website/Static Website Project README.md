# Building a static website for Zoe Fitness Company

## AWS Cloud Migration Project

## Overview
Zoe Fitness is a growing wellness brand offering online and in-person coaching. The company’s website was initially hosted on a traditional shared hosting service. As the brand expanded, this setup proved limiting and led to several challenges. To overcome these issues, Zoe Fitness migrated its static website built with HTML, CSS, and JavaScript to the AWS Cloud, leveraging AWS Free Tier services to achieve better performance, scalability, and cost efficiency.

## Challenges with Traditional Hosting

- Before the migration, Zoe Fitness faced the following challenges:

- Performance Issues: Slow page load times, especially for international users, due to limited bandwidth and shared server resources.

- Scalability Problems: Traffic spikes during promotions or viral campaigns often caused downtime or poor performance.

- Security Limitations: SSL certificates were either costly or difficult to manage, and there was minimal protection against DDoS attacks.

- High Fixed Costs: Monthly fees were fixed regardless of actual traffic or usage, which was inefficient for variable workloads.

- Poor Global Reach: The website was hosted from a single server in South Africa, causing delays for international visitors.

These limitations made it clear that Zoe Fitness needed a more reliable, scalable, and cost-effective hosting solution.

## Project Objectives
The main objectives of this project were to:

1. Rebuild the website using modern HTML, CSS, and JavaScript with a mobile-responsive layout.

2. Migrate hosting from traditional servers to AWS Cloud.

3. Improve performance and reliability using Amazon S3 and CloudFront.

5. Enable secure HTTPS using AWS Certificate Manager.

6. Reduce hosting costs by leveraging the AWS Free Tier.

7. Provide global reach and a smoother experience for international users.

8. Train Zoe Fitness staff to manage and update the website in the cloud.


## Architectural Diagram
![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/0a5c653345de94de394c6d5e82d96defda8b76fc/Project%3A%20S3%20Website/Screenshot%202025-09-03%20140144.png)

## Steps Taken

### 1. Discovery & Planning

During the discovery phase, we reviewed the existing website and its hosting challenges. We identified the AWS services required for the migration, including Amazon S3, CloudFront, Route 53, and Certificate Manager. At this stage, we also planned improvements such as implementing a mobile-responsive design and optimizing website assets for faster performance.

![image alt](https://github.com/Nndoza/AWS-re-start-Program/blob/eb67930e362f5d5d9dc7a387e95ad433ab655f25/Project%3A%20S3%20Website/Screenshot%202025-09-04%20001427.png)


### 2. AWS Environment Setup

In the setup phase, we created an Amazon S3 bucket to host the static website files. We configured CloudFront to enable faster global content delivery and deployed a free SSL certificate using AWS Certificate Manager to ensure secure browsing with HTTPS. Additionally, Route 53 was configured for domain and DNS management, providing seamless integration with the AWS hosting environment.

### 3. Website Rebuild & Upload

The website was rebuilt using clean HTML, CSS, and JavaScript, incorporating scroll animations and a responsive design for better user experience across devices. Images and other assets were optimized for quicker load times. Once the rebuild was complete, all files were uploaded to S3, proper permissions were set, and caching was configured to enhance performance.

### 4. Go-Live

In the go-live stage, the website domain was linked through Route 53. The site’s performance was tested across multiple global regions using CloudFront, ensuring that content was delivered efficiently to international users. Secure access via HTTPS was also verified to confirm that the SSL certificate was functioning correctly.

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project_%20S3%20Website/Food%20Website/Food%20Website/image/Home%20Page.png)

![image alt](https://github.com/RasKazTafari/AWS-restartProgram/blob/main/Project_%20S3%20Website/Food%20Website/Food%20Website/image/AboutUs.png)

### 5. Training & Handover

Finally, training was provided to the Zoe Fitness team on how to update and manage files directly within S3. Documentation was created to support future updates through GitHub and AWS Amplify pipelines. AWS billing alerts were also configured to help the team monitor usage and remain within Free Tier limits.

## Conclusion

This project highlighted the clear differences between traditional hosting and cloud hosting.

One of the key lessons was that traditional hosting is rigid, costly, and lacks scalability, whereas AWS Cloud provides flexible, pay-as-you-go pricing. Performance and scalability improved significantly after migration thanks to Amazon S3 and CloudFront. Security was also strengthened through AWS Certificate Manager and CloudFront’s built-in DDoS protection.

Another important takeaway was that the AWS Free Tier allows a production-ready static website to run at almost no cost. The structured approach of breaking the migration into distinct phases planning, setup, rebuild, go-live, and training ensured that the project was completed smoothly and successfully.

By moving to AWS, Zoe Fitness achieved faster performance, stronger security, global scalability, and cost efficiency. This migration also established a future-proof foundation that will support potential growth, including the addition of e-commerce or membership features.


