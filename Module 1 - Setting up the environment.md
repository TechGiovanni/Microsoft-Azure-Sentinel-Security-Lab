# Module 1 - Setting up the environment

## Objectives
This module guides you through the initial setup of the environment that will be used in all subsequent modules.

Prerequisites
You must have a Microsoft Azure subscription. If you do not have a subscription, you can sign up for a free account here.

An Azure subscription
Permissions to create a resource group in your Azure subscription
Note: Installing Sentinel for the very first time in a Subscription needs Subscription Contributor or Owner permission


## Exercise 1: The Create our resource group and workspaces

1. Navigate to the Azure Portal and log in with your account.

2. In the menu section on the left, click on Resource groups and click on Create.
   
<p align="center">
  <img src="https://i.imgur.com/VakkBxx.png"/>
</p>

3. In the Resource group text field type a name that will be used to hold all your resources.
4. Click Region and Select a (US) West US 2

<p align="center">
  <img src="https://i.imgur.com/TbIEgS6.png"/>
</p>

5. Click <strong>Review + create</strong> and then <strong>Create</strong> after the validation completes. The creation takes a few seconds.
6. Now you will have your resource group created. Click the resource group <strong>Honeypotlab</strong>.

<p align="center">
  <img src="https://i.imgur.com/Z108lSy.png"/>
</p>

7. We will be creating a Virtual machine resource. Click <strong>Create Resource</strong>

<p align="center">
  <img src="https://i.imgur.com/Y0wfA6g.png"/>
</p>

8. Type <strong>Virtual Machine</strong> in the Search box. Click the <strong>Create</strong> dropdown menu, then click <strong>Virtual Machine</strong>

<p align="center">
  <img src="https://i.imgur.com/9hiJWmN.png"/>
</p>

9. In the Create a virtual machine page, fill out the form as follows:

<ul>
<li><strong>Subscription:</strong> choose the Azure subscription where you would like to deploy the Microsoft Sentinel workspace</li>
<li><strong>Resource Group:</strong> select the existing resource group or create a new resource group (recommended) that will host the lab resources</li>
<li><strong>Virtual machine name:</strong> choose a name for your virtual machine, I will call it <strong>Honeypot-vm</strong> </li>
<li><strong>Region:</strong> from the drop down, select the Azure region where the lab will be located. recommend the same as the resource group</li>
<li><strong>Image:</strong> <strong>Windows 10 Pro, version 22H2 - x64 Gen2</strong></li>
<li><strong>Size:</strong> <strong>Standard_D2s_v3 - 2 vcpus, 8 GiB memory ($70.08/month)</strong></li>
</ul>

<p align="center">
  <img src="https://i.imgur.com/RUdr8bm.png"/>
</p>

10.Scroll down to fill out the other sections in the Administrative account fields.

<ul>
<li><strong>Username:</strong> <strong><yourname>admin</strong></li>
<li><strong>Password:</strong> select the password you will be using to log into the virtual machine</li>
</ul>

11. Click the <strong>I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights.</strong> in the Licensing section.

<p align="center">
  <img src="https://i.imgur.com/8bUkXDU.png"/>
</p>

12. Click <strong>Networking</strong> tab.
13. <strong>NIC network security group:</strong> Select <strong>Advanced</strong>.
14. <strong>Configure network security group:</strong> Click <strong>Create new</strong>.

<p align="center">
  <img src="https://i.imgur.com/CkDUmqn.png"/>
</p>

15. Delete the Inbound rule that was automatically created.

<p align="center">
  <img src="https://i.imgur.com/JRykqDc.png"/>
</p>

16. Click <strong>+ Add an inbound rule</strong>, to create a new rule.

<p align="center">
  <img src="https://i.imgur.com/v43O9Op.png"/>
</p>

17. We will make our Virtual machine super vulnerable. So we will allow:
<ul>
<li><strong>Source:</strong> Any</li>
<li><strong>Source port ranges:</strong> *</li>
<li><strong>Destination:</strong> Any</li>
<li><strong>Service:</strong> Custom</li>
<li><strong>Destination port ranges:</strong> *</li>
<li><strong>Protocol:</strong> *</li>
<li><strong>Action:</strong> Allow</li>
<li><strong>Priority:</strong> 100</li>
<li><strong>Name:</strong> AllowAnyInbound</li>
</ul>

<p align="center">
  <img src="https://i.imgur.com/WhfLdxl.png"/>
</p>

18. Click <strong>Add</strong> at the bottom of the window, then click <strong>OK</strong> at the bottom left of the Create network security group window.
19. Click <strong>Review + create</strong> and then <strong>Create</strong> after the validation completes. The creation takes a few seconds.


## Exercise 2: Create Log Analytics Workspace

### Objective

The purpose of Log analytics is to inject logs form the virtual machine. We will also create a custom log that includes where the attackers are coming from.

20. Click <strong>Resource groups</strong> then click your resource group <strong>"Honeypotlab"</strong> then click <strong>+ Create</strong>.

<p align="center">
  <img src="https://i.imgur.com/gencX1b.png"/>
</p>

21. Type log analytics, then click <strong>Create</strong> then Select <strong>Log Analytics Workspace</strong>

<p align="center">
  <img src="https://i.imgur.com/TYb0TfB.png"/>
</p>

22. In the Create Log Analytics workspace fill out this:

<ul>
<li><strong>Name:</strong> log-analytics-workspace-honeypot</li>
</ul>

23. Click <strong>Review + create</strong> and then <strong>Create</strong> after the validation completes. The creation takes a few seconds.

<p align="center">
  <img src="https://i.imgur.com/iIeIxkO.png"/>
</p>


## Exercise 3: Setup Microsoft Defender for Cloud

### Objective

We will enable the ability to gather logs from the Log Analytics Workspace.

24. Type <strong>Microsoft Defender for Cloud</strong> and then click <strong>Microsoft Defender for Cloud</strong> under Services.

<p align="center">
  <img src="https://i.imgur.com/zX6WCb5.png"/>
</p>

25. Click <strong>Management</strong> on the left widget window.
26. Then click <strong>Environment settings</strong>.

<p align="center">
  <img src="https://i.imgur.com/b6SeSk3.png"/>
</p>

27. Click the dropdown arrows until you see your log analytics workspace. click your <strong>log analytics workspace-honeypot</strong> option.

<p align="center">
  <img src="https://i.imgur.com/z8zHzMn.png"/>
</p>

28. Enable thse Defender Plans:

<ul>
<li><strong>Foundational CSPM:</strong> On</li>
<li><strong>Servers:</strong> On</li>
<li><strong>SQL servers on machines:</strong> Off</li>    
</ul>
   
<p align="center">
  <img src="https://i.imgur.com/YxhHeyG.png"/>
</p>



<p align="center">
  <img src=""/>
</p>

<p align="center">
  <img src=""/>
</p>

<p align="center">
  <img src=""/>
</p>


## Exercise 4: Setup Microsoft Sentinel

### Objective

We will enable the ability to gather logs from the Log Analytics Workspace.

24. Type <strong>Microsoft Sentinel</strong> and then click <strong>Microsoft Sentinel</strong> under Services.

<p align="center">
  <img src="https://i.imgur.com/osGttJZ.png"/>
</p>


25. 


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
  <p>Ref : </p>
  <img src=""/>
  <p></p>
</p><p align="center">
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
  <p>Ref : </p>
  <img src=""/>
  <p></p>
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
  <p>Ref : </p>
  <img src=""/>
  <p></p>
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
  <p>Ref : </p>
  <img src=""/>
  <p></p>
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
  <p>Ref : </p>
  <img src=""/>
  <p></p>
</p>
</p>
