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
After you create the Windows VM in Azure, the first steps in order to make sure osTicket is able to install properly on the VM are to go into the control panel and make sure IIS is checked. Within IIS... CGI, Common HTTP Features, & IIS Management Console are all checked as well. Once these are checked you run click ok. And, if you want to make sure you did this step correctly go to your browser of choice and type 127.0.0.1 in and if this page loads you are ready for the next steps. 
</p>
<img width="405" alt="1 copy" src="https://github.com/user-attachments/assets/24c33697-94e0-485d-b19b-741a2a5e5e77">
<img width="530" alt="Screenshot 2024-09-09 at 12 02 41 PM copy" src="https://github.com/user-attachments/assets/6a65926a-d6b7-48ea-af33-120d21173f21">
</p>
<br />

<p>
These are all the necessary files needed to run osTicket properly on your Windows VM, so this step shows all the programs/files I downloaded and then installed on the computer.
</p>
<p>
<img width="355" alt="2" src="https://github.com/user-attachments/assets/c18e616f-2a6b-4cd8-8f19-5fd26d0b64ea">
</p>
<br />

<p>
You will need to create a PHP directory within your C:Drive, once you do this extract the entire php-7.3.8-nts-Win32-VC15-x86.zip into the PHP Directory
</p>
<p>
<img width="610" alt="3 - make PHP folder extract it into this folder" src="https://github.com/user-attachments/assets/baab0bf7-e708-423b-9b99-be1440c6af0d">
</p>
<br />

<p>
To build on the previous step we now need to load IIS in Windows as an administrator and register PHP, after you do this it is best to either stop and start IIS or you can restart it. Either one works equally the same. 
</p>
<p>
<img width="1064" alt="4" src="https://github.com/user-attachments/assets/7df6857f-34bc-4019-88e4-f38f2657c93a">
</p>
<br />

<p>
Once osTicket is downloaded, copy the contents of the osTicket-v1.15.8.zip file "Upload" to C: Drive --> inetpub --> wwwroot, once the file copies over rename the file from "Upload" to "osTicket". After this, you will be able to load osTicket into the browser if all steps were completed correctly up to this point...
</p>
<p>
<img width="606" alt="5" src="https://github.com/user-attachments/assets/34cb8cd5-95bd-434d-b4ef-49f3a73bc196">
</p>
<br />

<p>
This image shows all the extensions we need to be enabled so that we can run osTicket make sure to enable (php_imap.dll, php_opcache.dll, php_intl.dll). Because they aren't once you first load up osTicket, so go back into PHP manager, and at the bottom the option to remove/add extensions will be there within IIS --> PHP Manager.
</p>
<p>
<img width="264" alt="6" src="https://github.com/user-attachments/assets/516585e7-a9d4-493d-b0d1-e6aa12e13307">
</p>
<br />

<p>
Change the name of ost-sampleconfig.php to ost-config.php, then change the permissions so that any user has full control. This is important because the OSTicket installer is going to use this file and we don't know which user it's going to use to do that, so by getting everyone access we are able to make changes once this takes place.
</p>
<p>
<img width="839" alt="7" src="https://github.com/user-attachments/assets/ffc55d88-cae3-401b-9ea8-03e10b5abdd3">
</p>
<br />

<p>
Install HeidiSQL, once open and running add a new file and import the username and password we created we downloading MYSQL, for me it was (username: root, password: Password1) once you enter those credentials HiediSQL will be synced to osTicket. Once this is complete add a new database within the database and name it osTicket.
</p>
<p>
<img width="927" alt="8" src="https://github.com/user-attachments/assets/43d27b52-16d8-4650-9456-9d0d1e56fb99">
</p>
<br />

<p>
Once you are done with the previous step, osTicket will be completely downloaded and installed and you will be able to run osTicket as an admin!
</p>
<p>
<img width="753" alt="9" src="https://github.com/user-attachments/assets/8e3edb89-3808-4340-b2fb-666811d3ddc0">
</p>
<br />
