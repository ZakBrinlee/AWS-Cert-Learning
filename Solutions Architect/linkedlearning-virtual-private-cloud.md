# [AWS Certified Solutions Architect - Associate (SAA-C03) Cert Prep: 3 Virtual Private Cloud](https://www.linkedin.com/learning/aws-certified-solutions-architect-associate-saa-c03-cert-prep-3-virtual-private-cloud)

Started: April 10, 2024
Completed: April 10, 2024

## Links
- [Compare NAT gateways and NAT instances](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-nat-comparison.html)

### What I need to know:
- Understand the basics of 
  - VPCs
  - VPC peering
  - VPC security
  - NAT & NACL

## Notes
### Amazon VPC Applications
#### Overview
- applications runs in the VPC or on-prem
- subnets
- Direct Connect can provide VPN connections

- Default VPC is created when you create an AWS account
  - one in each region
  - Amazon recommends not deleting the default
  - dynamic private/public IP
  - DNS names, provisioned, public and private options

#### Creating a VPC lab
- VPCs are region specific
- VPCs are isolated from each other
  - can be connected but needs to be facilitated

#### Elastic IP Addresses
- IP addresses within the VPC
- permanently allocated to your account
  - charged until released
- Network interfaces can be assigned an Elastic IP

#### Elastic Network interfaces
- Virtual network interface that is attached to an instance
- allows dual-homing
  - multiple network interfaces
- associated with a subnet within a VPC

- Virtual network card in the cloud
  - install it into a VPC
  - ability to give IP to whatever network you want

#### Endpoints
- AWS endpoints connect to VPCs to AWS services
- Can enforce policies on different endpoints

- Creating endpoint
  - Specify the VPC
  - Specify the service
    - com.amazonaws.<region>.<service>
  - Specify policy
  - Specify route table

### VPC Peering
#### Overview
- VPC peering allows you to connect two VPCs
  - think of it like building a WAN/LAN connection
- Initiating VPC sends a request to the receiving VPC
  - Owner role required
  - IP CIDR blocks in each must not overlap
- EAch VPC needs a defined route to the other VPC
  - may require route table mods
- Security groups and NACLs apply to peering connections

### Amazon VPC Security
#### Security Groups overview
- Acts like a firewall
  - assigned to an instance
  - applied to instances not subnets
- Defines allowed traffic flows
  - ingress (inbound) and egress (outbound)
- Supports only allow rules
  - deny is implicit
- Stateful
  - return traffic is allowed

- NACL
  - applied on subnets
  - stateless
  - allow and deny rules
  - rule number defines order of operations
    - lowed number is first
    - first match applies

#### Network Address Translation
- translate single address to another
- Keeps track of connections and rules
- Supports public and private implementations

- NAT instances
  - EC2 instance that acts as a NAT
  - allows linux or windows based services
  - implements EC2 in a public subnet

#### Gateways (VPGs and CGWs)
- Virtual Private Gateway (aws side)
  - connects local (on-prem) to the VPC
  - VPN concentrator is the gateway to the VPX

- Customer Gateway (customer side)
  - physical device or software that connects to the VPC
  - Anchor on the customer side
    - connects to VPG

- Alternatives
  - AWS Hardware VPN
  - AWS Direct Connect
  - VPN CloudHub
  - Software VPN that supports the protocols

#### VPN configuration options
- Ability to use certificates to authenticate with VPN connection
- VPN connection types
  - Site-to-Site
  - Client-to-Site
  - Client VPN
