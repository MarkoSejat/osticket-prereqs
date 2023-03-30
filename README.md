<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. For demonstration purposes, I will be setting this ticketing system on a virtual machine using Microsoft Azure. A VM is basically a simulation of a computer using the microsoft Azure network and anything that we do in the VM will not be carried over to our own desktop so dont worry about messing up. Lets have fun and get into it! <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Account 
- osTicket Installation Files (https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) 

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/OEp7NIW.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first thing we will need to do is set up a Microsoft Azure account. You can start off with a free trial account and then just delete all the contents of the resource group (which I'll explain later) so you do not get charged. You can set up the account by going on Google and just searching for Micosoft Azure and following the straight forward sign-up steps. Once your account has been set up you will be directed to the Azure Portal which looks like this:
  <img src="https://i.imgur.com/dCrPElO.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
  From here we will be able to control everything and create our virtual machine which from here on out we will just refer to as "VM" for short. The first step will be creating a "resource group" in which all our VM files will be stored in. To do this, we click on the resource group icon on top and then click "create". 
    <img src="https://i.imgur.com/CJftoTs.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
  <br>
  Once you have done the previous step, go on and name your resource group whatever you want. I named mine "RS-osTicket". For the region group I selected West US 3. You always want to make sure that all your contents for the VM are in the same region when setting up VM networks so always keep this in mind. Go on and click "REVIEW+CREATE" on the bottom. It should say "Validating" and once it does just go on and click "CREATE" and our resource group is now created. Our next step is to create the VM iteself. 
</p>
<br />

<p>
<img src="https://i.imgur.com/g6D589K.jpg" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
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
</p>
<p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
