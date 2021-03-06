# AWS

### High Availability and Fault Tolerant
Using AWS services allows for high avalability of whatever you put in the cloud as you only need an internet connection to access your information. In addition, it also allows for your information to be fault tolerant as it is not just connected to you hard drive but instead connected up to the cloud. 

### On-Premise vs. AWS(Scalability & Elasticity)
With On-Premise companies all their hardware/servers has to be accessable within the company. Companies will typically estimate the future use of their servers based on their users/data so that their companies can continue operating smoopthly. However, this becomes an issue as foreseeing is not always correct, which can lead to over-spending on servers that they don't need or under-spending on servers that they do need. 

With AWS services your servers can be accessed on an on-demand basis. This allows for scalability and elasticity within the company. Scalability refers to the reality that as user-base grows, you have the ability to quickly access more servers to 'scale-up' extremely easy. Elasticity refers to the fact that you can grow, but you can also shrink as needed based on your company needs. 

### What is AWS Compute Services?
Compute Services in AWS is the umbrella of various different services that AWS provides. These services include Amazon EC2, Amazon EBS, Amazon Elastic Load Balancing and AWS Lambda.

### What is AWS Lambda?
AWS lambda is a compute service that runs your back-end code which responds to events such as object uploads such as S3 buckets, updates to Amazon DynamoDB tables, data in Amazon Kinesis streams or in-app activity. 

Lambda handles all the capacity, scaling, and the administration of the infrastructure to run your code. It also provides visibility into performance with Amazon Cloud Watch. 

### Where is Lambda used?
AWS Lambda is used to process images when they're uploaded adding images into S3 buckets. The images are processed and converted into thumbnails based on the device. 

AWS Lambda can also be used to analyze social media data.
Ex. Trending hashtags -> Social Data is added into Amazon Kinesis -> AWS Lambda is trigerred -> The data is stored into a database which can be used by buiseness users.

AWS & Containers
AWS Lambda will make multiple request to multiple containers based on the needs of the application. With an increasing number of request, the number of containers is also increased, and when the request are reduced the number of containers is also reduced. So you pay for what you used saving money for the company. 

### What are Cloud Containers?
Cloud containers provide a streamline, easy-to-deploy and simple method of implementing specific infrastructure requirements. Containers create an isolation boundary at the application rather than the server level. This means that if anything goes wrong with a specific part of the application, it only affects that container and not the whole server. 