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
