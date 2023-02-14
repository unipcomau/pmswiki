# PC Setup steps for Onboarding (Wiki)
- Microsoft Team Microsoft Teams Version 23002.403.1788.1930
- D: drive
- Setup Do_not_Move and PMS folder
- Setup PowerShell 5.1.22621.963 prompt in ConEmu
- Chocolatey and packages
  - choco install sql-server-management-studio  
- SQL Server 2019 Developer (15.0.2095.3) Standalone installation
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
- Setup TortoiseGit (- choco install tortoisegit) and Beyond Compare DIFF 
- 3rd party DLL and Tools
  - Telerik Reporting (https://www.telerik.com/products/reporting.aspx)
  - (no setup) Telerik ASP.NET AJAX in WebUI (https://www.telerik.com/products/aspnet-ajax.aspx)
- OpenVPN- 3.3.6 (2752)
- LINQPad 7.7.1 64 bit Add licence key
- LLBLGen Add licence file
- OzCode
- IIS setup internal.portfoliomanager.cloud and internal.unip.com.au
