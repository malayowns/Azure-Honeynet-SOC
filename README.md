# Azure Honeynet and SOC with Real-World Cyber Attacks
## Objective
In this project, a honeynet was constructed using Microsoft Azure. The objective was to capture and analyze logs from all resources, and consolidate them into a Log Analytics workspace. Microsoft Sentinel was utilized as a SIEM and leveraged these logs to develop attack maps, create alerts, and generate security incidents. Azure Sentinel measured the insecure environment over a 48-hour period. The metrics analyzed were:

1. SecurityEvent (Windows Event Logs)
2. SecurityAlert (Log Analytics Alerts Triggered)
3. SecurityIncident (Incidents created by Sentinel)
4. FAILED_RDP_WITH_GEO_CL (Malicious Flows allowed into our honeynet)

## Technologies, Components, and Standards Used
1. Azure Virtual Network (VNet)
2. Azure Network Security Groups (NSG)
3. Virtual Machines (1 Windows VM)
4. Log Analytics Workspace with KQL Queries
5. Azure Key Vault for secrets management
6. Azure Storage Account for data storage
7. Microsoft Sentinel as a Security Information and Event Management system (SIEM)
8. Microsoft Defender for Cloud to protect cloud resources
9. PowerShell for automation

## Architecture
![before_securing](https://github.com/malayowns/Azure-Honeynet-SOC/assets/20374690/afe62aee-57d1-4d11-8b95-3c2f272316d4)
The project was exposed to the public for malicious actors to discover. The goal at this stage was to attract bad actors and observe their attack patterns. To achieve this, A Windows virtual machine hosting a Microsoft SQL database was deployed onto the Windows VM and exposed via the standard port. The Windows server had its network security group (NSG) had high priority inbound rules added, allowing all traffic from all ports in any protocol. This is an incredibly dangerous thing to do, but it made for some enticing targets and some great metrics. To entice attackers even more, a storage account and key vault were deployed with public endpoints which were visible on the open internet. The unsecured environment was monitored by Microsoft Sentinel using logs aggregated in the Log Analytics Workspace.

## Attack Map
![Screenshot 2024-01-09 at 10 15 48 AM](https://github.com/malayowns/Azure-Honeynet-SOC/assets/20374690/7980f1b2-618f-46f7-a20a-3f5c2a1d1bb8)

## Conclusion
In this project, a small but effective honeynet was constructed in Microsoft Azure, and log sources were aggregated into a Log Analytics workspace. Microsoft Sentinel was configured to trigger alerts and create incidents based on the ingested logs.
