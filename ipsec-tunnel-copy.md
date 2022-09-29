# IPsec Tunnel

You can connect to SHIP-HATS using one of the following methods based on your setup:

- [AWS VPC Endpoint](aws-vpc-endpoint)
- [IPsec Tunnel](#prerequisites)

## Audience

The following topic is intended for Tenants on Azure to establish connectivity to AWS GCC 2.0 via a site-to-site VPN Tunnel.

## Prerequisites

Provide the following details:

- Tenant's Azure private CIDR range
- VNet Gateway's public IP address (created on step 1b)

![Azure setup](./images/aws-azure-setup.png)


## Setup S2S VPN

1. Provision a blank VNet
    - You may have to request extremax for this.
    - VNet must not have a VNet gateway attached in our setup because the default setup by extremax has one attached and not visible to us. 
    - A required /28 subnet is required for the gateway subnet. Ensure that there are sufficient addresses for other usage.
1. Provision and configure a Virtual Network gateway: Raise a request to extremex to:
    1. Create a VNet gateway in the blank VNet
        
    ![](./images/create-vnet-gateway.png ':size=80%')</kbd>

    1. Create a public IP and attach it to a new VNet Gateway
    
    ![](./images/review-vnet-gateway.png ':size=80%')</kbd>

**SHIP-HATS team will configure a VPN at AWS GCC 2.0 and share the VPN configuration file.**

## Create Local Network Gateways

1. Take note of the Virtual Private Gateway IPs from the shared configuration file: 
    - IPSec Tunnel #1 - Outside IP Addresses - Virtual Private Gateway: 
        ![](./images/ipsec-tunnel1.png ':size=80%')
    - IPSec Tunnel #2 - Outside IP Addresses - Virtual Private Gateway:
        ![](./images/ipsectunnel2.png ':size=80%')
1. Request extremex to create two Local gateways, one for each of the above Virtual Private Gateway IPs:
    - In the **IP Address** field, enter the Virtual Private Gateway IP from above.
    - In the **Address Space** field, enter GCC 2.0 AWS PROD vpc CIDR.
        - SHIP GCC 2.0 UAT: 100.0.4.0/22
        - SHIP GCC 2.0 PROD: 100.10.4.0/22
    
![](./images/create-Local-network.png ':size=80%')

## Create Connections

Create two connections - one for each IPsec tunnel. 

1. Navigate to **AWSVNetGateway** > **Connections**, and then click **Add**.
1. In the **Name** field, select the *Local network gateway* from the dropdown list corresponding to IPsec Tunnel 1.
1. In the **Connection type**, select **Site-to-site (IPsec)**.
1. In the **Shared key (PSK)** field, fetch the value of pre-shared key corresponding to IPsec Tunnel 1 from the configuration file provided by the SHIP-HATS team.
1. For **IKE Protocol**, select **ikev2**. 

Repeat the above steps to create a second connection. Make sure that you select the Local network gateway **Name** and **Shared key (PSK)** corresponding to IPsec Tunnel 2.

![](./images/add-connection.png ':size=60%')

**SHIP-HATS team will provide DNS Resolver IPs for the tenants to configure.**


## Set up custom dns server

### To configure custom dns servers on VM that hosts the GitLab runner, complete the following steps:

1. Log in to the VM that hosts the GitLab runner.
1. Click **Network interface** 
1. Under **DNS server**, add the IP address provided by SHIP-HATS team.
1. Click **Add DNS Server**.  

    Added DNS server IPs will appear under **Applied DNS servers**.

    ![](./images/dns-server.png ':size=100%')

> **Note:** Currently private resolvers for Azure DNS is not supported in Singapore region (correct as of August 1, 2022). As a workaround, use one runner with above config to get resources from SHIP-HATS and pass artifacts to another that can resolve tenant's azure resources.


## What's Next

- [Set up GitLab Runners](gitlab-runners)

<!--
## (AWS)Create CGW, VPN connection
1. Log in to the target AWS Account.
1. Create a CGW based on VNet Gateway attached IP (step b)
1. Create a VPN Connection with below requirements: 
    - Use CGW (step c 2), change routing options to static, and indicate Local cidr of azure VNet
    - Choose transit gateway as target type
1. Once vpn is created download configuration:
-->
<!--## Create Local gateway

1. Request a Local gateway from extremax using downloaded configuration.
    1. take note of the VPG ip, use the ip on requesting Local gateway (request 1 Local gateway using the virtual private gateway ip in the textfile. In this case it will be 52.74.6.122)
    1. For address space, input aws vpc CIDR.

For reference:
- SHIP GCC2 UAT: 100.0.4.0/22
- SHIP GCC2 PROD: 100.10.4.0/22

1. Repeat the same steps for the other tunnel.
-->

<!--
## Update TGW route table 

TGW route tables - add a route to tgw attachment based on azure VNet's Local IP
CIDR: provided tenant's private IP CIDR
Attachment choose the attachment identified. 

## Setup R53 Inbound Resolver

1. Create Security Group - should contain inbound rule on port 53 based on azure VNet's Local IP
1. Create Inbound resolver on endpoint vpc

-->
