# Module 3 -  Setup Azure Monitor and Log Analytics custom log table

### Objectives

This module guides you through the process of creating a Data collection Endpoint using M. this creates a endpoint service in Azure that can link between any service and the Log Analytics Workspace as well as creating a Custom log so that Microsoft Sentinel can ingest it and then we can be able to plot it on a map for Analysis.

Prerequisites You must have a Microsoft Azure subscription and have completed Module 1 and 2 as this project builds from the previous module.

## Exercise 1: Create Azure Monitor Data Collection Endpoint

1. Go to <a href="https://portal.azure.com/">Azure portal</a>.
2. Click <strong>monitor</strong> on the left sidebar.
3. Click <strong>Data Collection Endpoints</strong>.
4. Then click <strong>Create data collection endpoint</strong>.

<p align="center">
  <img src="https://i.imgur.com/6nY2yaq.png"/>
</p>

5. Fill out these fields:
<ul>
<li><strong>Endpoint Name:</strong> custom-honeypot-log</li>
<li><strong>Region:</strong> West US 2</li>
</ul>

<p align="center">
  <img src="https://i.imgur.com/sFVJ2b2.png"/>
</p>

6. Click <strong>Review + create</strong> and then <strong>Create</strong> after the validation completes. The creation takes a few seconds.
7.  Refresh and the Endpoint should be created.
8.  Click the endpoint <strong>custom-honeypot-log</strong>.

<p align="center">
  <img src="https://i.imgur.com/Rigt3M9.png"/>
</p>


8. We will connect the virtual machine resourse. Currently we have no resources connected to the Azure Monitor, showing at the top right under Essentials.
9. We can click either <strong>View resources</strong> or <strong>Resources</strong> under Configuration Tab on the left.

<p align="center">
  <img src="https://i.imgur.com/cFbX5Qa.png"/>
</p>

10. Click the + Add button. 

<p align="center">
  <img src="https://i.imgur.com/aN5DFNA.png"/>
</p>

11. Choose your Vitual Machine from the dropdown.
12. Click <strong>Apply</strong> at the bottom.

<p align="center">
  <img src="https://i.imgur.com/gRouq53.png"/>
</p>

13. We now have these notifications suggesting the Vm is now connected to our Data Collection Rule.

<p align="center">
  <img src="https://i.imgur.com/I6MGlmw.png"/>
</p>
14. Show our VM Resource Created.

<p align="center">
  <img src="https://i.imgur.com/GOypShc.png"/>
</p>



## Exercise 2: Create a Custom Log using Log Analytics

### Objective

This objective of this section is to store our RDP Attacks in Log Analytics so that we can be able to retrieve it in Microsoft Sentinel for Visualization.

1. Type <strong>Log Analytics Workspace</strong> in the Search bar at the top and then select it under Services.

<p align="center">
  <img src="https://i.imgur.com/s1YwBLb.png"/>
</p>

2. Click your <strong>Log Analytics Workspace</strong>.
3. Click <strong>Tables</strong> under the Settings Dropdown menu.
4. Click the <strong>+ Create</strong> dropdown menu.
5. Click <strong>New custom log (MMA-based)</strong>. 

<p align="center">
  <img src="https://i.imgur.com/RS3ucpR.png"/>
</p>

We will need the log file from our Virtual Machine in order to select it in the Sample log field.

6.  Go to your Virtual Machine.
7.  <strong>Copy</strong> the <strong>failed_rdp.log</strong> file.

<p align="center">
  <img src="https://i.imgur.com/CoOkHxD.png"/>
</p>

8. Go to your desktop, right click and select <strong>Paste</strong>.

<p align="center">
  <img src="https://i.imgur.com/KHTK4xh.png"/>
</p>

9. The file should appear on your desktop. if not, Just create new file on your desktop with the same name failed_rdp.log and copy the contents over into this file.

<p align="center">
  <img src="https://i.imgur.com/dvmbUMO.png"/>
</p>

10. Click <strong></strong>Select a sample log under Sample log.
11. Navigate to your <strong>Desktop</strong> and select the <strong>failed_rdp.log</strong> file.
12. Click <strong>Next</strong>.

<p align="center">
  <img src="https://i.imgur.com/JuWsHOC.png"/>
</p>

13. Nothing to do on Record delimiter, so click <strong>Next</strong> again to go to the <strong>Collection paths</strong>.
14. Under Collection paths, this is the location of the log file on the Virtual Machine.
15. Go to your virtual machine and <strong>copy the address</strong>.

<p align="center">
  <img src="https://i.imgur.com/TuYhsNd.png"/>
</p>

16. Go to Azure and then choose <strong>Type: </strong>Windows
17. Paste the address in the Path field.
18. Fill in the file name at the end and include <strong>.log</strong> at the end.
19. Click <strong>Next</strong>.

<ul>
<li><strong>Type: Windows</strong> <strong>Path: C:\ProgramData\failed_rdp.log</strong></li>
</ul>

<p align="center">
  <img src="https://i.imgur.com/UllvIdj.png"/>
</p>

19. On the Details page, Fill out like this:

<ul>
<li><strong>Custom log name:</strong> FAILED_RDP_WITH_GEO</li>
</ul>

In our log search, the <strong>_CL</strong> will automatically be appended at the end, so for lof queries we would have to type <strong>FAILED_RDP_WITH_GEO_CL</strong>.

20. Click <strong>Next</strong>.
21. Click then <strong>Create</strong> after the validation completes. The creation takes a while.

<p align="center">
  <img src="https://i.imgur.com/OtuAxaz.png"/>
</p>

22. We should now see our custom log after a refresh.
    
<p align="center">
  <img src="https://i.imgur.com/R4pBELI.png"/>
</p>


23. Click <strong>Logs</strong>.
24. Click the <strong>X</strong> for the pop up windows.
25. Type FAILED_RDP_WITH_GEO_CL in the query field and select run.

26. Now we should see our logs coming in.

<p align="center">
  <img src="https://i.imgur.com/VWKZFgi.png"/>
</p>

Thats it for this module!
We will now setup Microsoft Sentinel to ingest the logs and Extend to fields to input the extracted Raw Data.

