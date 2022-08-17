# Failed RDP to IP Geolocation Information
<h1>JWipe - Disk Sanitization</h1>

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
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
