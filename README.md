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

Download PHP Mananger and rewrite module from the google drive. Then open up the file in the Downloads folder and install the applications. 

<p></p>
  
![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/393fbfbe-0716-4da9-9bd3-75c768ebcd24)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/af2e6fdd-5c54-4fcd-a2dd-0fab85f43697)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/68f6d35a-67e8-4a60-92fe-74d1b7410277)

Create the directory C:\PHP

From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/25e360a3-11c2-4a13-a6c3-39ec44d96b2f)

From the Installation Files, download and install VC_redist.x86.exe.

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/249ccdf4-2055-470a-acdc-25d5b52e4448)


From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password1

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/deaaa765-93de-438b-ab37-90f342642c88)


Open IIS as an Admin

Register PHP from within IIS

Reload IIS (Open IIS, Stop and Start the server)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/072c47f6-a701-4d41-9f53-63513ccbd393)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/3d0aad0d-4c3f-48b7-b0fb-f85a8d17be9f)


<h3>Step 3: Install osTicket</h3>
The third step is to install osTicket. Go to the Google Drive mentioned previously and download the osTicket files. Once it is downloaded, open the osTicket folder. Copy the "Upload" folder. 

Open up a new Windows File Explorer Window, go to "This PC" on the left hand side, go to C:\, then "inetpub", then wwwroot. This can also be pasted in the Explorer bar "c:\inetpub\wwwroot". Paste the "Upload" folder into the wwwroot folder and rename it "osTicket."

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/63cfc96a-aca3-4140-9379-9ecebbe0d05b)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/068c1b73-7002-46c5-8609-138ec7da8c12)


Once all this is completed, open up IIS from the start menu. On the left hand side of IIS, open up the directory (it should be the virtual machine name), then go to sites, then osTicket. Once osTicket has been opened in IIS, click "Browse *:80 (http)" on the right.

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/6e2909c7-aaa2-49b0-8c69-cc2fbed44aa0)


Before going forward with the osTicket Installer, there must be some add-ons enabled first. Go back to IIS and click on "PHP Manager." Then click "Enable or disable an extension."

Right click and enable the following: 
- php_imap.dll.
- php_intl.dll.
- php_opcache.dll.

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/fe7b10a2-793f-4f8a-9e7f-a567e98de182)


Once all those are installed, switch back to the osTicket Installer and refresh it. An extension should have changed from a red x to a green check. 

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/5983ecde-be92-4c2c-a20c-89332014aa7a)


Open up Windows File Explorer and it should still be on the osTicket folder. Open up the "include" folder and scroll down to the file "ost-sampleconfig.php." Rename this file to "ost-config.php."

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/b8eee491-c68d-441c-9180-cf9af8088a84)


Once the file has been renamed, right click on the file "ost-config.php" and click on "Properties." Then go to the "Security" tab then click the "Advanced" button. Then click "Disable inheritance." 

Once this is done, add a new permission by typing "Everyone" in the box, and check "Full Control." Then click "OK" to exit out. 

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/65b581fb-11a5-4693-aec2-6f578ede0906)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/85d5834a-2037-42d1-b655-09ebd8bd822e)


Once this is done, go back to the osTicket Installer. Start to fill out the setup page until you get to the database settings. 

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/e7af411e-d9fb-4e55-8744-008b18fc01c1)


<h3>Step 4: Install HeidiSQL</h3>
The fourth and final step to installing osTicket is installing HeidiSQL. This will act as the database for the ticketing system. 

Go back to the Google Drive and download HeidiSQL. Once it's downloaded, open the installer and install the application. 

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/03cc488e-9441-4a22-bd01-e8cc0afb04b3)

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/c2afe9a5-82e1-48ab-b850-95cd4d45a210)

Create a new database in HeidiSQL called osTicket. Go back to osTicket installer setup page and fill out database settings.

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/374d7314-b211-45e8-9732-25dd9d00e7fd)

It should be installed with no issues. Before continuing, there are some files that need to be cleaned up. 

![image](https://github.com/mathew-perez/osticket-prereqs/assets/144407220/56cee33b-739c-43ca-81c0-d99d793ace78)


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

