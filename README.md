## Welcome to Microsoft Sentinel Analyst Lab
<img src="https://i.imgur.com/eQ5ykGc.png"/>

### Introduction

Today we are going to be setting up Azure Sentinel (SIEM) as well as a Virtual Machine which will be our (Honeypot). The Virtual Machine will be super vulnerable to the internet and we will essentially monitor and Log the RDP Attacks from the different countries. 

The lab deploys a Microsoft Sentinel workspace and ingests event logs from the Vitual machine (honeypot) to showcase various types of attacks that are hitting this VM and also to showcase Microsoft Sentinel features. 
You should expect very little or no cost at all due to the size of the data (~10 MB), and the fact that Microsoft Sentinel offers a 30-day free trial on new workspaces.

### Prerequisites
- Microsoft Azure subscription
- Network analysis tools (Wireshark, Advanced IP Scanner) for capturing and examining network traffic.
- Network Documentation (Packet Tracer, GitHub)

### Modules
- <a href="https://github.com/TechGiovanni/Microsoft-Azure-Sentinel-Security-Lab/blob/main/Module%201%20-%20Setting%20up%20the%20environment.md" target=”_blank”>Module 1 - Setting up the environment</a>
- <a href="https://github.com/TechGiovanni/Microsoft-Azure-Sentinel-Security-Lab/blob/main/Module%202%20-%20Configuring%20the%20Virtual%20Machine.md" target=”_blank”>Module 2 - Configuring the Virtual Machine</a>
- <a href="https://github.com/TechGiovanni/Microsoft-Azure-Sentinel-Security-Lab/blob/main/Module%201%20-%20Setting%20up%20the%20environment" target=”_blank”>Module 3 - Setup Azure Monitor and Log Analytics custom log table</a>
- <a href="https://github.com/TechGiovanni/Microsoft-Azure-Sentinel-Security-Lab/blob/main/Module%201%20-%20Setting%20up%20the%20environment" target=”_blank”>Module 4 - Transforming the Logs</a>
- <a href="https://github.com/TechGiovanni/Microsoft-Azure-Sentinel-Security-Lab/blob/main/Module%201%20-%20Setting%20up%20the%20environment" target=”_blank”>Module 5 - Setting up Sentinel workspace and the Map</a>

### Diagram of the big picture
<img src="https://i.imgur.com/YePDPAK.png"/>




