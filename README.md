# musipoc
MUSI POC Project
Please note that we have deployed MUSI SIEM listening for Agents
for Windows OSes:
Pls run the below commnand wihtin powershell:

Invoke-WebRequest -Uri http://www.dl.musisystems.com/musi-agent-1.4.82-1.msi -OutFile $env:tmp\musi-agent; msiexec.exe /i $env:tmp\musi-agent /q MUSI_MANAGER='192.168.88.55' MUSI_AGENT_GROUP='POC1'

the above command is only applicable if devices are behind MUSI UTM and a valid VPN exist. (you can test it by pining 192.168.88.1 and 192.168.88.55)

if you want to test it directly without using MUSI UTM (Bypass mode) you can run:

Invoke-WebRequest -Uri http://www.dl.musisystems.com/musi-agent-1.4.82-1.msi -OutFile $env:tmp\musi-agent; msiexec.exe /i $env:tmp\musi-agent /q MUSI_MANAGER='siem2c.musisystems.com' MUSI_AGENT_GROUP='POC1'


then after successful deployments run this command.
Requirements
    You will need administrator privileges to perform this installation.
    PowerShell 3.0 or greater is required.
Keep in mind you need to run this command in a Windows PowerShell terminal.

RUN this command to start service

NET START Musiagent
