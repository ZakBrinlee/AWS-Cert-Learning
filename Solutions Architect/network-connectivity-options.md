# [AWS Network Connectivity Options](https://explore.skillbuilder.aws/learn/course/1754/play/41376/aws-network-connectivity-options;lp=1046)

Started: June 23, 2024
Completed: June 23, 2024

## Links
- [Amazon Virtual Private Cloud Documentation](https://docs.aws.amazon.com/vpc/)
- [AWS Virtual Private Network Documentation](https://docs.aws.amazon.com/vpn/)

## Notes
### UNDERSTANDING CONNECTIVITY CONCEPTS
#### General Concepts
- Multi-tier architecture
  - grouping of different components by function, into tiers/layers
  - Commonly used model is 3-tier architecture
    - Presentation tier
    - Application tier
    - Data tier

- High availability
  - Network designed to avoid loss of communication between components (internal/external)
  - accomplished by reducing/managing failures and minimizing downtime
    - implementation of redundant components
    - deployment of parallel systems to handle traffic
    - eliminate single points of failure

- Hybrid network
  - combination of on-premises and cloud resources

- High Performance
  - provide the fastest experience by guiding data along the shortest path

#### Connectivity Concept Benefits
- Multi-tier architecture
  - separation of concerns
  - shield against threats
  - data is placed at the end of the chain, reducing the risk of nefarious access

- Multi-VPC architecture
  - isolation of resources
  - control over traffic flow
  - ability to scale
  - robust analytics

- High availability
  - Not meant to element failure, but the ability to recover quickly
  - anticipate and plan for failure
  - building in redundancy

- Hybrid network
  - connects on-premises resources to cloud resources
  - utilize cloud for agility and scalability

- High Performance
  - reduce latency (Key concept/goal)
  - Some latency causes
    - packet loss
    - variations in latency or time delay (jitter)
    - bandwidth limitations
    - inefficient protocols
    - physical distance
  - To Reduce - Consider
    - physical proximity between nodes (components)
    - quality of routes
    - location of user to data
    - avg package delay under network cost constraints
    - memory resources
    - traffic patterns

### Understanding AWS Network Service Offerings
#### VPC Endpoints and AWS PrivateLink
- VPC endpoint lets you privately connect your VPC to supported AWS services and VPC endpoint services
- VPC endpoints, resources inside a VPC do not require public IP addresses to communicate with resources outside the VPC
- VPC endpoints are a security product first and a connectivity product second

- VPC Endpoint types
  - Gateway Endpoints
    - targets specific IP routes in the route table
    - S3 and DynamoDB
  - Interface Endpoints
    - powered by AWS PrivateLink
    - elastic network interface with a private IP address
    - entry point for traffic destined to a supported service
  - Gateway Load Balancer Endpoints
    - elastic network interface with a private IP address
    - entry point to intercept and route traffic to a service configured with GLB
    - AWS PrivateLink powered

- AWS PrivateLink
  - service that enables you to privately connect your VPC to supported AWS services and VPC endpoint services
  - ensure traffic stays within the AWS network and does not traverse the public internet
    - Benefits
      - security. secure way to connect services privately
        - no public ip addresses or traversing the internet
      - simplification. no need to manage NAT gateways, VPN connections, or VPC peering
      - capabilities. Use with DirectConnect for on-premises connectivity

- DNS
  - Interface endpoints use DNS to resolve the endpoint's private DNS name to the private IP address of the endpoint
  - three methods to resolve the private DNS name
    - endpoint-specific DNS names for the region
      - unique endpoint identifier, service name, region and `vpce.amazonaws.com` in the name
    - zonal specific DNS names
      - unique endpoint identifier, service name, region, availability zone and `vpce.amazonaws.com` in the name
    - private DNS hostname

#### VPC Peering
- networking connection between two VPCs that lets you route traffic between them privately
- traffic stays within the AWS network

- invalid configurations
  - overlapping CIDR blocks
  - transitive peering (VPC A peering with VPC B and VPC B peering with VPC C, VPC A cannot communicate with VPC C)
  - edge to edge routing through a gateway or VPN connection

#### AWS Direct Connect
- private, reliable connection to AWS from on-premises data centers
- Choices when setting up
  - bandwidth
  - connection type
    - 1 gbps
    - 10 gbps
    - 100 gbps
  - protocol config
    - border gateway protocol (BGP)
    - bidirectional forwarding detection (BFD)
  - network config
    - Your network must use single-mode fiber with one of the following:
      - 1000BASE-LX (1,310 nm) transceiver for 1-gigabit Ethernet
      - 10GBASE-LR (1,310 nm) transceiver for 10-gigabit Ethernet
      - 100GBASE-LR4 for 100-gigabit Ethernet
    - Auto-negotiation for the port must be deactivated. Port speed and full-duplex mode must be configured manually. 
    - 802.1Q VLAN encapsulation must be supported across the entire connection, including intermediate devices. 
    - Your device must support Border Gateway Protocol (BGP) and BGP MD5 authentication. 
    - (Optional) You can configure Bidirectional Forwarding Detection (BFD) on your network. Asynchronous BFD is automatically activated for Direct Connect virtual interfaces, but does not take effect until you configure it on your router or customer gateway device. 

- Three types of Virtual interfaces 
  - private virtual interface
    - connect to a VPC using a private IP address
  - public virtual interface
    - connect to a public AWS service in the same region
  - transit virtual interface
    - connect to any VPC or regional resource through AWS Transit Gateway in same region

- Pricing
  - port hours
  - outbound data transfer

#### AWS Site-to-Site VPN & Client VPN
- Site-to-Site
  - secure connection between your on-premises network and your VPC
  - uses a VPN tunnel to transfer data
  - monitor the connection with CloudWatch
  - pricing
    - per hour
    - outbound data transfer
  - Accelerated Site-to-Site VPN pricing
    - per hour
    - outbound data transfer
    - hourly fee for AWS Global Accelerator per VPN connection
    - data transfer out premium fees
- Client VPN
  - secure connection between your remote users and your VPC (cloud or on-premises)
  - uses OpenVPN-based client
  - CloudWatch monitoring
  - pricing
    - Number of connections per hour
    - number of subnets per hour associated to VPN

- Both have extensive limitations and constraints

#### AWS Transit Gateway
- interconnectivity between VPCs and your on-premises network
- Hub-and-spoke network architecture
  - provides a method for consolidating and managing routing between VPCs
- Uses other transit gateways for inter-region connectivity
- Concepts
  - attachments
    - one or more VPCs, VPN connections, or Direct Connect gateways, SD-WAN, or transit gateways
  - Transit Gateway MTU
    - 8,500 bytes for VPC, DirectConnect, transit gateway, and peering connections
    - 1,500 bytes for VPN connections
  - Transit Gateway Route Table
    - route table that contains routes to the attachments
  - Association
    - attachment to a route table
  - Route propagation
    - dynamically propagate routes to a transit gateway route table
      - VPC, VPN or DirectConnect can propagate routes

- Example
  - use one transit gateway to connect multiple VPCs within a region and another transit gateway to connect VPCs in another region

### Exploring Design Patterns
#### Simplifying Multi-VPC Routing
- Interesting scenario
  - Takeaways
    - use Transit Gateway to simplify routing and reduce number of connections
    - simplify route tables with Transit Gateway

#### Resilient Hybrid Networks
- Scenario where you have on-premises and cloud resources
  - Takeaways
    - avoid single points of failure by replicating connections
    - Don't use a single Direct Connect partner router for critical connections

#### Regional High Availability
- Interesting scenario using multiple VPCs in multiple regions
  - Takeaways
    - Route 53 latency-based routing can be used to direct traffic to the closest region or weighted routing to distribute traffic across regions
    - ELB can be used to distribute traffic within a region's VPC resources
    - Primary and Secondary DBs can be used to provide failover
    - VPC peering can be used to connect DBs in different regions for replication and synchronization

#### AWS Transit Gateway Peering
- Transit gateways are a regional service and support a hub-and-spoke network design within the Region in which they are deployed
- highly available multi-regional AWS environment using transit gateways, a mesh network design is required
