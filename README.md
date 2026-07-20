<p align="center">
<img width="800" height="748" alt="Banner" src="https://github.com/user-attachments/assets/ee9150c4-1954-46d3-9d60-a56cf889430e" />
</p>

<h1>Project Summary</h1>
This project demonstrates the deployment and configuration of a Microsoft Azure virtual network consisting of multiple Windows virtual machines. The lab covers virtual networking, remote administration through Remote Desktop Protocol (RDP), Network Security Group (NSG) configuration, connectivity testing, troubleshooting, and Azure resource cleanup.<br />

<h1>Skills Demonstrated</h1>

- Microsoft Azure
- Azure Virtual Networks
- Azure Resource Groups
- Windows Virtual Machines
- Remote Desktop Protocol (RDP)
- Network Security Groups
- Windows Defender Firewall
- ICMP Connectivity Testing
- PowerShell
- Network Troubleshooting
<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Windows 10 Virtual Machines
- Azure Virtual Network
- Azure Network Security Groups
- Virtual Machines
- Remote Desktop Protocol (RDP)
- ICMP (Ping)
- DNS
- TCP/IP Networking

<h2>Operating Systems Used </h2>

- Windows (Windows 10 Enterprise)</b> (21H2)

<h2>Deployment Process</h2>

- Environment & Architecture
- Connectivity Testing
- Troubleshooting
- Network Security Group (NSG) Testing

<h2>Lab Walkthrough</h2>

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

<p>
Figure 4 – Successfully deployed the second Windows 11 virtual machine within the same Azure virtual network to enable internal network communication and connectivity testing.
<img width="1918" height="912" alt="Azure Networking Lab Screenshot 4" src="https://github.com/user-attachments/assets/f67cab0b-74d6-4a9a-9ba4-2cdf9fd73299" />
</p>
<p>
A second Windows 11 virtual machine, VM-Client-02, was deployed into the same VNET-AzureLab virtual network and Subnet-Production subnet. Like the first virtual machine, it was configured with a public IP address for Remote Desktop (RDP) access and a private IP address for internal communication.

Deploying both virtual machines within the same virtual network provides an environment for testing connectivity, validating Network Security Group (NSG) rules, and troubleshooting common networking scenarios.
</p>
<br />

<p>
Figure 5 – Successfully connected to VM-Client-01 using Remote Desktop Protocol (RDP), confirming remote administrative access.
<img width="1914" height="950" alt="Azure Networking Lab Screenshot 5" src="https://github.com/user-attachments/assets/0da8b4df-d79b-4bdf-9940-6e46a6d89f94" />
</p>

<p>
Figure 6 – Successfully connected to VM-Client-02 using Remote Desktop Protocol (RDP), confirming connectivity to both virtual machines within the Azure environment.
<img width="1902" height="1008" alt="Azure Networking Lab Screenshot 6" src="https://github.com/user-attachments/assets/393af28c-1e8a-4a92-8801-96d1fd5b242d" />
</p>
<p>
After deployment, both virtual machines were successfully accessed using Remote Desktop Protocol (RDP). Each virtual machine was assigned a public IP address during deployment, allowing secure remote administration through TCP port 3389.

Successfully connecting to both systems confirmed that:

- The virtual machines were running correctly.
- RDP traffic was permitted by the Network Security Group (NSG).
- Remote administrative access was functioning as expected.
- The Azure networking configuration was working properly.
</p>
<br />

<p>
Figure 7 – Default inbound Network Security Group (NSG) rules permitting Remote Desktop access while enforcing Azure's default security policies.
<img width="1910" height="913" alt="Azure Networking Lab Screenshot 7" src="https://github.com/user-attachments/assets/9c02741a-3539-44d2-bd77-1e63280db857" />
</p>
<p>
The Network Security Group (NSG) associated with the virtual machines was reviewed to understand how Azure controls inbound and outbound network traffic. The default inbound rules permitted Remote Desktop (RDP) traffic over TCP port 3389, allowing secure administrative access to the Windows virtual machines. Additional default Azure rules, including the DenyAllInbound rule, demonstrated how Azure blocks unsolicited inbound traffic unless an explicit allow rule exists.

Reviewing these rules provided insight into how Azure evaluates security rules based on priority and enforces network access using a layered security model.
</p>
<br />

<p>
Figure 8 – Initial ICMP connectivity test failed while attempting to communicate between Azure virtual machines.
<img width="1914" height="1031" alt="Azure Networking Lab Screenshot 8" src="https://github.com/user-attachments/assets/376fac8f-cdef-4c1f-b801-61b8d7e677ea" />
</p>
<p>
</p>
<br />

<p>
Figure 9 – Enabled the Windows Defender Firewall rule allowing inbound ICMP Echo Requests.
<img width="1910" height="1028" alt="Azure Networking Lab Screenshot 9" src="https://github.com/user-attachments/assets/8eecb419-6112-4254-97fa-6c57bc69b238" />
</p>
<p>
</p>
<br />

<p>
Figure 10 – Successful ICMP communication between both virtual machines after enabling the appropriate Windows Firewall rule.
<img width="1899" height="967" alt="Azure Networking Lab Screenshot 10" src="https://github.com/user-attachments/assets/4f0cd3d6-6676-4726-9c85-2e9819bb7192" />
</p>
<p>
To verify internal network communication, an ICMP (ping) test was initiated from VM-Client-01 to the private IP address of VM-Client-02. The initial test failed with 100% packet loss, despite both virtual machines being deployed within the same virtual network and subnet.

After verifying the Azure networking configuration, the issue was traced to the Windows Defender Firewall on VM-Client-02, where inbound ICMP Echo Requests were blocked by default. The built-in File and Printer Sharing (Echo Request - ICMPv4-In) firewall rules were enabled, allowing ICMP traffic.

Once the firewall rules were enabled, the connectivity test was repeated successfully, confirming communication between the virtual machines over their private IP addresses.
</p>
<br />

<p>
Figure 11 – Custom Azure Network Security Group rule created to block inbound ICMP traffic for testing purposes.
<img width="1919" height="911" alt="Azure Networking Lab Screenshot 11" src="https://github.com/user-attachments/assets/a9d208a6-4b7c-4a05-a37d-2b53a06e3f4b" />
</p>
<p>
To demonstrate Azure's cloud-based firewall capabilities, a custom Network Security Group (NSG) rule was created to block inbound ICMP traffic. The rule was configured with a priority of 200, ensuring it was evaluated before Azure's default inbound rules.

This exercise illustrates how Azure NSGs can be used to control network traffic independently of the Windows Defender Firewall running inside the virtual machine.
</p>
<br />

<p>
Figure 12 – ICMP connectivity test failed after applying the Azure Network Security Group rule, confirming that the cloud firewall blocked inbound ping requests.
<img width="1901" height="963" alt="Azure Networking Lab Screenshot 12" src="https://github.com/user-attachments/assets/bbf4b421-584d-4676-b063-16cf4477a092" />
</p>
<br />

<p>
Figure 13 – ICMP connectivity successfully restored after removing the custom Azure NSG rule blocking inbound traffic.
<img width="1892" height="961" alt="Azure Networking Lab Screenshot 13" src="https://github.com/user-attachments/assets/5766af40-a361-4b8e-850f-dabf4a370a9c" />
</p>
<p>
To verify the effectiveness of the custom Network Security Group rule, another ICMP connectivity test was performed after applying the Deny-ICMP rule. As expected, communication between the virtual machines failed because Azure blocked inbound ICMP traffic.

After confirming the rule behaved as intended, the custom NSG rule was removed. A final connectivity test was performed, and communication between the virtual machines was successfully restored.

This validation demonstrated how Azure Network Security Groups can be used to temporarily restrict network traffic while allowing administrators to quickly restore connectivity when required.
</p>
<br />

<p>
Figure 14 – Both Windows 11 virtual machines connected to the same Azure Virtual Network (VNET-AzureLab), enabling private network communication and centralized network management.
<img width="1665" height="854" alt="Azure Networking Lab Screenshot 14" src="https://github.com/user-attachments/assets/55728a44-36fc-4fd0-a5e8-bff8e186a33d" />
</p>
<p>
After completing deployment and connectivity testing, the Azure virtual network was reviewed to verify that both virtual machines were connected to the same virtual network and subnet. Hosting both systems within the same network enabled private IP communication, Remote Desktop administration, and Network Security Group testing throughout the lab. This final review confirmed that the Azure infrastructure was configured correctly before the environment was cleaned up.
</p>
<br />

<p>
Lessons Learned
</p>
<p>
  
- Azure NSGs operate independently from Windows Defender Firewall.
- ICMP is blocked by default by Windows Firewall.
- Connectivity testing should isolate Azure networking before modifying VM settings.
- Azure Resource Groups simplify management.
- Validating changes before and after implementation reduces troubleshooting time.
</p>
<br />
