![Screenshot 2022-01-08 at 21-58-59 Hack The Box - Academy](https://user-images.githubusercontent.com/21301377/148647137-a7000e8d-6dd9-4422-bbe1-3a8e219862cb.png)
# hackthebox-windows-fundamental
Introduction to Windows

As a penetration tester, it is important to have knowledge of a wide variety of technologies. A thorough understanding of Windows and Linux operating systems is beneficial in a wide range of assessment types. The majority of systems that we encounter during assessments, whether on-premise or in the cloud, will be based on these two operating systems. It is important to understand how to attack and defend these operating systems and how they can each be used as a platform to perform further penetration testing activities.
The Windows Operating System

Microsoft first introduced the Windows operating system on November 20, 1985. The first version of Windows was a graphical operating system shell for MS-DOS. Later versions of Windows Desktop introduced the Windows File Manager, Program Manager, and Print Manager programs.

Windows 95 was the first full integration of Windows and DOS and offered built-in Internet support for the first time. This version also debuted the Internet Explorer web browser. Since the initial version, there have been over a dozen versions of Windows released, such as Windows XP, Vista, and 8, up to the current version: Windows 10. Over time, Microsoft has offered various editions of each Windows Desktop release catering to everyone from casual consumers to enterprise customers.

Windows Server was first released in 1993 with the release of Windows NT 3.1 Advanced Server. Windows NT saw several updates over the years, adding in technologies such as Internet Information Services (IIS), various networking protocols, Administrative Wizards to facilitate admin tasks, and more. With the release of Windows 2000, Microsoft debuted Active Directory, originally intended to help sysadmins set up file sharing, data encryption, VPNs, etc. Windows Server 2000 also included the Microsoft Management Console (MMC) and supported dynamic disk volumes.

Windows Server 2003 came next with server roles, a built-in firewall, the Volume Shadow Copy Service, and more. Windows Server 2008 included failover clustering, Hyper-V virtualization software, Server Core, Event Viewer, and major enhancements to Active Directory. Over the years, Microsoft released further Server versions, including Server 2012, Server 2016, and most recently, Server 2019. This latest version added support for Kubernetes, Linux containers, and more advanced security features.

As new versions of Windows are introduced, older versions are deprecated and no longer receive Microsoft updates (unless a long-term support contract is purchased in some cases). Windows Server 2008 and 2012 reached end of life for security updates on January 14, 2020. Currently, only Server 2012 R2 and later are in support. However, Microsoft has released out-of-band patches for earlier versions of Windows in the past few years due to the discovery of the critical SMBv1 vulnerability (EternalBlue).

Many versions of Windows are now deemed "legacy" and are no longer supported. Organizations often find themselves running various older operating systems to support critical applications or due to operational or budgetary concerns. An assessor needs to understand the differences between versions and the various misconfigurations and vulnerabilities inherent to each.
Windows Versions

![Screenshot 2022-01-08 at 21-54-35 Hack The Box - Academy](https://user-images.githubusercontent.com/21301377/148646857-cc4e247b-ce77-417f-8acb-eb8e5589e87a.png)

We can use the Get-WmiObject cmdlet to find information about the operating system. This cmdlet can be used to get instances of WMI classes or information about available WMI classes. There are a variety of ways to find the version and build number of our system. We can easily obtain this information using the win32_OperatingSystem class, which shows that we are on a Windows 10 host, build number 18362.

![Screenshot 2022-01-08 at 21-55-32 Hack The Box - Academy](https://user-images.githubusercontent.com/21301377/148646885-5e32a45a-6e8c-45af-acf4-ddd6490e9244.png)

Some other useful classes that can be used with Get-WmiObject are Win32_Process to get a process listing, Win32_Service to get a listing of services Win32_Bios to get BIOS information. We can use the ComputerName parameter to get information about remote computers. GetWmiObject can be used to start and stop services on local and remote computers, and more. Further information about the cmdlet can be found "https://ss64.com/ps/get-wmiobject.html" and "https://adamtheautomator.com/get-wmiobject/"

Target

Connect via Remote Desktop (RDP) using the following command:

![Screenshot 2022-01-08 at 21-57-39 Hack The Box - Academy](https://user-images.githubusercontent.com/21301377/148646938-9433610f-363d-4aee-8978-d8567203919f.png)
