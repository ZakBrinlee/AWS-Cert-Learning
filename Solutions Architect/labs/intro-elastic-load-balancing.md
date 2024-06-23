# [Introduction to Elastic Load Balancing](https://explore.skillbuilder.aws/learn/course/882/introduction-to-elastic-load-balancing;lp=1046)

Started: June 23, 2024
Completed: June 23, 2024

## Links
- []()
- []()

#### Lab Overview
- covers creating and testing a Network Elastic Load Balancer
- create a Network Elastic Load Balancer and use the two Web Servers as targets
- test the functionality of the load balancer in different scenarios

#### Lab Objectives
- Test connectivity to two web servers that reside in two different Availability Zones
- Create a Network Load Balancer and use the two web servers as Elastic Load Balancer targets
- Test the default functionality of your load balancer
- Enabled Cross-Zone load balancing and test how your load balancer behaves
- Test the behavior of your load balancer during a failure of one of your web servers
- Test the behavior of your load balancer after your web server has recovered from the failure

## Notes 
- Amazon Elastic Load Balancer (Amazon ELB) is a service that automatically distributes incoming application traffic across multiple Amazon EC2 instances
- detects unhealthy instances within a pool and automatically reroutes traffic to healthy instances until the unhealthy instances have been restored
- enable Elastic Load Balancing within a single Availability Zone or across multiple zones for even more consistent application performance

- Network Load Balancer operates at the connection level (Layer 4)
- routing connections to targets (Amazon EC2 instances, microservices, and containers) within Amazon VPC, based on IP protocol data
- load balancer sends a health check request to each registered target every HealthCheckIntervalSeconds seconds, using the specified port, protocol, and ping path
- LB DNS name is resolved to one or more IP addresses, depending on the number of Availability Zones enabled for the load balancer