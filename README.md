# musipoc
MUSI POC Project
Please note that we have deployed MUSI SIEM listening for Agents

Invoke-WebRequest -Uri http://www.dl.musisystems.com/musi-agent-1.4.82-1.msi -OutFile $env:tmp\musi-agent; msiexec.exe /i $env:tmp\musi-agent /q WAZUH_MANAGER='siem2c.musisystems.com' WAZUH_AGENT_GROUP='RZQHQ' 

Requirements

    You will need administrator privileges to perform this installation.
    PowerShell 3.0 or greater is required.

Keep in mind you need to run this command in a Windows PowerShell terminal

NEXT: Start the agent:

NET START Musi






Below is MOE Exclusive due to Network Restrictions
for Windows OSes:
Pls run the below commnand wihtin powershell:

Invoke-WebRequest -Uri http://www.dl.musisystems.com/musi-agent-1.4.82-1.msi -OutFile $env:tmp\musi-agent; msiexec.exe /i $env:tmp\musi-agent /q WAZUH_MANAGER='192.168.88.55' WAZUH_AGENT_GROUP='MOEnergy'

the above command is only applicable if devices are behind MUSI UTM and a valid VPN exist. (you can test it by pining 192.168.88.1 and 192.168.88.55)

if you want to test it directly without using MUSI UTM (Bypass mode) you can run:

Invoke-WebRequest -Uri http://www.dl.musisystems.com/musi-agent-1.4.82-1.msi -OutFile $env:tmp\musi-agent; msiexec.exe /i $env:tmp\musi-agent /q WAZUH_MANAGER='siem2c.musisystems.com' WAZUH_AGENT_GROUP='MOEnergy'


then after successful deployments run this command.
Requirements
    You will need administrator privileges to perform this installation.
    PowerShell 3.0 or greater is required.
Keep in mind you need to run this command in a Windows PowerShell terminal.

RUN this command to start service

NET START Musi



======================================================================================================================================================

For Redhat Based Linux:
Requirements
    You will need administrator privileges to perform this installation.
    Shell Bash is required.
Keep in mind you need to run this command in a Shell Bash terminal.


curl -o wazuh-agent-4.10.1-1.x86_64.rpm www.dl.musisystems.com/wazuh-agent-4.10.1-1.x86_64.rpm && sudo WAZUH_MANAGER='siem2c.musisystems.com' WAZUH_AGENT_GROUP='MOEnergy' rpm -ihv wazuh-agent-4.10.1-1.x86_64.rpm


then pls make sure to run

sudo systemctl daemon-reload

sudo systemctl enable wazuh-agent

sudo systemctl start wazuh-agent
