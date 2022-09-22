# IPsec Tunnel

You can connect to SHIP-HATS using one of the following methods based on your setup:

- [AWS VPC Endpoint](aws-vpc-endpoint)
- [IPsec Tunnel](#prerequisites)


## Prerequisites

Gather the following details:

- Tenant's Azure private CIDR range
- VNet Gateway's public IP (created on step 1b)

![](./images/aws-azure-setup.png)


## Setup S2S VPN

1. Request for a blank VNet
    - VNet must not have a VNet gateway attached in our setup because the default setup by extremax has one attached and not visible to us. 
    - A required /28 subnet is required for the gateway subnet, ensure there is sufficient addresses for other usage
1. (Azure)Create VNet Gateway w/ attached pub IP
    - Request extremax to create a public ip and attach it to a new VNet Gateway with below requirements:

## (AWS)Create CGW, VPN connection
1. Log in to the target AWS Account.
1. Create a CGW based on VNet Gateway attached IP (step b)
1. Create a VPN Connection with below requirements: 
    - Use CGW (step c 2), change routing options to static, and indicate local cidr of azure VNet
    - Choose transit gateway as target type
1. Once vpn is created download configuration:

## Create Local gateway

1. Request a local gateway from extremax using downloaded configuration.
    1. take note of the VPG ip, use the ip on requesting local gateway (request 1 local gateway using the virtual private gateway ip in the textfile. In this case it will be 52.74.6.122)
    1. For address space, input aws vpc CIDR.

For reference:
- SHIP GCC2 UAT: 100.0.4.0/22
- SHIP GCC2 PROD: 100.10.4.0/22

1. Repeat the same steps for the other tunnel.

## Create Connection

1. Once local gateway is created, use both VNet gateway and local gateway to create the connection
1. Use IKEv2 as the IKE version, IPsec VPN
1. Per each connection use the same pre-shared key for each tunnel. (Preshared key should be included with the downloaded config file )
1. Identify the tgw attachment for the vpn created.
1. Copy the vpn id. 
1. Find the tgw attachment using the copied vpn id, add a name tag to easily identify the tgw attachment. 

## Update TGW route table 

TGW route tables - add a route to tgw attachment based on azure VNet's local IP
CIDR: provided tenant's private IP CIDR
Attachment choose the attachment identified. 

## Setup R53 Inbound Resolver

1. Create Security Group - should contain inbound rule on port 53 based on azure VNet's local IP
1. Create Inbound resolver on endpoint vpc

## Setup of custom dns server on tenant's runner

1. Once resolver is created, add the ip provided to azure VM's custom dns server (can be reached by clicking VM's network interface > dns servers)
    > **Note:** currently private resolvers for Azure dns is not supported in singapore region(correct as of Aug 1, 2022), to get around this, please use one runner with above config to get resources from ship and pass artifacts to another that can resolve tenant's azure resources.
1. Add Inbound rules to VPC endpoint sg for tenant's private CIDRs. 


