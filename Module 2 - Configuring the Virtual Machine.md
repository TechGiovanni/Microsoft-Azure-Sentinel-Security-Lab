Module 2 - Configuring the Virtual Machine
Objectives
This module guides you through the process of updating the firewall, using remote Desktop Protocal (RDP) to gain access to the virtual machines desktop and using powershell script to extract Eventlogs from the virtual machine.

Prerequisites You must have a Microsoft Azure subscription and have completed Module 1 as this project builds from the previous module.

Exercise 1: Virtual Machine setup

1. From your actual windows computer, type <strong>Remote Desktop</strong> and click <strong>Remote Desktop Connection</strong>. 

<p align="center">
  <img src="https://i.imgur.com/rBfuiDZ.png"/>
</p>

2. The Remote Desktop Connection GUI should open.
3. Next we get the IP address of our Virtual Machine.
<p align="center">
  <img src="https://i.imgur.com/BRInebb.png"/>
</p>

4. On <a href="https://portal.azure.com/">AzurePortal</a>, type <strong>Virtual machines</strong> and click <strong>Virtual machines</strong> under Services.

<p align="center">
  <img src="https://i.imgur.com/5NKk5JR.png"/>
</p>

5. Click the virtual machine that we created.

<p align="center">
  <img src="https://i.imgur.com/Did7vIb.png"/>
</p>

6. Then copy the IP Address.

<p align="center">
  <img src="https://i.imgur.com/GDcDvnl.png"/>
</p>

7. Paste the IP Address into the Remote Desktop Connection and then click <strong>Connect</strong>.

<p align="center">
  <img src="https://i.imgur.com/4PAVoVT.png"/>
</p>

8. Enter the fields for username and Password. Click <strong>OK</strong>.
9. Accept the certificate Warning by clicking <strong>Yes</strong>.

<p align="center">
  <img src="https://i.imgur.com/zi6PXrL.png"/>
</p>

10. Once the Windows machine loads, Click <strong>No</strong> for all the Services options.

<p align="center">
  <img src="https://i.imgur.com/wUZosm0.png"/>
</p>


11. Click <strong>Yes</strong> for allowing your PC to be discoverable by other PCs

<p align="center">
  <img src="https://i.imgur.com/sK3c3Qy.png"/>
</p>

12. Go through the Microsoft Edge setup as we will needing access to the internet.
13. Type in the search box <strong>wf.msc</strong> to go to <strong>Windows Defender Firewall with Advanced Security</strong>

<p align="center">
  <img src="blob:https://imgur.com/3ac2284a-52cb-44c4-8ce5-2fe9fcc76f3d"/>
</p>

14. Click <strong>Windows Defender Firewall Properties</strong>

<p align="center">
  <img src="https://i.imgur.com/4TGmpZy.png"/>
</p>

15. <strong>Firewall States:</strong> Off, for Public, Private and Domain.
16. <strong>Apply</strong> the changes then click <strong>OK</strong>.

<p align="center">
  <img src="https://i.imgur.com/O44N88u.png"/>
  <img src="https://i.imgur.com/JSacsny.png"/>
  <img src="https://i.imgur.com/uSM9amD.png"/>
</p>


## Exercise 2. Extract Security Logs

### Objective

In this section we will use Powershell to extract the security logs that we can then use to view in our Microsoft Sentinel (SIEM).

17. Go to <strong>Windows Powershell ISE</strong> on the virtual Machine.

<p align="center">
  <img src="https://i.imgur.com/istljmg.png"/>
</p>

18. Go to the <a href="https://github.com/TechGiovanni/Microsoft-Azure-Sentinel-Security-Lab/blob/main/Custom_Security_Log_Exporter.ps1">Powershell Script</a> page and copy the contents to <strong>Windows Powershell ISE</strong> on the virtual Machine. 

<p align="center">
  <img src="https://i.imgur.com/rOHkrDu.png"/>
</p>

19. Save the file to the <strong>Desktop</strong> with the name <strong></strong>

<p align="center">
  <img src=""/>
</p>


<p align="center">
  <p>Ref 1: </p>
  <img src=""/>
  <p></p>
</p>

<p align="center">
  <p>Ref 1: </p>
  <img src=""/>
  <p></p>
</p>

<p align="center">
  <p>Ref : </p>
  <img src=""/>
  <p></p>
</p>

<p align="center">
  <p>Ref : </p>
  <img src=""/>
  <p></p>
</p>

<p align="center">
  <img src=""/>
</p>


<p align="center">
  <p>Ref 1: </p>
  <img src=""/>
  <p></p>
</p>

<p align="center">
  <p>Ref 1: </p>
  <img src=""/>
  <p></p>
</p>

<p align="center">
  <p>Ref : </p>
  <img src=""/>
  <p></p>
</p>

<p align="center">
  <p>Ref : </p>
  <img src=""/>
  <p></p>
</p>




