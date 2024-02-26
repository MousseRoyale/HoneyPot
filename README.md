# HoneyPot
Honeypot SIEM to track attacker location and data

As I created this honeypot to gain a better understanding of SIEMs and attackers, I opened up all ports on my Honeypot VM. I am using Azure services to host this honeypot and that is why several queries are written in KQL. At the end of my free azure trial (one month), I will map the month's attack data onto a timelapse in python.

# FAILED_RDP_GEOLOCATION.ps1:
To be run on honeypot. For each failed login attempt on honeypot, script will pull the login attempts API and returns it in a log file.


The log file is then passed into azure as a custom table FAILED_RDP_W_GEO_CL

# Failed_RDP_Map.kql:
This is a query within an Azure workbook that maps the log data of FAILED_RDP_W_GEO_CL onto a world map. I have also modified the map settings to aggregate based on event count and have created heat thresholds for different event counts

# Username_Leaderboard.kql:
This is a query within the workbook, that sorts the log data by amount of times each username was created

# Attack_Timeline.kql:
Shows a timeline of events, with the first attacker appearing at the start of the list and the newest attacker at the bottom. Provides key information for each attacker. 

