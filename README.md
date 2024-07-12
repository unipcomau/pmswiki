# Training PC Setup steps for Onboarding (Wiki)
- Microsoft Team Microsoft Teams Version 24060.3102.2733.5911. The client version is 48/24032909844.
- D: drive
- Setup Do_not_Move and PMS folder
- Setup PowerShell 5.1.22621.963 prompt in Windows Terminal
- SQL Server 2022 Developer
- Create folder C:\Temp\PMSDB
- Create folder C:\Temp\PMSDB\Snapshots

NEW for SQL22

![image](https://github.com/user-attachments/assets/6addeabb-1ddf-46dd-aae3-e0b4bc44c141)

![image](https://github.com/unipcomau/pmswiki/assets/71107438/3f0d2852-a68d-4567-821e-72e82e328b4f)

![image](https://github.com/unipcomau/pmswiki/assets/71107438/4c7fa180-8c63-47e0-a1a3-945ae43543eb)

![image](https://github.com/unipcomau/pmswiki/assets/71107438/2dc0092d-c69a-4193-b46c-bf94c1573346)

SQL19

![image](https://user-images.githubusercontent.com/71107438/218455248-e974b527-ecd0-4282-822d-2193a6753ee9.png)

![image](https://user-images.githubusercontent.com/86107243/218457084-c6abc38b-b4c0-4aba-ac25-dd918b8fc646.png)

- https://blog.sqlauthority.com/2015/07/13/sql-server-how-to-change-server-name/
- SELECT  HOST_NAME() AS 'host_name()',
@@servername AS 'ServerName\InstanceName',
SERVERPROPERTY('servername') AS 'ServerName',
SERVERPROPERTY('machinename') AS 'Windows_Name',
SERVERPROPERTY('ComputerNamePhysicalNetBIOS') AS 'NetBIOS_Name',
SERVERPROPERTY('instanceName') AS 'InstanceName',
SERVERPROPERTY('IsClustered') AS 'IsClustered'
- ![image](https://user-images.githubusercontent.com/71107438/218431728-72d41f8c-bec0-4f74-8143-01eaaf4c12d4.png)
- StackExchange Link : Developer setup as instance https://dba.stackexchange.com/questions/322065/how-do-i-download-sql-server-2019-developer-edition
  Download : https://go.microsoft.com/fwlink/?linkid=866662 
- Beyond Compare 4.4.5 27371 (- choco install beyondcompare) Add licence key
- Use developer email address and setup BitBucket as SSH/SSL to get the Code in PMS folder
- Setup git alias rb pu gs gg (Commit using gg - Git GUI)
- ![image](https://github.com/unipcomau/pmswiki/assets/71107438/5ec7ca95-c923-4eb9-ba2e-311503a1f4a5)

  ![image](https://github.com/unipcomau/pmswiki/assets/71107438/47d6ec2d-f441-46f3-8758-30a54d881751)

  [oh-my-posh.txt](https://github.com/unipcomau/pmswiki/files/15080386/oh-my-posh.txt)

- Beyond Compare DIFF 
- 3rd party DLL and Tools
  - Telerik Reporting (https://www.telerik.com/products/reporting.aspx)
  - (no setup) Telerik ASP.NET AJAX in WebUI (https://www.telerik.com/products/aspnet-ajax.aspx)
- LINQPad 7.7.1 64 bit Add licence key
- LLBLGen Add licence file

- 7Zip
- Portable folder
- Notepad3

- PS> choco upgrade all
Chocolatey v2.2.2
Upgrading the following packages:

dropbox v198.4.7615 
git v2.45.0 
git.install v2.45.0 
oh-my-posh v19.25.0 
openvpn-connect v3.4.4 (login as 'support')
postman v10.24.16 
powershell-core v7.4.2 
powertoys v0.80.1 
rdtabs v3.0.12 
soapui v5.7.2 
tortoisegit v2.16.0 
vscode v1.89.0 
vscode.install v1.89.0 

- IIS setup internal.portfoliomanager.cloud and internal.unip.com.au in hosts file<br />
- IIS Rewrite Module 2 (v7.2.1993)

#Local Sites<br />
127.0.0.1         internal.unip.com.au<br />
127.0.0.1         internal.portfoliomanager.cloud<br />
127.0.0.1         internal.portfolio.live<br />
127.0.0.1         template.unip.com.au<br />
127.0.0.1         template.portfoliomanager.cloud<br />
127.0.0.1         template.portfolio.live<br />

#Remote Sites when connecting via VPN<br />
#172.31.11.0       uat.portfolio.live<br />
#172.31.11.0       uat.portfoliomanager.cloud<br />
#172.31.11.0       uat.unip.com.au<br />

#Remote Sites when connecting via Direct PublicIP of the server<br />
13.211.124.248       uat.portfolio.live<br />
13.211.124.248       uat.portfoliomanager.cloud<br />
13.211.124.248       uat.unip.com.au<br />

#When moving a server to new IP (Prod) - setup testing<br />
#172.31.13.16      nextprod.portfolio.live<br />
#172.31.13.16      nextprod.portfoliomanager.cloud<br />
#172.31.13.16      nextprod.unip.com.au<br />

git checkout -b NUMBER_AMIT_BRANCHNAME origin/master;git push -u origin NUMBER_AMIT_BRANCHNAME;     
996_SNEHAL_LLBLGenUpgrade591to594 
git checkout -b 996_SNEHAL_LLBLGenUpgrade591to594 origin/master;
git push -u origin 996_SNEHAL_LLBLGenUpgrade591to594;


How to create package<br />
1. Connect to VPN<br />
2. PS> profile cmd to open PowerShell_profile.ps1 Or path:C:\Users\LPT142\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1<br />
3. PS> jump cmd or Go to Path "D:\Do_not_Move\PMS\Source\PMS.PAS\BuildTools\Psake\deploy_PMS"  <br />
4. PS> .\localBuild.bat SFTPUF  For UAT FULL Package. (For MINI package use SFTPUM) =><br />
5. Above cmd will transfer the package to Remote Folder :  C:\HostingSpaces\admin\uat.unip.com.au\restorefrom<br />
6. We can check status of last release : https://uat.unip.com.au/status/api/<br />
7. Put this json into notepad<br />
8. PS>  .\sessionConnect.ps1 (It will open Putty software)<br />
9. Double click on UAT 172.31.11.0(unipftp) will open the PowerShell prompt<br />
10. PS C:\HostingSpaces\do_not_move\Portable\Psake\deploy_PMS>.\serverDeployUAT.bat TestPackage<br />
11. PS C:\HostingSpaces\do_not_move\Portable\Psake\deploy_PMS>.\serverDeployUAT.bat Deploy<br />
12. We can check status of our release : https://uat.unip.com.au/status/api/<br />

Email for UAT<br />
Deployed a new version in UAT - 23.203.1644_M00387_UM Database Change Required (LINQPad script count - 0, DBScript count - 0, Schema change - NO, Data change - NO, Batch Job - NO, Web/Web-Template.config - NO BatchJob.config - NO)

Hi Ashok,

Deployed a new version in UAT - 23.203.1644_M00387_UM Database Change Required (LINQPad script count - 0, DBScript count - 0, Schema change - NO, Data change - NO, Batch Job - NO, Web/Web-Template.config - NO BatchJob.config - NO).

@'Amit Kakaiya' please deploy below branch on production tonight.

Branch: MIX_MEHUL_653_AMIT_975

![image](https://user-images.githubusercontent.com/71107438/220879633-0a796a65-715b-47b6-a9a3-2e0d30ddcc65.png)

![image](https://user-images.githubusercontent.com/71107438/218746935-f925da82-7c08-4316-8112-8d0ad492477f.png)

![image](https://user-images.githubusercontent.com/71107438/220823620-879c1450-1c66-4559-a854-c8e3cd8b2ddf.png)

![image](https://user-images.githubusercontent.com/71107438/221779053-910ccfa7-e9e5-4af0-a37a-061098bc8f12.png)

![image](https://user-images.githubusercontent.com/71107438/224647508-8eb4facc-ae74-4210-8a59-538ba74fd328.png)

![Stock Buy Sell Lines](https://user-images.githubusercontent.com/71107438/233927415-6ab401e9-6119-4597-b275-a9cad912f591.png)



![image](https://github.com/unipcomau/pmswiki/assets/71107438/2dc0092d-c69a-4193-b46c-bf94c1573346)


