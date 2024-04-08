# [AWS Networking Basics](https://explore.skillbuilder.aws/learn/course/12439/play/81847/aws-networking-basics)

Started: April 1, 2024
Completed: April 1, 2024

## Notes
- A network is defined as a set of devices that share resources that use common communication protocols(opens in a new tab) over interconnections to communicate with each other.
- These internet network connections are designed from telecommunication network technologies(opens in a new tab). 

- TCP/IP protocols lay out standards on which the internet was created
- OSI model provides guidelines on communication. 

- One big difference between security groups and network ACLs is that security groups recognize AWS resources.
- 
### Networking Concepts
- 3 main types of network protocols
  - **management protocols**
    - SNMP – Simple Network Management Protocol (SNMP)(opens in a new tab) is used to monitor and manage network devices. This TCP-based protocol adds visibility and the ability to modify endpoints which alter behavior of devices across the network. SNMP relies on the use of agents to collect and send data to an overarching SNMP manager, which in turn queries agents and gets their responses.
    - ICMP – Internet Control Message Protocol (ICMP)(opens in a new tab) is primarily used for diagnostic purposes. Managed devices on the network can use this protocol to send error messages, providing information regarding network connectivity issues between devices.
  - **communication protocols**
    - HTTP – Hypertext transfer protocol (HTTP)(opens in a new tab) is an application layer protocol that allows the browser and server to communicate.
    - TCP – Transmission Control Protocol (TCP)(opens in a new tab) separates data into packets that can be shared over a network. These packets can then be sent by devices like switches and routers to the designated targets.
    - UDP – User Datagram Protocol (UDP)(opens in a new tab) works in a similar way to TCP, sending packets of data over the network. The key difference between the two is that TCP ensures that a connection is made between the application and server, but UDP does not.
    - IRC – Internet Relay Chat (IRC)(opens in a new tab) is a text-based communication protocol. Software clients are used to communicate with servers and send messages to other clients. This protocol works well on networks with a large number of distributed machines.
  - **security protocols**
    - SSL – A Secure Sockets Layer (SSL)(opens in a new tab) is a network security protocol primarily used for ensuring secure internet connections and protecting sensitive data. This protocol can allow for server/client communication as well as server/server communication. Data transferred with SSL is encrypted to prevent it from being readable.
    - SFTP – Secure File Transfer Protocol (SFTP)(opens in a new tab), as its name might suggest, is used to securely transfer files across a network. Data is encrypted and the client and server are authenticated.
    - HTTPS – Secure Hypertext Transfer Protocol(opens in a new tab) is the secure version of HTTP. Data sent between the browser and server are encrypted to ensure protection.


- Classless Inter-Domain Routing (CIDR)
  - Private IP address cannot communicate with internet witout using NAT
    - Network Address Translation


- Open Systems Interconnect (OSI) model
  - 7 layers
    - Physical
    - Data Link
    - Network
    - Transport
    - Session
    - Presentation
    - Application

### VPC Basics


