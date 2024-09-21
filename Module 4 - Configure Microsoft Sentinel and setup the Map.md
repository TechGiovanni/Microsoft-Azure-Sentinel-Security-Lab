# Module 4 - Configure Microsoft Sentinel and setup the Map

### Objectives

This module guides you through the process of the basic working of Microsoft Sentinel. We will be Ingesting the logs provided by Log Analytics workspace and then Extracting the location data, Extending the table so that the extracted raw data can be separated into its own columns then we will be visualising where the attacks are coming from on a Map.  

Prerequisites You must have a Microsoft Azure subscription and have completed Module 1, 2, and 3, as this project builds from the previous module.

## Exercise 1: Create Extracting the Raw Data into their own separate columns

1. Go to Microsoft Sentinel by typing it in the search box at the top.

<p align="center">
  <img src="https://i.imgur.com/FQJh7P8.png"/>
</p>

2. Click your <strong>Log Analytics Workspace</strong> resource.
3. Click <strong>Workbooks</strong> under Threat Management.

As you can see on the far right we have over 2000+ Failed RDP logons on our Virtual Machine (Honeypot).

<p align="center">
  <img src="https://i.imgur.com/9kaJ8Js.png"/>
</p>

5. Click <strong>+ Add Workbook</strong>.

<p align="center">
  <img src="https://i.imgur.com/YApNA2R.png"/>
</p>

6. Click <strong>Edit</strong>.

<p align="center">
  <img src="https://i.imgur.com/64st6L8.png"/>
</p>

7. Remove the Default widgets that automatically comes with the workbook by clicking the <strong>three dot</strong> dropdown button at the far right.
8. Click <strong>Remove</strong>.
9. When the <strong>Remove text?</strong> pops up, Click <strong>Yes</strong>. 
10. Do the same for the second widget.

<p align="center">
  <img src="https://i.imgur.com/zqSqfcE.png"/>
</p>

10. Click the <strong>+ Add</strong> dropdown button
11. Click <strong>Add Query</strong>.

<p align="center">
  <img src="https://i.imgur.com/j716LiB.png"/>
</p>

12. Copy this code into the blank space under <strong>Log Analytics workspace Logs (Analytics) Query</strong>.

This will extend the Table that we created in Log Analytics and extend columns using functions. We will also filter out null values so that we can pin point the state of each attack more precisely.

<p>
FAILED_RDP_WITH_GEO_CL
| extend timestamp = TimeGenerated,
  latitude = toreal(extract("latitude:(.*?),", 1, RawData)),
  longitude = toreal(extract("longitude:(.*?),", 1, RawData)),
  destinationhost = extract("destinationhost:(.*?),", 1, RawData),
  username = extract("username:(.*?),", 1, RawData),
  sourcehost = extract("sourcehost:(.*?),", 1, RawData),
  state = extract("state:(.*?),", 1, RawData),
  country = extract("country:(.*?),", 1, RawData)
| where state != "null" and state != ""
| project latitude, longitude, destinationhost, username, sourcehost, state, country, timestamp
</p>

<p align="center">
  <img src="https://i.imgur.com/uqKp3mU.png"/>
</p>


## Exercise 2: Plotting the Map with Microsoft Sentinel

### Objective

We will now show specifically what we want to see on the map based on the log data table we created.


13. Click .

<p align="center">
  <img src=""/>
</p>


<p align="center">
  <img src=""/>
</p>





