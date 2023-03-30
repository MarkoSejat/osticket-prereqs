  <br>
</p>
<br />


<p>
<img src="https://i.imgur.com/O7Ged9k.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
Going back to the portal homescreen, we can click on the newly created VM and clicking on it. From there we should be taken to the screen above where we will need to copy the public IP address for our newly created virtual machine. From there we will need to login into it. Since I am using a Windows desktop PC I will click on my windows search tab by my start menu and type in "Remote Desktop Connection" where I will paste the IP that we copied from the VM. After that I will be asked to login using my account name and password that we set up when we set up the VM. 
  <img src="https://i.imgur.com/8IIPKHY.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/g7KzmPn.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
  From here we will be logged into our VM where we can move onto the next step which is install/enabling Windows IIS with CGI. We can do this by going into the VM desktop that we created and clicking the search by our start menu and typing run. Once in the run app write "control" which will access our control panel and clicking "PROGRAMS".
   <img src="https://i.imgur.com/EDf5arH.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  From here You will see it says "Programs and features" and you can click "Turn Windows features on or off". From here you can scroll down to "Internet Information Service" and you can select everything that I have selected in the picture below. Make sure you turn on CGI! CGI will enable us to install PHP Manager for osTicket and its basically a back-end programming language which osTicket needs in order to work properly. 
   <img src="https://i.imgur.com/BSM74P9.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  Click "OK" and Windows should start doing its installation process giving you a "Windows completed the requested changes" message. Now its time to test if the IIS is working correctly and we can do that by opening up a brower in our VM and typing in 127.0.0.1 which is our subnet. We will know its working if we can see the following screen: 
  <img src="https://i.imgur.com/GpwBnYg.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
We can now move onto the next phase which will be installing our PHP manager. We can do this by going into the link of files I provided at the very start of this article and and accessing the file titled: PHPManagerForIIS_V1.5.0.msi
  <br>
<img src="https://i.imgur.com/3rmxiCs.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DtGHYPx.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
You can start installing the PHP manager by just pressing NEXT on all the prompts and allow for it to install. Once installed we can move onto our next step which is installing the Rewrite Module (rewrite_amd64_en-US.msi) from our set of files in the same link as before.
<img src="https://i.imgur.com/RSEXuLG.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
As before, the install is very straight forward. Just keep pressing Next until the install is complete and then we should be able to move onto our next step which is creating a directory for  C:\PHP
</p>
<p>
<img src="https://i.imgur.com/JmUoLXY.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
We can set up our PHP directory by simply going to our C: drive and creating a new folder and naming it PHP. Then we are going to download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP. 
<img src="https://i.imgur.com/fed1edj.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once we have our file downloaded we can extract everything in the .zip file by right=clicking and selecting "extract all" and selecting the C:\PHP as shown above. Once we have this done, we can move onto our next step which is downloading VC_redist.x86.exe and proceeding with the install process as normal. This file is sometimes required by PHP in order to get it to work correctly so that is why we are installing it.
<img src="https://i.imgur.com/8K0l7Dv.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once installed you should see the image above. Next we will move onto downloading MySQL 5.5.62 (mysql-5.5.62-win32.msi). When asked during installation, select typical install. Launch MySQL and select standard configuration. When you get to the password section, stop and take a look at the image below.
<img src="https://i.imgur.com/GqbXAGh.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
For the purposes of this demonstration I am going to name the username "root" and set the password as Password1
<br>
At this point, the install will be setting up a database for the MySQL to store all the data such as user names. Once the install is completed just simply click "finish" and we can move onto the next step. We can now go to our search bar near our start menu and type in IIS and then right click it and then run it as administrator. 
<img src="https://i.imgur.com/VyOnLri.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once we have the IIS open we should see the following:
<img src="https://i.imgur.com/7cDhyEC.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
We can then click Register new PHP version
<img src="https://i.imgur.com/axIDuvS.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/aN2EpQC.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Then we will browse to our C:\PHP and select the file called "php-cgi"
 
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />


<p>
We will set up our VM by clicking "Virtual Machines" from the portal homescreen or searching "Virtual Machines" in the search bar. Once we have done that we should be taken to a screen that looks like the one above and click Create. Select "Azure Virtual Machine" from the drop down menu and then you should be taken to the following screen:
    <img src="https://i.imgur.com/LumnioY.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
    <img src="https://i.imgur.com/l9fOLLs.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
  From here I set up the resource group to fall under the one that we previously created. I named mine RS-osTicket and I named my VM "vm-osticket". I also went and placed my region to be same as that of my resource group. Follow the settings that I have done including setting up an account name and password that you will be using to log into the VM. It can be anything you want for it to be just make sure that you remember it. I named mine "labuser". from there we can scroll back up top and click "REVIEW+CREATE". It should validate and then we can go on and click "CREATE". Congreatulations, we have just set up a VM in Microsoft Azure. Our next step will be logging into the VM. 
  <br>
</p>
<br />


<p>
<img src="https://i.imgur.com/O7Ged9k.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
Going back to the portal homescreen, we can click on the newly created VM and clicking on it. From there we should be taken to the screen above where we will need to copy the public IP address for our newly created virtual machine. From there we will need to login into it. Since I am using a Windows desktop PC I will click on my windows search tab by my start menu and type in "Remote Desktop Connection" where I will paste the IP that we copied from the VM. After that I will be asked to login using my account name and password that we set up when we set up the VM. 
  <img src="https://i.imgur.com/8IIPKHY.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <img src="https://i.imgur.com/g7KzmPn.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
  From here we will be logged into our VM where we can move onto the next step which is install/enabling Windows IIS with CGI. We can do this by going into the VM desktop that we created and clicking the search by our start menu and typing run. Once in the run app write "control" which will access our control panel and clicking "PROGRAMS".
   <img src="https://i.imgur.com/EDf5arH.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  From here You will see it says "Programs and features" and you can click "Turn Windows features on or off". From here you can scroll down to "Internet Information Service" and you can select everything that I have selected in the picture below. Make sure you turn on CGI! CGI will enable us to install PHP Manager for osTicket and its basically a back-end programming language which osTicket needs in order to work properly. 
   <img src="https://i.imgur.com/BSM74P9.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  Click "OK" and Windows should start doing its installation process giving you a "Windows completed the requested changes" message. Now its time to test if the IIS is working correctly and we can do that by opening up a brower in our VM and typing in 127.0.0.1 which is our subnet. We will know its working if we can see the following screen: 
  <img src="https://i.imgur.com/GpwBnYg.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
We can now move onto the next phase which will be installing our PHP manager. We can do this by going into the link of files I provided at the very start of this article and and accessing the file titled: PHPManagerForIIS_V1.5.0.msi
  <br>
<img src="https://i.imgur.com/3rmxiCs.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/DtGHYPx.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
You can start installing the PHP manager by just pressing NEXT on all the prompts and allow for it to install. Once installed we can move onto our next step which is installing the Rewrite Module (rewrite_amd64_en-US.msi) from our set of files in the same link as before.
<img src="https://i.imgur.com/RSEXuLG.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
As before, the install is very straight forward. Just keep pressing Next until the install is complete and then we should be able to move onto our next step which is creating a directory for  C:\PHP
</p>
<p>
<img src="https://i.imgur.com/JmUoLXY.jpg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
We can set up our PHP directory by simply going to our C: drive and creating a new folder and naming it PHP. Then we are going to download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP. 
<img src="https://i.imgur.com/fed1edj.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once we have our file downloaded we can extract everything in the .zip file by right=clicking and selecting "extract all" and selecting the C:\PHP as shown above. Once we have this done, we can move onto our next step which is downloading VC_redist.x86.exe and proceeding with the install process as normal. This file is sometimes required by PHP in order to get it to work correctly so that is why we are installing it.
<img src="https://i.imgur.com/8K0l7Dv.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Once installed you should see the image above. Next we will move onto downloading MySQL 5.5.62 (mysql-5.5.62-win32.msi). When asked during installation, select typical install. Launch MySQL and select standard configuration. When you get to the password section, stop and take a look at the image below.
<img src="https://i.imgur.com/GqbXAGh.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
For the purposes of this demonstration I am going to name the username "root" and set the password as Password1
<br>
At this point, the install will be setting up a database for the MySQL to store all the data such as user names. Once the install is completed just simply click "finish" and we can move onto the next step. We can now go to our search bar near our start menu and type in IIS and then right click it and then run it as administrator. 
<img src="https://i.imgur.com/VyOnLri.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/S8E20mV.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
From this point we want to go to the PHP Manager. If we click, it will take us to the next menu.
<img src="https://i.imgur.com/xWRTPLS.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
It tells us that PHP is not enabled so we would have to click "Register New PHP Version"
<img src="https://i.imgur.com/3bYVobS.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Simply just browse to the C:\PHP folder and select: php-cgi. After this I recommend going back to the main IIS menu and selecting "restart" from the right tap under where it says Manage Server. Now we are finally going to install osTicket!


</p>
<p>
<img src="https://i.imgur.com/aUrTAav.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
From our Installation files on the google drive link, we can download osTicket-v1.15.8.zip and from here we can go onto our next step. We are going to want to go to c:\inetpub\wwwroot as this is where we will be placing our "upload" folder from the osTicket zip we just downloaded. 
<img src="https://i.imgur.com/jC72zNz.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
If we look at the image above, we are now going to rename that same "upload" folder to "osTicket" and then restart IIS. 
<img src="https://i.imgur.com/puAspA5.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
Now if we go into our IIS main page and see where it says connections on the left we will see a tab. Click the vm-osticket then sites, default web site, osTicket and then click "Browse*:80 (http)" on the right under where it says browse folder. If this works you should have now successfully installed osTicket!
</p>
<br>
<img src="https://i.imgur.com/Xv4AN3k.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>

  
<br />
