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
Hi, welcome to my tutorial on how to install/set up osTicket from scratch on my Windows OS. In the picture below, you can see that after you create the Windows VM in Azure, the first steps in order to make sure osTicket is able to be installed properly on the VM is to go into the control panel and make sure IIS is checked. Within IIS... CGI, Common HTTP Features, & IIS Management Console are all checked as well. Once these are checked you run click ok. And, if you want to make sure you did this step correctly go to your browser of choice and type 127.0.0.1 in, and if this page loads you are ready for the next steps. 
</p>
<img width="405" alt="1 copy" src="https://github.com/user-attachments/assets/24c33697-94e0-485d-b19b-741a2a5e5e77">
<img width="530" alt="Screenshot 2024-09-09 at 12 02 41 PM copy" src="https://github.com/user-attachments/assets/6a65926a-d6b7-48ea-af33-120d21173f21">
</p>
<br />

<p>
Next, for this lab, there are a lot of files/programs that are going to need to be downloaded/installed. Go in the order below to ensure that all steps are being fulfilled because one mess up and it will be hard to pinpoint where you went wrong because this lab is lengthy. To access all of these download links use this link right here: https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0 once downloaded all of these will show up within the Windows VMs download folder so they will be easily accessible. So after this is downloaded go ahead and install (1 & 2) in the list and you will be good to move on to the next step.
</p>
<ol>
     <li>PHPManagerForIIS_V1.5.0.msi (DOWNLOAD & INSTALL)</li>
     <li>rewrite_amd64_en-US.msi (DOWNLOAD & INSTALL)</li>
     <li>php-7.3.8-nts-Win32-VC15-x86.zip (DOWNLOAD & EXTRACT INTO PHP FOLDER WITHIN C:Drive)</li>
     <li>VC_redist.x86.exe (DOWNLOAD & INSTALL)</li>
     <li>mysql-5.5.62-win32.msi (DOWNLOAD & INSTALL)</li>
     <li>osTicket v1.15.8 (DOWNLOAD & INSTALL)</li>
     <li>HeidiSQL_12.3.0.6589_Setup.exd (DOWNLOAD & INSTALL)</li>
</ol>

<p>
<img width="355" alt="2" src="https://github.com/user-attachments/assets/c18e616f-2a6b-4cd8-8f19-5fd26d0b64ea">
</p>
<br />

<p>
Now since PHPManager & rewrite_amd are installed. The next step is to go within the hardrive and create a folder named PHP in the C: Drive. Once this is created you will unzip php-7.3.8 into this folder directly.
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
Now since we have downloaded the first 3 programs for osTicket. At this point we can go ahead and install (4 & 5). In MySQL do a typical setup & standard configuration. It is going to ask for a password for username: root, whatever you use as the password make sure to remember, because this will be important in later steps. Now install, osTicket once finishing installing, copy the contents of the osTicket-v1.15.8.zip file "Upload" to C: Drive --> inetpub --> wwwroot, once the file copies over rename the file from "Upload" to "osTicket". After this, you will be able to load osTicket into the browser if all steps were completed correctly up to this point...
</p>
<p>
<img width="606" alt="5" src="https://github.com/user-attachments/assets/34cb8cd5-95bd-434d-b4ef-49f3a73bc196">
</p>
<br />

<p>
Okay so we are almost done at this point, go back into IIS and navigate on the left (Go to sites -> Default -> osTicket... On the right, click “Browse *:80”). You will see that there are a few red X's we need to enable those extensions, so go back into IIS and navigate to PHP Manager. Scroll towards the bottom unit you see “Enable or disable an extension”, once you see this click it and enable the 3 extensions that are disabled on the osTicket page (php_imap.dll, php_opcache.dll, php_intl.dll).
</p>
<p>
<img width="600" alt="Screenshot 2024-09-09 at 12 27 19 PM" src="https://github.com/user-attachments/assets/d5772a80-0e7c-4ffd-b45f-edf8629b1569">
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
<img width="1427" alt="Screenshot 2024-09-09 at 12 36 11 PM" src="https://github.com/user-attachments/assets/9e788afa-5749-4812-9fe8-75d8a838be62">
<img width="753" alt="9" src="https://github.com/user-attachments/assets/8e3edb89-3808-4340-b2fb-666811d3ddc0">
</p>
<br />
