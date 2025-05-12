For Agent Deployment via Powershell (With Admin Rights): 

Invoke-WebRequest -Uri http://www.dl.musisystems.com/musi-agent-1.4.82-1.msi -OutFile $env:tmp\musi-agent; msiexec.exe /i $env:tmp\musi-agent /q WAZUH_MANAGER='siem2c.musisystems.com' WAZUH_AGENT_GROUP='SGSIT'

Then run: 

NET START Musi

Our Cloud SIEM is located here

https://siem2c.musisystems.com:5555/

We will create users as per requested for viewing.
