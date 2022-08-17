# Failed RDP to IP Geolocation Information
<h1>SIEM- Azure Sentinel</h1>

<h2>Description</h2>
The Powershell script in this repository is responsible for parsing out Windows Event Log information for failed RDP attacks and using a third party API to collect geographic information about the attackers location.

The script is used in this demo where I setup Azure Sentinel (SIEM) and connected it to a live virtual machine acting as a honey pot. We will observe live attacks (RDP Brute Force) from all around the world. I will use a custom PowerShell script to look up the attackers Geolocation information and plot it on an Azure Sentinel Map!
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell: Extract RDP failed logon logs from Windows Event Viewer</b>
- <b>Microsoft Azure Sentitnel: Used to plot map of various RDP Brute Force attacks</b>
- <b>ipgeolocation.io: IP Address to Geolocation API</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)

<h2>Program walk-through:</h2>

<p align="center">
Launch of Azure: <br/>

![Screenshot (174)](https://user-images.githubusercontent.com/20980822/185135848-e7e8c70a-b4b2-4871-b8fe-46e2f5edcf41.png)
<br />
<br />
Setting up windows 10:  <br/>
![Screenshot (142)](https://user-images.githubusercontent.com/20980822/185228225-e2e899af-222e-4abb-a699-8aa437c81ed2.png)
![Screenshot (145)](https://user-images.githubusercontent.com/20980822/185228726-71d7d32a-1f3b-480b-927f-e49abc5109dc.png)
![Screenshot (146)](https://user-images.githubusercontent.com/20980822/185228751-b9f27772-8d60-4b52-8a2e-e9ff43f98864.png)
<br />
<br />
Setting Up our firewall to be exposed to the public internet: <br/>
setting this up so our address can be exposed and attackers can attack the windows 10 i setup <br/>
![Screenshot (149)](https://user-images.githubusercontent.com/20980822/185230192-7cc1a90a-8293-4676-8e14-388a827fa158.png)
![Screenshot (151)](https://user-images.githubusercontent.com/20980822/185230491-91b66c86-2deb-4fb3-bd94-dcc050f18ccb.png)
![Screenshot (153)](https://user-images.githubusercontent.com/20980822/185230569-458e9ccd-4359-4108-b92c-06f4b7657fc1.png)
![Screenshot (154)](https://user-images.githubusercontent.com/20980822/185230668-6620c8a6-e18b-40fa-a0e0-35720fb70c07.png)

<br />
Creating Log Analytics Workspace: <br/>
The reason for creating the log analytics is so we can inject event logs from the virtual machine created we created and add a custom geographical information which will tell where the attacks are coming from

![Screenshot (159)](https://user-images.githubusercontent.com/20980822/185236011-1682e9e4-0867-4e9b-b852-738338c7114f.png)
![Screenshot (160)](https://user-images.githubusercontent.com/20980822/185236068-023b4361-778b-47d0-aee1-a36e3c6c150c.png)
<br />
<br />
Enabling the ability to gather logs from the virtual machine in the secuirty center: <br/>
Enabling this allows the log analytics workspace to gather logs from the virtual machine. to do this one turns on the azure defender on and on the data coleection we enable it to store all event logs.
![Screenshot (164)](https://user-images.githubusercontent.com/20980822/185238198-3044096a-bd70-4387-9cf6-8c1e6aa11539.png)
![Screenshot (166)](https://user-images.githubusercontent.com/20980822/185238211-8dba03e7-186e-4138-aac4-6f2ec3122197.png)
![Screenshot (168)](https://user-images.githubusercontent.com/20980822/185238395-d9c1dfc7-67a5-488b-8db8-be9f038bc658.png)
![Screenshot (169)](https://user-images.githubusercontent.com/20980822/185238400-e43708f1-89e3-426e-b8f8-d5fc27681512.png)
<br />
<br />
Connecting the Log Analytics workspace to the virtual machine:  <br/>
![Screenshot (170)](https://user-images.githubusercontent.com/20980822/185239198-9d3fc345-e282-4b00-b9e1-1dc4cb1e3962.png)
![Screenshot (171)](https://user-images.githubusercontent.com/20980822/185239208-4ef9fd70-b4cd-4bf8-a51d-3ea6fd0adbed.png)
<br />
<br />
Setting up Microsoft Sentinel:  <br/>
![Screenshot (175)](https://user-images.githubusercontent.com/20980822/185240133-ad585c47-bf06-4507-991a-d77e0e0b6615.png)
<br />
<br />
Launching the windows 10 using RDP:  <br/>
![Screenshot (176)](https://user-images.githubusercontent.com/20980822/185241034-0a7a2e94-c2c2-4a5b-9d7a-3e0b12eb07f2.png)
![Screenshot (177)](https://user-images.githubusercontent.com/20980822/185241051-64a133ea-c10b-4992-a036-fe9b9041d92b.png)
![Screenshot (178)](https://user-images.githubusercontent.com/20980822/185241110-53883055-09e0-4b6b-933b-2bd0803c3f4d.png)
![Screenshot (179)](https://user-images.githubusercontent.com/20980822/185241125-83ee8cc7-3b41-4fff-a303-aa55331e41d9.png)
![Screenshot (181)](https://user-images.githubusercontent.com/20980822/185241136-51ac7537-8c09-4829-82b6-1c58575d4ad2.png)
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
