<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
These step-by-step instructions will outline the prerequisites and installation of the open-source help desk ticketing system, osTicket.<br />


<h2>Environments and Technologies Used</h2>

* Microsoft Azure (Virtual Machines/Compute)
* Remote Desktop
* Internet Information Services ( IIS )

<h2>Operating Systems Used </h2>

* Windows 10</b> (21H2)

<h2>Start 20 step process</h2>

* Step 1: Download the osTicket-Installation-Files.zip and unzip/extract

  &emsp;* link > https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD



* Step 2: Install / Enable IIS in Windows WITH CGI
  
  &emsp;* Control panel > Programs > Uninstall Programs > Turn Windows features on/off
  
  &emsp;* Check Internet Information Services
  
  &emsp;* www  services > App Dev Features > CGI



* Step 3: Inside the osTicket folder, install

  &emsp;*  PHP (PHPManagerForIIS_V1.5.0.msi)

  &emsp; * Rewrite module (rewrite_amd64_en-US.msi)



* Step 4: Create a folder on the C drive called “ PHP ”


  
* Step 5: In the osTicket folder, extract all from > (php-7.3.8-nts-Win32-VC15-x86.zip) into the PHP folder



* Step 6: Install VC_redist.x86



* Step 7: Install mysql-5.5.62-win32
  
  &emsp;* Launch standard configuration
  
  &emsp;* Username: root
  
  &emsp;* Password: root




<h2>osTicket Installation Files</h2>

<p>
<img width="1280" alt="image 1 os Ticket Install" src="https://github.com/user-attachments/assets/013f44f1-f185-4422-867b-34d51bbc7566" />
</p>
<p>
Your screen should look like this. You have the “ osTicket ” file open on the left and the normal folder open in the middle. The two folders on the left are the osTicket folders, one is the unzipped version of the other.
</p>
<br />


* Step 8: Open IIS as an Admin > start > search “ IIS ” > Run as Admin user



* Step 9: Register PHP from within IIS > php manager > register new PHP version > browse to PHP folder inside and get “ php-cgi ”



* Step 10: refresh IIS > top left of IIS under " connections " right click “ practice-osTicket ” > click stop > wait a moment > click start

<p>
<img width="1280" alt="image 2 start and stop ISS" src="https://github.com/user-attachments/assets/adb338f1-5c63-4ba7-a6af-249f873eea76" />
</p>
<p>
This is the ISS and how to (Start | Stop) it



* Step 11: Install “ osTicket-v1.15.8.zip ” > extract > it will open folder w “ scripts | upload ”
  
  &emsp;* Put the “ upload ” folder into the “ c:\inetpub\wwwroot ” and rename “ upload ” to “ osTicket ”. Make sure the name is correct!



* Step 12: Reload ISS using the (stop | start) option



* Step 13: Load the osTicket site
  
   &emsp;* ISS > sites > default > osTicket
  
   &emsp;* On the right, click “ Browse*.80(http) ” ( This should pull up the osTicket site! )

<p>
<img width="1280" alt="image 3 osTiket page" src="https://github.com/user-attachments/assets/3a135bd2-c1f1-4d1a-9012-fd90583cbe5b" />
</p>
<p>
This is how your osTicket should look when it pulls up in the web browser.
</p>
<br />



* Step 14: Notice some extensions are not enabled

  &emsp;* ISS > Sites > Default sites > osTicket
  
  &emsp;&emsp;&emsp;* double click PHP manager (icon)

  &emsp;&emsp;&emsp;* click "enable or disable an extension" 

  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;* Enable: php_imap.dll

  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;* Enable: php_intl.dll

  &emsp;&emsp;&emsp;&emsp;&emsp;&emsp;* Enable: php_opcache.dll

  &emsp;* Refresh the osTicket browser and see that they are enabled



* Step 15: Rename ost-config.php

  &emsp; * From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  
  &emsp; * From: C:\inetpub\wwwroot\osTicket\include\ost-config.php



* Step 16: Assign permissions - ost-config.php

  &emsp; * Right click > properties > security > advancted > Disable inheritance > remove all

  &emsp; * Click add > principal > Everyone > ok > check off the “full control” option > ok, ok, ok, (now osTicket has control over the configuration file)

<p>
<img width="497" alt="image 4 like this " src="https://github.com/user-attachments/assets/7c89bbe1-bd7c-48da-b65f-07e7e85a38a7" />
</p>
<p>
The access should look something like this
</p>
<br />



* Step 17: Set up the rest of osTicket

  &emsp;* username : adminuser

  &emsp;* Password: Password1



* Step 18: from “ osTicket installation files ” install “ HeidiSQL_12.3.0.6589_Setup ”

  &emsp;* Double click > check accept box > ok, ok, ok

  &emsp;* Create new session > click new root/root

  &emsp;* Create data base called “ osTicket ” > right click dolphin > create new > database



* Step 19: Continue setting up your osTicket from the browser

  &emsp;* MySQL Database: osTicket

  &emsp;* MySQL Username: root

  &emsp;* MySQL Password: root

  &emsp;* Install now



* Step 20: osTicket is now installed!

  &emsp;* login page: http://localhost/osTicket/scp/login.php

  &emsp;&emsp;* Username: adminuser

  &emsp;&emsp;* Password: Password1

  &emsp;* Enter Tickets: http://localhost/osTicket/
