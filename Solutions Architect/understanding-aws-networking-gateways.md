# [Understanding AWS Networking Gateways](https://explore.skillbuilder.aws/learn/course/1377/understanding-aws-networking-gateways)

Started: May 20th, 2024
Completed: May 20th, 2024


## Notes

### Summary
- Regional resources
  - Virtual Private Gateway
    - VPN usable
    - Direct Connect usable
  - Transit Gateway
    - Route tables are attachable
    - VPN usable
    - Direct Connect usable
  - Internet Gateway
    - Route tables are attachable
  - NAT Gateway
    - Route tables are attachable
- Global resources
  - Direct Connect Gateway
- Local resources
  - Local Gateway
  - Customer Gateway
    - VPN usable

### Networking Refresher
#### Internet Gateway
- attached to a VPC
- regional resource
- NAT for instances in a public subnet

#### Internet Gateway: Ingress routing
- associate route table with internet gateway
- redirects traffic VPC through virtual appliances
- segments VPC traffic

#### Internet access for private subnets: NAT Gateway
- NAT Gateway
  - regional resource
  - NAT for instances in a private subnet
  - high availability
  - managed service
  - scales automatically

- NAT gateway lives in the subnet
  - route table points to NAT gateway
  - AZ service

#### NAT Gateway
- enables instances in private subnet to access the internet
- assigned private IPv4 address
- only lives in 1 AZ
- resides in public subnet of VPC

#### VPC Peering
- connection between 2 VPCs requiring only IP addresses


### Scope
#### If all you need is..
- Communicating to other VPCs or on premises using VPN but...
  - you want to manage connections using your own VPN provider
  - responsibility for managing VPN connections
  - Aware that VPN instances can become network bottlenecks
  - aware you may need IGW in each VPC

- Sharing services between VPCs across AWS accounts
  - AWS PrivateLink may be a better option

### Virtual Private Gateway
- AWS Site-to-Site VPN
  - One virtual private gateway per VPC
  - Border Gateway Protocol (BGP) or static routes
  - redundant IPSec tunnels
  - Redundant routers across two AZs

- AWS Direct Connect
  - Restricted to one region
  - one BGP peering per VPC

- Ingress routing
  - associate route table with virtual private gateway
  - redirects traffic VPC through virtual appliances
  - segments VPC traffic

- Summary
  - regional resource
  - must attach to VPC for user
  - VPN or Direct Connect

### Customer Gateway
- Site-to-Site VPN
  - redundant IPSec tunnels
    - each tunnel contains IKE (Internet Key Exchange) and IPSec association

- Summary
  - Physical or software on the customer side of VPN connection
  - can be reused for multiple VPN connections

### Direct Connect Gateway
- global resource
- ability to connect 10 VPW globally and across accounts
- does not permit VPC-to-VPC connections
- can be associate with VPGW or transit gateway

### Transit Gateway
- Hub and spoke structure
- Cross region and cross account over 1 VIF and BGP peering

- Key concepts
  - Attachments
    - VPC, VPN, Direct Connect, transit gateway peering
  - Associations
    - route tables
  - Propagation
    - route tables
      - attachment routes are installed

- Attachments
  - AWS Transit Gateway connect
    - removes S2S VPN between hub and AWS Transit Gateway
    - Dynamic routing between SD-WAN and transit gateway
    - easy integration with on-premises SD-WAN appliances with TGW
    - improve scalability and throughput

- Path selection behavior
  - Most specific route
  - Static route entries, including static site-to-site VPN routes
  - BGP propagated routes from Direct Connect
  - BGP propagated routes from AWS Site-to-site VPN connections

- Summary
  - regional resource residing outside VPC
  - connects VPCs and on-premises networks through central hub
  - simplifies networking by acting as regional router
  - encrypts data by default

### Local Gateways
- Outpost rack
  - 42U rack
  - fully assembled
  - installed by AWS
  - centralized redundant power and cooling

- One local gateway per outpost
- Performs NAT for instances that are assigned address from customer-owned IP pool

- outposts can communicate with other outposts on the same VPC regardless of subnets

- Components
  - Route Tables
    - part of the install process
  - Virtual interfaces
    - One VIF is created for each Link Aggregation Group (LAG) connection

