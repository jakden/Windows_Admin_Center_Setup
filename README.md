# Windows Admin Center Setup

Windows Admin Center, formally knows as Project Honolulu, is a quick and easy way to manage you Windows Hyper-V Core hosts, on the same local network, remotely from a web browser.  

To get started we need to download the installation files.  To access the installer you can click the link below, a direct download link to the MSI on Microsoft's evaluation.

https://download.microsoft.com/download/1/0/5/1059800B-F375-451C-B37E-758FFC7C8C8B/WindowsAdminCenter1910.2.msi

![alt text](/posts/images/P0003/P0003_IMG01.png)

After the download has completed you can run the MSI file and walk through the prompts below on your PC.  

![alt text](/posts/images/P0003/P0003_IMG02.png)

**NOTE:** If you plan to deploy the Azure's Application Proxy alongside the Windows Admin Center for remote access or want to centralize the applications services, a version of Windows Server will be required.  Azure's Application Proxy allows you to manage your host over the internet through an Office 365 app session.  In later posts I will use Windows Admin Center to demo the Azure Application Proxy.

Accept the terms and click Next.

![alt text](/posts/images/P0003/P0003_IMG03.png)

Review Microsoft's documentation for more details about deployment options at the link provided during the installation https://aka.ms/WindowsAdminCenter-Install and click Next.

![alt text](/posts/images/P0003/P0003_IMG04.png)

An option will be presented to configure an alternate port, create a desktop icon and allow the application to update your Trusted Hosts.  To view or create a new host using Powershell, see the commands below.  Click Install once you are ready.

```Powershell
Get-Item WSMan:\localhost\Client\TrustedHosts
Set-Item WSMan:\localhost\Client\TrustedHosts -Value DEVICENAME
```

*You will need administrative rights to accept the UAC prompt.*

![alt text](/posts/images/P0003/P0003_IMG05.png)

![alt text](/posts/images/P0003/P0003_IMG06.png)

Select the certificate you would like to use to authenticate to the Windows Admin Center.  During the installation a default certificate will be automatically generated for use.  If you click the option to Open Windows Admin Center you will be provided with the web address to access the device.  This will need to be an IP address or hostname along with your port, as an example for a local install - https://localhost:6516.

![alt text](/posts/images/P0003/P0003_IMG07.png)

When the web page is opened you will receive a prompt to select the certificate to authenticate.

![alt text](/posts/images/P0003/P0003_IMG08.png)

Once you are authenticated you will be provided with the option to step through a tutorial to show you around.  In later posts I will walk through some of the basics tasks you will likely perform with the host.

![alt text](/posts/images/P0003/P0003_IMG09.png)
