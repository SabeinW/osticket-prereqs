<p align="center">
<img src="https://www.zippyops.com/userfiles/cache/thumbnails/1920/tn-osticket-1517973894.jpg" alt="osTicket logo"
  height="200"
  width="700"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create an Azure Virtual Machine Windows 10
- Log into the VM with Remote Desktop
- Install / Enable IIS in Windows WITH CGI
- install PHP Manager for IIS 
- Create the directory C:\PHP
- unzip PHP 7.3.8
- install VC_redist.x86.exe
- install MySQL 5.5.62
- Open IIS as an Admin and register PHP from within IIS
- Reload IIS
- Install osTicket v1.15.8
- Reload IIS
- Enable: php_imap.dll, Enable: php_intl.dll, Enable: php_opcache.dll
- Rename: ost-config.php
- assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All
- Continue Setting up osTicket in the browser
- install HeidiSQL
- Create a database
- Continue Setting up osTicket in the browser and then install
  






<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/V75ke5Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Created and deployed the Windows 10 virtual machine in Azure, inside the "osTicket" resource group for unified deployment, organization as well as easier management. 
</p>
<br />

<p>
<img src="https://i.imgur.com/nnRy2hK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once we deploy our VM we log into it using Windows remote desktop connection. Which is RDP (Remote Desktop Protocol), a Microsoft protocol that allows you to remotely access another computer as if you were sitting right in front of it.
</p>
<br />

<p>
<img src="https://i.imgur.com/86t3Fpd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
When you visit osTicket.com, the official website for osTicket, you can find the prerequisites required for the installation and proper operation of the osTicket system. These prerequisites include server specifications, software versions, and settings that need to be in place before installing osTicket. By meeting all these prerequisites, you will ensure that osTicket runs effectively and securely, giving you a reliable ticketing system for your help desk operations.
</p>
<br />

<p>
<img src="https://i.imgur.com/yRGgSNH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/XMbuZu3.png"/>
</p>
<p>
Before we can use osTicket we must install/enable IIS (Internet Information Services) along with CGI ( a dependency that osTicket needs).
</p>
<br />

<p>
<img src="https://i.imgur.com/zAK8p0r.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
PHP manager for IIS (a must-have if you're running PHP apps on a Windows IIS server because it simplifies PHP version control, configuration, and troubleshooting
</p>
<br />

<p>
<img src="https://i.imgur.com/mq7nZo2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ias3gDR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create a PHP folder on the windows C drive and from the php-7.3-nts folder, extract to the PHP folder on the C drive (Extracting PHP to C:\php is the best practice because it prevents permission issues, simplifies configuration, and avoids path-related problems in IIS.).
</p>
<br />

<p>
<img src="https://i.imgur.com/gFDw6zd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Microsofft Visual C++ Redistrubutable is a essential requirement for running osTicket on IIS with PHP, ensuring the proper execution of PHP extensions and FastCGI components
</p>
<br />

<p>
<img src="https://i.imgur.com/Hm2T9Vl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 A database that osTicket will use to store all our data (MySQL Server is the "brain" behind osTicket, storing all tickets, users, and configurations!)
</p>
<br />

<p>
<img src="https://i.imgur.com/q4xPMAs.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Registering PHP in IIS ensures your server can process PHP scripts and run apps like osTicket, WordPress, or Laravel!
Download and install PHP Manager for IIS. Open IIS and click PHP Manager in the Features View. Click "Register New PHP Version" and select php-cgi.exe from your PHP installation folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/bZBMhZV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/ywFmytw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Extract osTicket-v1, then rename the upload folder to osTicket. Extract it to a directory like C:\inetpub\wwwroot, doing so makes the installation path cleaner (e.g., C:\inetpub\wwwroot\osTicket), ensures osTicket works properly with IIS, and easier to reference when configuring the web server.
</p>
<br />

<p>
<img src="https://i.imgur.com/Bwq8gay.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/uMqPMi9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In IIS Manager, select your server from the left panel.
Double-click PHP Manager in the Features View. Enable the Required Extensions. Click "Enable or disable an extension" under PHP settings. Find and select the following extensions:
php_imap.dll
php_intl.dll
php_opcache.dll
Click Enable.
Restart IIS (In IIS Manager, click Restart on the right-side panel)
</p>
<br />

<p>
<img src="https://i.imgur.com/7pYw6fd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Right-click the ost.config.php file.Select "Rename", enter the new name, such as newname.config.php, and press Enter. Make sure the new name is consistent with the file's role in your project, so the system can still locate and process the configuration file correctly.
</p>
<br />

<p>
<img src="https://i.imgur.com/gEnuECc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
<img src="https://i.imgur.com/bzcabff.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/a8oUb8u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Set the right permissions for configuration and upload directories to allow the web server to write data (e.g., chmod 755).
Ensure the web server owns the files (chown www-data:www-data).
Grant the database user proper permissions (e.g., GRANT SELECT, INSERT, UPDATE, DELETE).
Manage admin/staff roles and permissions through the osTicket admin panel.
Always audit and secure your installation to minimize vulnerabilities.
By configuring the permissions correctly, osTicket can manage backend operations smoothly while ensuring security.
</p>
<br />

<p>
<img src="https://i.imgur.com/qHchNAF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue setup on osTickets website.
</p>
<br />

<p>
<img src="https://i.imgur.com/32tS01O.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
HeidiSQL is a powerful tool for managing and configuring your databases, making it easier to perform complex database-related tasks without needing to rely solely on command-line tools.
</p>
<br />

<p>
<img src="https://i.imgur.com/qgGo8eo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once configured, osTicket will be able to store and retrieve ticket data, configurations, and user information in the newly created database.
</p>
<br />

<p>
<img src="https://i.imgur.com/zTGuaHy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
So, the osTicket database will play a crucial role in storing and managing all the data that makes the ticketing system work effectively. Without it, osTicket wouldn't be able to store, retrieve, or update tickets and other vital data.
</p>
<br />

<p>
<img src="https://i.imgur.com/x35CbK3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue with the installation process by entering the database settings and credentials we made in HeidiSQL, then click Install Now.
</p>
<br />

<p>
<img src="https://i.imgur.com/z9f2sQe.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We have officially installed osTicket and are ready to start the post-installation process!  
</p>
<br />

