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

Code:
```
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
```

<p align="center">
  <img src="https://i.imgur.com/uqKp3mU.png"/>
</p>


## Exercise 2: Plotting the Map with Microsoft Sentinel

### Objective

We will now show specifically what we want to see on the map based on the log data table we created.


13. Click the <strong>Map</strong> option in the dropdown under <strong>Visualization</strong>.
14. Under the <strong>Size</strong> option, choose the one that is appropriate to your liking.

<p align="center">
  <img src="https://i.imgur.com/3ky8ZqP.png"/>
</p>

15. Now we see we have an attacker in the ocean, This is a <strong>samplehost</strong> under <strong>destinationhost</strong>, from <strong>Russia</strong>, so we will filter this attacker out of our map.

Use this one line: 
<p>| where country != "Russia" and destinationhost != "sample"</p>

<p align="center">
  <img src="https://i.imgur.com/6FNVX33.png"/>
</p>

16. Now we will see our map updated.

<p align="center">
  <img src="https://i.imgur.com/xca7mHa.png"/>
</p>


17. To customize the Map, click <strong>Map Settings</strong>
We will create a <strong>label</strong>, and a <strong>CountryCount</strong> column and field to use in our map settings.

```
FAILED_RDP_WITH_GEO_CL
| extend 
    timestamp = TimeGenerated,
    latitude = toreal(extract("latitude:(.*?),", 1, RawData)),
    longitude = toreal(extract("longitude:(.*?),", 1, RawData)),
    destinationhost = extract("destinationhost:(.*?),", 1, RawData),
    username = extract("username:(.*?),", 1, RawData),
    sourcehost = extract("sourcehost:(.*?),", 1, RawData),
    state = extract("state:(.*?),", 1, RawData),
    label = extract("label:(.*?),", 1, RawData),
    country = extract("country:(.*?),", 1, RawData)
| where state != "null" and state != ""
| where country != "Russia" and destinationhost != "sample"
| summarize CountryCount = count() by country
| join kind=inner (
    FAILED_RDP_WITH_GEO_CL
    | extend 
        timestamp = TimeGenerated,
        latitude = toreal(extract("latitude:(.*?),", 1, RawData)),
        longitude = toreal(extract("longitude:(.*?),", 1, RawData)),
        destinationhost = extract("destinationhost:(.*?),", 1, RawData),
        username = extract("username:(.*?),", 1, RawData),
        sourcehost = extract("sourcehost:(.*?),", 1, RawData),
        state = extract("state:(.*?),", 1, RawData),
        label = extract("label:(.*?),", 1, RawData),
        country = extract("country:(.*?),", 1, RawData)
    | where state != "null" and state != ""
    | project latitude, longitude, destinationhost, username, sourcehost, state, label, country, timestamp
) on country
| project latitude, longitude, destinationhost, username, sourcehost, state, label, country, timestamp, CountryCount
```


<p align="center">
  <img src="https://i.imgur.com/faidQjb.png"/>
</p>

18. These are the section that were changed on the Map Settings.
19. Click <strong>Apply</strong> and then <strong>Save and Close</strong>.

<p align="center">
  <img src="https://i.imgur.com/FAC9ahJ.png"/>
</p>

20. Now our Map looks like this.
21. After 1000 API call, we have to wait until tomorrow for another 1000, then you will see the different countries that are attacking your Virtual Machine in real-time.

* Note: for the map to update with ne attacks, we need to make sure the Powershell script is running on the Virtual Machine, so that it can update the failed_rdp.log file. *

<p align="center">
  <img src="https://i.imgur.com/IGfrwNv.png"/>
</p>

22. Click the <strong>Save</strong> button at the top menue bar.

<p align="center">
  <img src="https://i.imgur.com/wwOeOLx.png"/>
</p>

23. Type your <strong></strong>, update the <strong></strong>Resource group ad Choose the Correct <strong></strong>.
<ul>
<li><strong>Title:</strong> FAILED RDP World Map</li>
<li><strong>Subscription: Choose your Microsoft subscription account.</strong></li>
<li><strong>Resource group:</strong> Choose your resource group that you've created</li>
<li><strong>Location:</strong> (US) West US 2</li>
</ul>

<p align="center">
  <img src="https://i.imgur.com/Qzj4oeZ.png"/>
</p>

24. Click the <strong>Done Editing</strong> button.

<p align="center">
  <img src="https://i.imgur.com/unKaku7.png"/>
</p>

25. Now click the <strong>X</strong> button at the top right to go back. This map can always be found by going to <strong>Microsoft Sentinel</strong>, <strong>Workkbook</strong> then selecting the Workbook we've created. There should only be one option if this lab is the only lab you followed along with so far. <strong></strong>


We have completed the project. This map looks great!

