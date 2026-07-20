<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>Project Summary</h1>
This project demonstrates the deployment and configuration of a Microsoft Azure virtual network consisting of multiple Windows virtual machines. The lab covers virtual networking, remote administration through Remote Desktop Protocol (RDP), Network Security Group (NSG) configuration, connectivity testing, troubleshooting, and Azure resource cleanup.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Windows 11 Pro Virtual Machines
- Azure Virtual Network
- Azure Network Security Groups
- Virtual Machines
- Remote Desktop Protocol (RDP)
- ICMP (Ping)
- DNS
- TCP/IP Networking

<h2>Operating Systems Used </h2>

- Windows 11 Pro</b> (21H2)

<h2>Ticket Lifecycle Stages</h2>

- Intake
- Assignment and Communication
- Working the Issue
- Resolution

<h2>Lifecycle Stages</h2>

<p>
Figure 1 – Successfully created the Azure Resource Group that will contain all networking resources for this lab.
<img width="1904" height="912" alt="Azure Networking Lab Screenshot 1" src="https://github.com/user-attachments/assets/217ca34d-09ae-4495-9342-1e84b9889584" />
</p>
<p>
A dedicated Azure Resource Group named RG-AzureNetworkingLab was created in the East US 2 region. This Resource Group serves as the central container for all Azure resources used throughout the lab, making deployment, organization, and cleanup more efficient.
</p>
<br />

<p>
Figure 2 – Azure Virtual Network and subnet successfully created to provide private network connectivity between virtual machines.
<img width="1916" height="913" alt="Azure Networking Lab Screenshot 2" src="https://github.com/user-attachments/assets/24cbe581-ae6a-48b8-9101-88400911df72" />
</p>
<p>
A virtual network named VNET-AzureLab was deployed within the RG-AzureNetworkingLab resource group in the East US 2 region. The network was configured with a 10.0.0.0/16 address space and includes a dedicated subnet named Subnet-Production using the 10.0.1.0/24 address range. This virtual network provides private connectivity for the virtual machines deployed later in the lab.
</p>
<br />

<p>
Figure 3 – Successfully deployed the first Windows 11 virtual machine (VM-Client-01) within the Azure virtual network.
<img width="1900" height="911" alt="Azure Networking Lab Screenshot 3" src="https://github.com/user-attachments/assets/3e9a6b5a-a6f0-4177-a84a-5d9ee1fd0895" />
</p>
<p>
The first virtual machine, VM-Client-01, was deployed within the VNET-AzureLab virtual network using the Windows 11 Pro operating system. A public IP address was automatically assigned to support Remote Desktop (RDP) connectivity, while the virtual machine also received a private IP address for internal communication within the virtual network.

During deployment, the virtual machine was associated with the Subnet-Production subnet and configured to allow inbound RDP (TCP port 3389) traffic through its Network Security Group.
</p>
<br />
