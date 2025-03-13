# Network Forensics Analysis Report

## Overview

This report documents the analysis of a network traffic capture file (`Final.pcap`) to investigate a potential security incident involving unauthorized access and data exfiltration.

## Tools Used

* **Wireshark**: For detailed packet inspection and filtering
* **Zui (Brim)**: For alert analysis and traffic visualization
* **NetworkMiner**: For extracting files and credentials from network traffic
* **CyberChef**: For data processing and transformation

## Key Findings

### Malware Origin
* The malware was downloaded from a specific domain.
* A unique SHA-256 hash identifies the malware file.

### VBS Script
* A VBS script associated with the malware was discovered.

### Compromised Machine
* IP address of the compromised machine identified.

### Data Exfiltration
* Data was exfiltrated to a remote server.
* The network port used for data exfiltration identified.
* The connection between the victim and server lasted for a significant duration.

### Credentials
* FTP credentials were identified in the traffic.
* A compromised email password was retrieved.
 
![image](https://github.com/user-attachments/assets/343246e9-3bf4-4fd8-9a0c-480915ed1a69)

### Most Frequent Alert
* Using Zui for analysis, a specific alert was triggered most frequently.

## Analysis Methodology

### Wireshark Analysis
1. **Filtering Traffic**: Applied filters to isolate traffic between the victim and server on the identified port.
   ![image](https://github.com/user-attachments/assets/571095be-257e-47ea-8523-1108048f53a1)

2. **Identifying Connection Duration**: Located the first packet (SYN) and last packet (FIN/ACK) to calculate the connection duration.
3. **Examining FTP Data**: Inspected FTP traffic to identify commands and data transfers.

### Zui (Brim) Analysis
1. **Loading the pcap File**: Imported `Final.pcap` into Zui for analysis.
2. **Filtering for Alerts**: Used `_event_type=="alert"` to isolate alert events.

3. **Identifying Frequent Alerts**: Sorted alerts by frequency to determine the most common signature.
![image](https://github.com/user-attachments/assets/9ed17d98-5a51-4a72-956f-cb957b9fe839)


### NetworkMiner Analysis
* Extracted files and credentials from the network traffic.
* Identified relevant scripts and malware.

## Conclusion

The analysis revealed a malware infection that led to unauthorized access and data exfiltration. The attacker used specific credentials to access a server, and certain patterns in the traffic indicated suspicious activity.

This report provides a comprehensive overview of the network forensics analysis performed. For more details, please refer to the analysis notes and screenshots in the respective folders.
