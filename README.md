<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>
<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure account
- Installation files: https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>
<br>
</p>
<br />
Our first steps are to set up an account with Microsoft Azure. We can set up using a free-trial account. 
<img src="https://i.imgur.com/96Kqktg.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
<img src="https://i.imgur.com/daFK83r.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
The first thing we will see is our Azure Portal home screen. From here we have the freedom to do many things but for this project, we are going to start by creating a resource group. We can begin by clicking on the "resource group" icon and clicking "create" on the next screen.  
<br>
<img src="https://i.imgur.com/1TEfRp2.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
We should see the following screen. We can name our resource group "RS-osTicket" and then select our region. Make sure you remember which region you set up your resource group in. I set mine up using US West 3 in the example above. Make sure everything you do from here on out is set up for the same region.  
<br>
<img src="https://i.imgur.com/n5xzLGO.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
Our next step is going to be to set up our Virtual Machine. The virtual machine is essentially a simulation of a computer using the Azure server to let us perform tasks as if they were being done on our desktops. We will begin by clicking the "Virtual-Machines" icon in our portal home screen and then selecting "Create" from the top left and selecting "Azure Virtual Machine" 
<br>
<img src="https://i.imgur.com/WpeOrlF.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 From here we can begin our VM setup. The first thing we have to do is make sure that our resource group is one that we created. In my example it is RS-osTicket. I set my image to Windows 10 as that is the OS that I want my VM to have. I also set my security to standard and made sure that my region is the same as that of my resource group. 
<br>
<img src="https://i.imgur.com/2KcjAhN.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
Next, we want to make sure that our username and password are set up. For this lab, I just simply used the name "labuser" but you can use whatever you want. Make sure you remember your password as well. Check the box below and click Create. It should then begin to validate and you will have to click Create once more. 
<br>
<img src="https://i.imgur.com/s4c3tAQ.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
Going back to the portal home screen, we can click on the newly created VM and clicking on it. From there we should be taken to the screen above where we will need to copy the public IP address for our newly created virtual machine. From there we will need to login into it. Since I am using a Windows desktop PC I will click on my Windows search tab by my start menu and type in "Remote Desktop Connection" where I will paste the IP that we copied from the VM. After that, I will be asked to log in using my account name and password that we set up when we set up the VM.  
    <br>
  <img src="https://i.imgur.com/8IIPKHY.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/g7KzmPn.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
From here we will be logged into our VM where we can move on to the next step which is installing/enabling Windows IIS with CGI. We can do this by going into the VM desktop that we created and clicking the search by our start menu and typing run. Once in the run app write "control" which will access our control panel and click "PROGRAMS".
    <br>
  <img src="https://i.imgur.com/EDf5arH.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
    <br>
From here You will see it says "Programs and features" and you can click "Turn Windows features on or off". From here you can scroll down to "Internet Information Service" and you can select everything that I have selected in the picture below. Make sure you turn on CGI! CGI will enable us to install PHP Manager for osTicket and it's a back-end programming language that osTicket needs to work properly. 
    <br> 
  <img src="https://i.imgur.com/BSM74P9.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
    <br>
Click "OK" and Windows should start doing its installation process giving you a "Windows completed the requested changes" message. Now it's time to test if the IIS is working correctly and we can do that by opening up a browser in our VM and typing in 127.0.0.1 which is our local host/loopback address. We will know its working if we can see the following screen: 
    <br>
  <img src="https://i.imgur.com/GpwBnYg.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
We can now move on to the next phase which will be installing our PHP manager. We can do this by going into the link of files I provided at the very start of this article and accessing the file titled: PHPManagerForIIS_V1.5.0.msi 
  <br>
<img src="https://i.imgur.com/3rmxiCs.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DtGHYPx.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
You can start installing the PHP manager by just pressing NEXT on all the prompts and allowing it to install. Once installed we can move on to our next step which is installing the Rewrite Module (rewrite_amd64_en-US.msi) from our set of files in the same link as before. 
  <br>
  <img src="https://i.imgur.com/RSEXuLG.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
As before, the installation is very straightforward. Just keep pressing Next until the installation is complete and then we should be able to move on to our next step which is creating a directory for C:\PHP 
</p>
<img src="https://i.imgur.com/JmUoLXY.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  <br>
We can set up our PHP directory by simply going to our C: drive and creating a new folder and naming it PHP. Then we are going to download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP. 
  <br>
<img src="https://i.imgur.com/fed1edj.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
Once we have our file downloaded we can extract everything in the .zip file by right=clicking and selecting "extract all" and selecting the C:\PHP as shown above. Once we have this done, we can move on to our next step which is downloading VC_redist.x86.exe and proceeding with the installation process as normal. This file is sometimes required by PHP to get it to work correctly so that is why we are installing it. 
  <br>
<img src="https://i.imgur.com/8K0l7Dv.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
Once installed you should see the image above. Next, we will move on to downloading MySQL 5.5.62 (mysql-5.5.62-win32.msi). When asked during installation, select typical install. Launch MySQL and select standard configuration. When you get to the password section, stop and take a look at the image below. 
<img src="https://i.imgur.com/GqbXAGh.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
For this demonstration, I am going to name the username "root" and set the password as Password1 
<br>
At this point, the install will be setting up a database for MySQL to store all the data such as user names. Once the installation is completed just simply click "finish" and we can move on to the next step. We can now go to our search bar near our start menu and type in IIS and then right click it and then run it as administrator.  
  <br>
<img src="https://i.imgur.com/VyOnLri.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
 Once we have the IIS open we should see the following: 
  <br>
<img src="https://i.imgur.com/7cDhyEC.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
We can then click Register new PHP version 
  <br>
<img src="https://i.imgur.com/axIDuvS.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/aN2EpQC.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Then we will browse to our C:\PHP and select the file called "php-cgi"
</p>
<br />

<p>
We will set up our VM by clicking "Virtual Machines" from the portal home screen or searching "Virtual Machines" in the search bar. Once we have done that we should be taken to a screen that looks like the one above and click Create. Select "Azure Virtual Machine" from the drop-down menu and then you should be taken to the following screen:   
    <img src="https://i.imgur.com/LumnioY.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
    <img src="https://i.imgur.com/l9fOLLs.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
From here I set up the resource group to fall under the one that we previously created. I named mine RS-osTicket and I named my VM "vm-osticket". I also went and placed my region to be the same as that of my resource group. Follow the settings that I have done including setting up an account name and password that you will be using to log into the VM. It can be anything you want it to be just make sure that you remember it. I named mine "labuser". from there we can scroll back up top and click "REVIEW+CREATE". It should validate and then we can go on and click "CREATE". Congratulations, we have just set up a VM in Microsoft Azure. Our next step will be logging into the VM. 
  <br>
</p>
<br />


<p>
<img src="https://i.imgur.com/O7Ged9k.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
Going back to the portal home screen, we can click on the newly created VM and clicking on it. From there we should be taken to the screen above where we will need to copy the public IP address for our newly created virtual machine. From there we will need to login into it. Since I am using a Windows desktop PC I will click on my Windows search tab by my start menu and type in "Remote Desktop Connection" where I will paste the IP that we copied from the VM. After that, I will be asked to log in using my account name and password that we set up when we set up the VM.   
  <img src="https://i.imgur.com/8IIPKHY.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/g7KzmPn.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
From here we will be logged into our VM where we can move on to the next step which is installing/enabling Windows IIS with CGI. We can do this by going into the VM desktop that we created and clicking the search by our start menu and typing run. Once in the run app write "control" which will access our control panel and click "PROGRAMS". 
   <img src="https://i.imgur.com/EDf5arH.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
From here You will see it says "Programs and features" and you can click "Turn Windows features on or off". From here you can scroll down to "Internet Information Service" and you can select everything that I have selected in the picture below. Make sure you turn on CGI! CGI will enable us to install PHP Manager for osTicket and it's a back-end programming language that osTicket needs to work properly. 
   <img src="https://i.imgur.com/BSM74P9.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Click "OK" and Windows should start doing its installation process giving you a "Windows completed the requested changes" message. Now it's time to test if the IIS is working correctly and we can do that by opening up a browser in our VM and typing in 127.0.0.1 which is our subnet. We will know it's working if we can see the following screen: 
  <img src="https://i.imgur.com/GpwBnYg.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
We can now move on to the next phase which will be installing our PHP manager. We can do this by going into the link of files I provided at the very start of this article and accessing the file titled: PHPManagerForIIS_V1.5.0.msi 
  <br>
<img src="https://i.imgur.com/3rmxiCs.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DtGHYPx.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
You can start installing the PHP manager by just pressing NEXT on all the prompts and allowing it to install. Once installed we can move on to our next step which is installing the Rewrite Module (rewrite_amd64_en-US.msi) from our set of files in the same link as before.
<img src="https://i.imgur.com/RSEXuLG.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
As before, the installation is very straightforward. Just keep pressing Next until the installation is complete and then we should be able to move on to our next step which is creating a directory for C:\PHP
</p>
<p>
<img src="https://i.imgur.com/JmUoLXY.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
We can set up our PHP directory by simply going to our C: drive and creating a new folder and naming it PHP. Then we are going to download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP. 
<img src="https://i.imgur.com/fed1edj.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once we have our file downloaded we can extract everything in the .zip file by right=clicking and selecting "extract all" and selecting the C:\PHP as shown above. Once we have this done, we can move on to our next step which is downloading VC_redist.x86.exe and proceeding with the installation process as normal. This file is sometimes required by PHP to get it to work correctly so that is why we are installing it.
<img src="https://i.imgur.com/8K0l7Dv.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once installed you should see the image above. Next, we will move on to downloading MySQL 5.5.62 (mysql-5.5.62-win32.msi). When asked during installation, select typical install. Launch MySQL and select standard configuration. When you get to the password section, stop and take a look at the image below.
<img src="https://i.imgur.com/GqbXAGh.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
For this demonstration, I am going to name the username "root" and set the password as Password1 
<br>
Right now, the install will be setting up a database for MySQL to store all the data such as user names. Once the installation is completed just simply click "finish" and we can move on to the next step. We can now go to our search bar near our start menu and type in IIS and then right click it and then run it as administrator.
<img src="https://i.imgur.com/VyOnLri.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/S8E20mV.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
From this point, we want to go to the PHP Manager. If we click, it will take us to the next menu.
<img src="https://i.imgur.com/xWRTPLS.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
It tells us that PHP is not enabled so we would have to click "Register New PHP Version".
<img src="https://i.imgur.com/3bYVobS.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Simply just browse to the C:\PHP folder and select: php-cgi. After this, I recommend going back to the main IIS menu and selecting "restart" from the right tap under where it says Manage Server. Now we are finally going to install osTicket!


</p>
<p>
<img src="https://i.imgur.com/aUrTAav.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
 From our Installation files on the google drive link, we can download osTicket-v1.15.8.zip and from here we can go on to our next step. We are going to want to go to c:\inetpub\wwwroot as this is where we will be placing our "upload" folder from the osTicket zip we just downloaded.
<img src="https://i.imgur.com/jC72zNz.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
If we look at the image above, we are now going to rename that same "upload" folder to "osTicket" and then restart IIS.
<img src="https://i.imgur.com/puAspA5.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Now if we go into our IIS main page and see where it says connections on the left we will see a tab. Click the vm-osticket then sites, default web site, osTicket, and then click "Browse*:80 (HTTP)" on the right under where it says browse the folder. Now, osTicket has been installed!

</p>
<br>
<img src="https://i.imgur.com/Xv4AN3k.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Looking at the photo above you will notice that some of the extensions have a red X next to them because they have not been enabled yet through osTicket. That is going to be the next step to getting everything up and running. We now need to go back into our IIS.
<img src="https://i.imgur.com/1nCOB1H.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once we are back into IIS we can go back to where it says connection, go to our vm-osticket, click sites, default website, osTicket, and click on PHP Manager.
<img src="https://i.imgur.com/IkOsHEA.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
We then have to click on "Enable or disable an extension" under where it says PHP Extensions as shown above. After that make sure that the following extensions are enabled:
<br>
php_imap.dll 
<br>
Enable: php_intl.dll
<br>
Enable: php_opcache.dll
<br>
<img src="https://i.imgur.com/p0I4MwO.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
At this point, all of these should be enabled and we can go back to our browser with osTicket and refresh. 
<br>
<img src="https://i.imgur.com/p0I4MwO.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 We now have to rename ost-sampleconfig.php in our C:\inetpub\wwwroot\osTicket\include\ost-sample config.php 
<br>
<img src="https://i.imgur.com/hATzPSF.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/HOr9YEg.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/qBx1zde.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
Now "ost-sampleconfig.php" needs to be renamed to "ost-config.php" 
<br>
<img src="https://i.imgur.com/OV1Gcgo.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
Next, we are going to set permissions here so that everyone has permission to do anything to this file. This is because the actual osTicket installer that is going to run on this browser needs to be able to able to manipulate and interact with this file and we are not sure which user is going to be used to do that so we are going to just allow everyone to do it. We will do that by going to our file ost-config.php, right click > properties >security > advanced > disable inheritance. Then select "Remove all inherited permissions from this object." 

<br>
<img src="https://i.imgur.com/punabXy.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
A box should pop up and then we are going to click "Add" and then click "Select a principal" from the top and then another box should appear where we are going to write "everyone" and select "check names". Finally, press OK. 
<br>
<img src="https://i.imgur.com/IRlTOtX.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
A new window should pop up and simply just select "Full control" to give everyone control as shown in the picture above. Click Apply on the previous window and now everyone will have permissions. Now we are going to continue to set up osTicket in the browser. 
<br>
<img src="https://i.imgur.com/brsg8jQ.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Back at the osTicket browser just click continue and you should see the screen above. I set up my info as shown in the picture but I recommend you make your own. The default email can be whatever. Make sure you remember the admin info credentials as that part is very troublesome if you forget it. The next step is going to be setting up Heidi SQL which will allow us to connect to our MySQL database server that we installed earlier. This is what you could call a database client. The Heidi install file is also included with all other previous files or could be downloaded here https://www.heidisql.com/installers/HeidiSQL_12.3.0.6589_Setup.exe 
<br>
<img src="https://i.imgur.com/tisUgMa.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 Once the Heidi file is installed you should see the image above. 
<br>
<img src="https://i.imgur.com/gHm6Z6m.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 Now that Heidi is installed we can click "New" and then we will see our previous MySQL user appear that we named "root". Now, all we have to do is type in the password which in my example is just Password1 and we now have our connection. 

<br>
<img src="https://i.imgur.com/uHdikCM.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/XdS2RpN.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 Now once again if we go back to our browser window with osTicket and we scroll down to the bottom, it asks us for our MySQL database info under "Database settings". Don't do anything there yet. Just go back into HeidiSQL and right-click "unnamed" > Create new > Database 
<br>
<img src="https://i.imgur.com/EBG2r2j.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 Now, returning to our browser with our database settings we can go on and fill everything out with the info above and click Install Now. It is going to say "doing stuff" as it installs and now osTicket should up set up. 
<br>
<img src="https://i.imgur.com/Mp2jsim.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 Congratulations! We are not out of the woods just yet! The last step we have to do is clean up and test. We can begin to clean up by deleting C:\inetpub\wwwroot\osTicket\setup 
<br>
<img src="https://i.imgur.com/pN0u43z.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
<img src="https://i.imgur.com/0LRzi0h.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<br>
 You can go ahead and delete the setup folder and then we can go back to the "include" folder and revisit the "ost-config.php" file and then just right-click> properties > security > Advanced > click where it says everyone > changes to read & wrote and read as shown in the photo above. 
<br>
Now the initial set-up of osTicket is complete!  
<br>
 We can now test if everything is working by going to the following URLs: 
<br>
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
<br>
End Users osTicket URL: http://localhost/osTicket/
<br>
For our purposes will be trying to use the helpdesk admin URL which is the first one. So we can simply copy and paste http://localhost/osTicket/scp/login.php into our browser and login with our admin credentials.  
<br>
<img src="https://i.imgur.com/0BZ7Cm1.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/uRKUFN7.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Check to see if your login works. If it does, the following screen should appear as shown in the photos above and now osTicket is finally up and running! This concludes this portion of this project!




  
<br />
