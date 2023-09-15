<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and How to Install</h1>
osTicket is an open source ticketing system. Ticketing systems are used in Information Technology (IT) for users to create requests for service. It is widely used across all areas of IT especially help desk. This tutorial will go over how to install osTicket on an Azure virtual machine. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Step 1: Install Internet Information Services 
- Step 2: Install PHP Manager for IIS
- Step 3: Install osTicket
- Step 4: Install HeidiSQL

<h2>Installation Steps</h2>

We will be creating a Windows 10 virtual machine using Microsoft Azure. 

Once the virtual machine is created, we will be logging into the virtual machine using remote desktop protocol. 


![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/20764c18-61e3-4273-98df-3fb35d2eaee2)


<h3>Step 1: Install Internet Information Services </h3>
The first step is to install Internet Information Services (IIS) in Windows. Go to the Start menu and type in "Control Panel" and open it. Click "Programs" and then click "Turn Windows features on or off". Then click and enable check Internet Information Services. 

<p></p>

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/46943e49-12a8-4389-bb25-307f8dd3879c)


<h3>Step 2: Install PHP Installer with IIS </h3> 
The second step is to PHP Manager with IIS and all other neccesary files to run osTicket. 

<p></p>

To start, open up these download files [here](https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).

Download PHP Mananger and rewrite module from the google drive. Then open up the file in the Downloads folder and install the application. 

<p></p>
  
![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/393fbfbe-0716-4da9-9bd3-75c768ebcd24)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/af2e6fdd-5c54-4fcd-a2dd-0fab85f43697)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/68f6d35a-67e8-4a60-92fe-74d1b7410277)

Create the directory C:\PHP

From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/25e360a3-11c2-4a13-a6c3-39ec44d96b2f)

From the Installation Files, download and install VC_redist.x86.exe.

From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1


<p>
<img src="https://i.imgur.com/pqDM8rr.png" height="80%" width="80%" alt="8."/>
</p>

<p>
<img src="https://i.imgur.com/ykZCSNB.png" height="80%" width="80%" alt="9."/>
</p>

Follow the installation process. The Installer will inherently fail installing some of the items. Find those items in the Google Drive folder that was mentioned previously.

Install the following:
- PHP Version 7.3.8.
- Microsoft Visual C++ 2009 Redistributable Package.
- PHP Manager 1.5.0 for IIS 10.

<p>
<img src="https://i.imgur.com/nQoI9GZ.png" height="80%" width="80%" alt="10."/>
</p>

<p>
<img src="https://i.imgur.com/dI77INN.png" height="80%" width="80%" alt="11."/>
</p>

<p>
<img src="https://i.imgur.com/ht5QrzG.png" height="80%" width="80%" alt="12."/>
</p>

<p>
<img src="https://i.imgur.com/PMiBxmc.png" height="80%" width="80%" alt="13."/>
</p>

<h3>Step 3: Install osTicket</h3>
Third step is to install osTicket. Go to the Google Drive mentioned previously and download the osTicket files. Once it is downloaded, open the osTicket folder. Copy the "Upload" folder. 

Open up a new Windows Explorer Window, go to "This PC" on the left hand side, go to C:\, then "inetpub", then wwwroot. This can also be pasted in the Explorer bar "c:\inetpub\wwwroot". Paste the "Upload" folder into the wwwroot folder and rename it "osTicket."

<p>
<img src="https://i.imgur.com/SmiOjs6.png" height="80%" width="80%" alt="14."/>
</p>

<p>
<img src="https://i.imgur.com/GAbKERu.png" height="80%" width="80%" alt="15."/>
</p>

<p>
<img src="https://i.imgur.com/TjUdLgj.png" height="80%" width="80%" alt="16."/>
</p>

<p>
<img src="https://i.imgur.com/1DCcmlK.png" height="80%" width="80%" alt="17."/>
</p>

<p>
<img src="https://i.imgur.com/YaCtxHm.png" height="80%" width="80%" alt="18."/>
</p>

Once all this is completed, open up IIS from the start menu. On the left hand side of IIS, open up the directory (it should be the virtual machine name), then go to sites, then osTicket. Once osTicket has been opened in IIS, click "Browse *:80 (http)" on the right.

<p>
<img src="https://i.imgur.com/Kx4KiP5.png" height="80%" width="80%" alt="19."/>
</p>

<p>
<img src="https://i.imgur.com/0hOzHJ9.png" height="80%" width="80%" alt="20."/>
</p>

<p>
<img src="https://i.imgur.com/4eQjySx.png" height="80%" width="80%" alt="21."/>
</p>

Before going forward with the osTicket Installer, there must be some add-ons enabled first. Go back to IIS and click on "PHP Manager." Then click "Enable or disable an extension."

Right click and enable the following: 
- php_imap.dll.
- php_intl.dll.
- php_opcache.dll.

<p>
<img src="https://i.imgur.com/mrRBeJU.png" height="80%" width="80%" alt="22."/>
</p>

<p>
<img src="https://i.imgur.com/IAqrxAI.png" height="80%" width="80%" alt="23."/>
</p>

<p>
<img src="https://i.imgur.com/N5CGt5v.png" height="80%" width="80%" alt="24."/>
</p>

<p>
<img src="https://i.imgur.com/a4K62lK.png" height="80%" width="80%" alt="25."/>
</p>

Once all those are installed, switch back to the osTicket Installer and refresh it. An extension should have changed from a red x to a green check. 

<p>
<img src="https://i.imgur.com/VeuTLZV.png" height="80%" width="80%" alt="26."/>
</p>

Open up Windows Explorer and it should still be on the osTicket folder. Open up the "include" folder and scroll down to the file "ost-sampleconfig.php." Rename this file to "ost-config.php."

If you're lost as to where to go in Windows Explorer, copy and paste this: "C:\inetpub\wwwroot\osTicket\include\".

<p>
<img src="https://i.imgur.com/rlgHvnR.png" height="80%" width="80%" alt="27."/>
</p>

<p>
<img src="https://i.imgur.com/yNnb593.png" height="80%" width="80%" alt="28."/>
</p>

Once the file has been renamed, right click on the file "ost-config.php" and click on "Properties." Then go to the "Security" tab then click the "Advanced" button. Then click "Disable inheritance." 

Once this is done, add a new permission by typing "Everyone" in the box, and check "Full Control." Then click "OK" to exit out. 

<p>
<img src="https://i.imgur.com/wq4jAUp.png" height="80%" width="80%" alt="29."/>
</p>

<p>
<img src="https://i.imgur.com/CBcLz7d.png" height="80%" width="80%" alt="30."/>
</p>

<p>
<img src="https://i.imgur.com/F831pQE.png" height="80%" width="80%" alt="31."/>
</p>

<p>
<img src="https://i.imgur.com/bJzumr2.png" height="80%" width="80%" alt="32."/>
</p>

Once this is done, go back to the osTicket Installer. Start to fill out the setup page until you get to the database settings. 

<p>
<img src="https://i.imgur.com/lzl7E3x.png" height="80%" width="80%" alt="33."/>
</p>

<p>
<img src="https://i.imgur.com/z729IeR.png" height="80%" width="80%" alt="34."/>
</p>

<p>
<img src="https://i.imgur.com/a7rAHrb.png" height="80%" width="80%" alt="35."/>
</p>

<h3>Step 4: Install HeidiSQL</h3>
The fourth and final step to installing osTicket is installing HeidiSQL. This will act as the database for the ticketing system. 

Go back to the Google Drive with all the downloads and download HeidiSQL if it wasn't done yet. Once it's download it, open the installer and install the application. 

<p>
<img src="https://i.imgur.com/zwKaeCu.png" height="80%" width="80%" alt="36."/>
</p>

<p>
<img src="https://i.imgur.com/u1wE5BZ.png" height="80%" width="80%" alt="37."/>
</p>

In HeidiSQL, right click "Unamed" on the left side, then "Create new", then "Database."

<p>
<img src="https://i.imgur.com/pLOAM54.png" height="80%" width="80%" alt="38."/>
</p>

<p>
<img src="https://i.imgur.com/oebqiTC.png" height="80%" width="80%" alt="39."/>
</p>

<p>
<img src="https://i.imgur.com/HmQY5Mc.png" height="80%" width="80%" alt="40."/>
</p>

Once this is done in HeidiSQL, go back to the osTicket Installer and finish the installation.

<p>
<img src="https://i.imgur.com/50jaXKo.png" height="80%" width="80%" alt="41."/>
</p>

<p>
<img src="https://i.imgur.com/N8cQoR7.png" height="80%" width="80%" alt="42."/>
</p>

It should be installed with no issues. Before continuing, there are some files that need to be cleaned up. 

Delete the "setup" in the osTicket folder. Copy and paste this into Windows Explorers if there is trouble finding it: "C:\inetpub\wwwroot\osTicket\setup".

<p>
<img src="https://i.imgur.com/WOe4EJf.png" height="80%" width="80%" alt="43."/>
</p>

<p>
<img src="https://i.imgur.com/rcWIhMh.png" height="80%" width="80%" alt="43."/>
</p>

Next, go to the file "ost-config.php", right click it and select Properties. Go back to Security, Advanced,then Permissions, then allow only read and read & execute. 

<p>
<img src="https://i.imgur.com/SgfA9ex.png" height="80%" width="80%" alt="44."/>
</p>

<p>
<img src="https://i.imgur.com/G7mawZl.png" height="80%" width="80%" alt="45."/>
</p>

Congratulations! Now osTicket is installed. 

The next two tutorials will show how to configure osTicket (such creating users, administrators, etc.) and how to work to tickets. 

<p>
<img src="https://i.imgur.com/LWC2RGB.jpg" height="80%" width="80%" alt="46."/>
</p>


**REMEMBER TO DELETE YOUR RESOURCES ONCE YOU ARE DONE WITH THE LAB!**

