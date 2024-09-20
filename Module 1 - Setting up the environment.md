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

7.We will be creating a Virtual machine resource. Click <strong>Create Resource</strong>

<p align="center">
  <img src="https://i.imgur.com/Y0wfA6g.png"/>
</p>

8. Type <strong>Virtual Machine</strong> in the Search box. Click the <strong>Create</strong> dropdown menu, then click <strong>Virtual Machine</strong>

<p align="center">
  <img src="https://i.imgur.com/9hiJWmN.png"/>
</p>

9. In the Create a virtual machine page, fill out the form as follows:

<ul>
<li>Subscription: choose the Azure subscription where you would like to deploy the Microsoft Sentinel workspace</li>
<li>Resource Group: select the existing resource group or create a new resource group (recommended) that will host the lab resources</li>
<li>Virtual machine name: choose a name for your virtual machine, I will call it <strong>Honeypot-vm</strong> </li>
<li>Region: from the drop down, select the Azure region where the lab will be located. recommend the same as the resource group</li>
<li>Image: <strong>Windows 10 Pro, version 22H2 - x64 Gen2</strong></li>
<li>Size: <strong>Standard_D2s_v3 - 2 vcpus, 8 GiB memory ($70.08/month)</strong></li>
</ul>

<p align="center">
  <img src="https://i.imgur.com/RUdr8bm.png"/>
</p>

10.Scroll down to fill out the other sections in the Administrative account fields.

<ul>
<li>Username: <strong><yourname>admin</strong></li>
<li>Password: select the password you will be using to log into the virtual machine</li>
</ul>

11. Click the <strong>I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights.</strong> in the Licensing section.

<p align="center">
  <img src="https://i.imgur.com/8bUkXDU.png"/>
</p>

12. Click <strong>Networking</strong> tab.
13. NIC network security group: Select <strong>Advanced</strong>.
14. Configure network security group: Click <strong>Create new</strong>.

<p align="center">
  <img src="https://i.imgur.com/CkDUmqn.png"/>
</p>

15. Delete the Inbound rule that was automatically created

<p align="center">
  <img src="https://i.imgur.com/JRykqDc.png"/>
</p>

16. Click <strong>+ Add an inbound rule</strong>

<p align="center">
  <img src="https://i.imgur.com/v43O9Op.png"/>
</p>

17. 

<p align="center">
  <img src="https://i.imgur.com/WhfLdxl.png"/>
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
