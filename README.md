<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>
Video Tutorial Coming Soon!

<!-- - ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com) -->

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Install & enable Internet Information Services (IIS)
     <ul> 
      <li>CGI</li>
      <li>Common HTTP Features</li>
      <li>IIS Management Console</li>
     </ul>
- Download & Install all files below:
  <ol> 
      <li>PHPManagerForIIS_V1.5.0.msi</li>
      <li>rewrite_amd64_en-US.msi</li>
      <li>php-7.3.8-nts-Win32-VC15-x86.zip</li>
      <li>VC_redist.x86.exe</li>
      <li>mysql-5.5.62-win32.msi</li>
      <li>osTicket v1.15.8</li>
      <li>HeidiSQL_12.3.0.6589_Setup.exd</li>
     </ol>

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/JN3x4p0.png" height="40%" width="50%" alt="Disk Sanitization Steps"/>
</p>
<p>
After you create the Windows VM in Azure, the first steps in order to make sure osTicket is able to install properly on the VM are to go into the control panel and make sure IIS is checked. Within IIS... CGI, Common HTTP Features, & IIS Management Console are all checked as well. Once these are checked you run click ok. And, if you want to make sure you did this step correctly go to your browser of choice and type 127.0.0.1 in and if this page loads you are ready for the next steps. 
</p>
<br />

<p>
<img src="https://i.imgur.com/KyMrPvq.png" height="80%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
These are all the necessary files needed to run osTicket properly on your Windows VM, so this step shows all the programs/files I downloaded and then installed on the computer.
</p>
<br />

<p>
<img src="https://i.imgur.com/4bmFbOk.png" height="80%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
You will need to create a PHP directory within your C:Drive, once you do this extract the entire php-7.3.8-nts-Win32-VC15-x86.zip into the PHP Directory
</p>
<br />

<p>
<img src="https://i.imgur.com/THa54Nz.png" height="80%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
To build on the previous step we now need to load IIS in Windows as an administrator and register PHP, after you do this it is best to either stop and start IIS or you can restart it. Either one works equally the same. 
</p>
<br />

<p>
<img src="https://i.imgur.com/71VZBNK.png" height="80%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once osTicket is downloaded, copy the contents of the osTicket-v1.15.8.zip file "Upload" to C: Drive --> inetpub --> wwwroot, once the file copies over rename the file from "Upload" to "osTicket". After this, you will be able to load osTicket into the browser if all steps were completed correctly up to this point...
</p>
<br />

<p>
<img src="https://i.imgur.com/xWn4QEg.png" height="80%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
This image shows all the extensions we need to be enabled so that we can run osTicket make sure to enable (php_imap.dll, php_opcache.dll, php_intl.dll). Because they aren't once you first load up osTicket, so go back into PHP manager, and at the bottom the option to remove/add extensions will be there within IIS --> PHP Manager.
</p>
<br />

<p>
<img src="https://i.imgur.com/RXdirxa.png" height="80%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
Change the name of ost-sampleconfig.php to ost-config.php, then change the permissions so that any user has full control. This is important because the OSTicket installer is going to use this file and we don't know which user it's going to use to do that, so by getting everyone access we are able to make changes once this takes place.
</p>
<br />

<p>
<img src="https://i.imgur.com/PfwicXT.png" height="80%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install HeidiSQL, once open and running add new file and import the username and password we created we downloading MYSQL, for me it was (username: root, password: Password1) once you enter those credentials HiediSQL will be synced to osTicket. Once this is complete add a new database within the database and name it osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/hW7CDxQ.png" height="80%" width="60%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you are done with the previous step, osTicket will be completely downloaded and installed and you will be able to run osTicket as an admin!
</p>
<br />
