                                            Reliability Project
This repository encompasses the documentation for my final project at Makers Academy within the Cloud/DevOps Engineering specialization track.

Project Overview 
Our team was engaged by an organization providing software and services to multiple veterinary hospitals. The primary objective was to improve the reliability of their existing application, HOSP, while preserving its core functionality. Additionally, we took on the responsibility of implementing enhancements and introducing new features to enhance the overall user experience.

The HOSP System Regrettably, due to licensing issues, access to the source code was unavailable. However, we had access to the AWS load balancer and API documentation.

image.png


Approach and Investigation 
Our initial focus centered on bolstering the system's reliability. Using Amazon CloudWatch, we analyzed application logs to address user-reported issues. This investigation revealed a significant number of failed API requests at server endpoints, providing crucial insights into the root causes of user problems.

NGINX Reverse Proxy Server Implementation 
To address failed API requests, we deployed an NGINX reverse proxy server on an AWS EC2 instance. This strategic deployment automatically retried failed requests, resulting in a notable reduction in overall failures. This solution enhanced the system's resilience and ensured a smoother user experience.


image.png

Implemented Improvements 
With improved reliability, our attention shifted to implementing key enhancements:

1. Enhanced Security with HTTPS: We prioritized implementing the HTTPS protocol for increased system security. This involved deploying an AWS CloudFront CDN and enforcing encrypted communication across all traffic. The transition to HTTPS significantly enhanced data privacy and secured sensitive information exchanged within the system.

2. X-Ray Results Integration: Responding to a request from hospital nurses, we introduced a feature allowing the saving of X-Ray results directly within patient notes. This streamlined the process and created a comprehensive patient record. Using AWS Lambda and Python, we developed a solution that captured the API response from the screening server and initiated a new POST request back to the patient notes endpoint, ensuring the original request was delivered to the user.

3. Audit Trail Functionality: To enhance system transparency and security, we implemented an audit trail feature using an AWS Lambda function. This feature allowed administrators to track and monitor all user activities, facilitating the prompt identification of potential security breaches. The audit trail utilized AWS Athena and CloudWatch to query user interactions and provide results as a downloadable CSV file.

image.png


These improvements collectively elevated the system's functionality, user experience, and security standards. Leveraging serverless technology enhanced scalability and significantly reduced operational overheads, providing hospital staff and patients with a consistently reliable, high-performing system for uninterrupted focus on core tasks.

image.png

