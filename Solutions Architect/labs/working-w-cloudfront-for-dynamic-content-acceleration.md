# [Working with Amazon CloudFront for Dynamic Content Acceleration](https://explore.skillbuilder.aws/learn/course/464/play/25617/working-with-amazon-cloudfront-for-dynamic-content-acceleration;lp=1046)

Started: June 24, 2024
Completed: June 24, 2024

#### Lab Overview
- demonstrates how to distribute a dynamic website using Amazon CloudFront's global network of edge locations
- focus on creating a CloudFront distribution with the AWS Management Console, and then will examine the features of CloudFront that enable different types of dynamic content to be accelerated to the end user

#### Lab Objectives
- Create an Amazon CloudFront distribution using the AWS Management Console
- Customize your Amazon CloudFront distribution
- Log into your Dynamic Application

## Notes 
- web service that accelerates the delivery of your content to your users through Amazon CloudFront’s global network of edge locations
- ability to deliver your entire website, including dynamic, static, streaming, and interactive content using a global network of edge locations
- optimized to work with other Amazon Web Services
  - S3
  - EC2
  - Elastic Load Balancing
  - Route 53
- Pay only for the content that you deliver through the network
- Ability to add a `cname` to your distribution to make it look like it is coming from your domain
- number of seconds in 24 hours: **86400**
- CloudFront knows where your Amazon EC2 origin server is, and will serve both static and dynamic content to and from the end user

- Features
  - Multiple cache behaviors
    - allows you to specify different behaviors for different types of content
  - Post + Put support
    - accelerates PUT/POST requests to your origin server
  - Zero TTL
    - allows you to specify a TTL of 0 seconds
    - useful for dynamic content not cached at the edge
  - Query String Parameter forwarding:
    - allows you to cache based on query strings
    - forward query strings to your origin server
  - HTTP Cookie forwarding
    - allows you to delivery dynamic based on cookies
    - forward cookies you specify to your origin server
  - Custom error pages
    - deliver custom error pages to your users