<h1>Install Windows 10&Join PC To domain,RSAT tool,Server Manager</h1>

 

<h2>Description</h2>
This lab focused on joining a Windows 10 workstation to an Active Directory domain to enable centralized management and authentication. Using the Remote Server Administration Tools (RSAT) and Server Manager, the workstation was configured to connect to the domain and inherit policies from the Domain Controller. This configuration ensures the workstation operates within the domain’s security framework, allowing for consistent policy application, streamlined resource access, and efficient administrative control.
<br />


<h2>Utilities Used</h2>

- <b>Windows Server 2016</b> 
- <b>Windows 10</b>
- <b>Active Directory Users and Computers</b>
- <b>System Properties</b>
- <b>Remote Server Administration Tools</b>
- <b>Server Manager</b>
- <b>Active Directory Domain Services</b>
- <b>DNS Services</b>
- <b>Command Prompt</b>

<h2>Environments Used </h2>

- <b>Windows Server 2016</b> 
- <b>VirtualBox</b>
- <b>Windows 10</b>
<h2>Walk-through:</h2>

<b>Step 1: Download the Windows 10 ISO file</b>

- The Windows 10 ISO file is the installation image of the operating system, allowing you to install Windows 10 on a virtual machine or physical hardware. Microsoft provides official ISO files that can be used for evaluation or setup purposes.

- Navigate to the official Microsoft Windows 10 download page. Select Windows 10 ISO download option.
Make sure you choose the correct edition and language for your needs.
<p align="center">
<img src="https://i.imgur.com/FRJtfom.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
 
 
  <br/>

<b>Step 2: Create a new virtual machine and plug in the Windows 10 ISO file </b>
- After downloading VirtualBox, open up the application and you should see the same window as the one directly below.
- Click on “New” to add our Windows 10 image.
 <p align="center">
<img src="https://i.imgur.com/EMGzVr5.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">

- For the name of the VM, enter “RRWindows10Lab”. Leave the default folder as is.
- For the “ISO image” find the location in which you downloads was saved and select the download file for the Windows 2016 server.
- Click “Continue”
<p align="center">
<img src="https://i.imgur.com/YgfUCh2.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">

 - Use the recommended amount of RAM if your device has enough memory space for you to do so. 
<p align="center">
<img src="https://i.imgur.com/pdt64zS.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
 
 - Click "Create"
<p align="center">
<img src="https://i.imgur.com/AmZwxUz.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
 
 - Click "Continue"
<p align="center">
<img src="https://i.imgur.com/eNFUuCs.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">

 - Click "Continue"
<p align="center">
<img src="https://i.imgur.com/eilxG2z.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">

 - Click "Continue"
<p align="center">
<img src="https://i.imgur.com/woEsv09.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
 <br/>

<b>Step 3: Let’s start things up and setup Windows </b>

- Select "RRWindows10Lab" and click “Start”. 
<p align="center">
<img src="https://i.imgur.com/9vpr7wt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- After clicking “Start”. A window comes up in order to select the file in which operating system you want to choose from. Choose the Windows 10 ISO file we have downloaded for this project and click "Start".
<p align="center">
<img src="https://i.imgur.com/kpAqzY6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- When the VM starts up you will see the Windows 10 installation window. If you are doing this project and you live outside the United States, choose the appropriate location settings for you.
- Click “Next”
<p align="center">
<img src="https://i.imgur.com/savMVgT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click “Install” then on the next screen, click "I don't have a product key".
<p align="center">
<img src="https://i.imgur.com/ahC0Phm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Next, select “Windows 10 Pro” when asked which operating system you want to install, then click "Next".
<p align="center">
<img src="https://i.imgur.com/F1WWMDZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Accept the terms and agreements and click “Next”
<p align="center">
<img src="https://i.imgur.com/PIjpaDY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

<p align="center">
 [The Windows OS installation will take up approximately 10GB. If you are getting a message in regards to the required space then you will have to start the lab all over again and increase the virtual hard drive space so that the installation can properly take place.]
<p align="center">

- On the next window, click on “Custom: Install Windows only (advanced)”
<p align="center">
<img src="https://i.imgur.com/lRj6lzI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Then, Click “Next” and the installation will take place.
<p align="center">
<img src="https://i.imgur.com/z4FMEHY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<p align="center">
<img src="https://i.imgur.com/WvxrlTG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

<b>Step 4: Lets create a static IP on our Server 2016 VM </b>

- While the installation is taking place, we will create a static IP on the Server 2016 VM so we have one constant IP address for the lab environment.
- Log into your Server 2016 WM.
- Once logged in, type in "Control Panel" in the Windows search bar and open it.
<p align="center">
<img src="https://i.imgur.com/WSjEwuX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on "view network status and tasks" under the Network and Internet section.
<p align="center">
<img src="https://i.imgur.com/FvlrUlN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on "Change adapter settings" on the left-hand side of the window.
<p align="center">
<img src="https://i.imgur.com/CCsLkpP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on "Ethernet".
- Then, click on "Properties" on the pop-up window.
<p align="center">
<img src="https://i.imgur.com/0oBykIW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- On the Ethernet Properties window, double-click on "Internet Protocol Version 4 (TCP/IPv4).
- Next, on the Internet Protocol Version 4 (TCP/IPv4) properties window, select the "Use the following IP address:" option.
- For the IP address, type in "10.1.10.2", click in the Subnet Mask section then the Subnet Mask will then fill itself out with "255.0.0.0" automatically. For the Default Gateway, we will type in "10.1.10.1"
- Finally, leave the Use the following DNS server addresses:" option selected. In the "Preferred DNS server:" section we will type in "10.1.10.2". For the "Alternate DNS Server:" we will type in "10.1.10.1".
- Click "OK" on all pop-up windows.
<p align="center">
<img src="https://i.imgur.com/oWDustZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- At the top of the VM screen, click on "Devices", hover over Network to the click on "Network settings".
<p align="center">
<img src="https://i.imgur.com/2RemRYN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on the "Attached to:" drop-down box and switch it from "NAT" to "Host-only Adapter"
- Click "OK"
<p align="center">
<img src="https://i.imgur.com/MiHAWf2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

Now, we have created our static IP for our labbing environment and do not have to worry about the IP address changing on us until we do it manually.

- Once installed, it'll ask you to select which country you reside in, for myself I will choose United States.
- Click "Yes"
<p align="center">
<img src="https://i.imgur.com/tUqsrlr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Then it'll ask if you want to add another keyboard layout, I will continue with US but do what works best for you.
- Click "Yes"
<p align="center">
<img src="https://i.imgur.com/B7vx0nR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Select "Set up for personal use" when you arrive on the window where you are asked how you would like to set up Virtual Machine.
- Click "Next"
<p align="center">
<img src="https://i.imgur.com/0VoJSat.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- On the next window, guide your cursor to the bottome left of the screen and click "Offline account".
<p align="center">
<img src="https://i.imgur.com/sSPphms.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- At the bottom left of the window, click on "Limited experience".
<p align="center">
<img src="https://i.imgur.com/EZ9as7n.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- For the account name, type in "User". This account will adminstrator capabilites.
<p align="center">
<img src="https://i.imgur.com/ioPy2Bn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- For the password, make it something that you will remember, in my case I am making the password "Password123!". If you decide to use a different password, make sure you save the password on a clipboard/notes because you will be working out of this lab throughout the project series.
- Hit "Next"
<p align="center">
<img src="https://i.imgur.com/EGNkZnm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
Finally, the Windows OS will take a few minutes to finish the installation and once that is done you will be able to use Windows 10!
<br/>
 
 <b>Step 4: Create a password for the User</b>

- When finally logged on, click on "File Explorer' at the bottom of the screen on the Task Bar.
<p align="center">
<img src="https://i.imgur.com/h2v4mnv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- After opening File Explorer, go to the left-hand side and right-click "This PC" and click on "Manage".
<p align="center">
<img src="https://i.imgur.com/K9keZfI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

<br/>

- Under the Computer Management window that we just opened, guide your cursor to the left-hand side and click the dropdown box next to "Local Users and Groups".
- Click on "Users".
- Then, right-click on administrators and you want to click on "Properties".
<p align="center">
<img src="https://i.imgur.com/qOfcXPB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Next, we will uncheck the box for "Account is disabled".
- Keep the "Password never expires" checked.
- Then click on "Apply".
<p align="center">
<img src="https://i.imgur.com/e8LVumI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Back on the Computer Management window, right-click on administrator again except this time we will be clicking on "Set Password".
<p align="center">
<img src="https://i.imgur.com/UD5w5AN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on "Proceed".
<p align="center">
<img src="https://i.imgur.com/V7wBq6t.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- In the "New password" box, we will use the same password, Password123!" we used for the "User" account which we are currenly on.
- Press on "OK"
- Press "OK" again to set the password.
<p align="center">
<img src="https://i.imgur.com/5R7RTS2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>
 
- Close out of all windows and go to the bottom left corner of the screen and right-click the Windows Start button.
- Hover over "shut down or sign out" and click on "Sign out"
<p align="center">
<img src="https://i.imgur.com/zLmxz50.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- Now, we want to log into the Administrator account using the password we have set for it which is "Password123!".
<p align="center">
<img src="https://i.imgur.com/kNaai9c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- Go to the left-hand side and right-click "This PC" and click on "Manage".
<p align="center">
<img src="https://i.imgur.com/q967Go0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- Guide your cursor to the left-hand side and click the dropdown box next to "Local Users and Groups".
- Click on "Users".
- Then, right-click on Users and you want to click on "Delete".
<p align="center">
<img src="https://i.imgur.com/8KCCfJW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- When a window pops up asking if you are sure you want to delete the "User" account, click "Yes".
<p align="center">
<img src="https://i.imgur.com/8KCCfJW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- Another window will come up letting you know you are about to delete an administrator account and to make sure you have another one set up before deleting, which we do, so will click on "OK".
[Now, there is only one administrator account on the Windows10Lab VM, named "Administrator]
<p align="center">
<img src="https://i.imgur.com/vajwLqi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

<p align="center">
[Now, there is only one administrator account on the Windows10Lab VM, named "Administrator"]
<p align="center">
 <br/>
 
<b>Step 5: Review</b>

- On the home screen search bar, type in programs.
- Click on "Add and removes programs" at the top of the panel
<p align="center">
<img src="https://i.imgur.com/QIctx37.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- Under the "Apps & features" section, click on "Optional features".
<p align="center">
<img src="https://i.imgur.com/2ojeb5J.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- Click the first option on the settings window, "Add a feature".
<p align="center">
<img src="https://i.imgur.com/R7lP1Yt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

- While on the Add a features window, check the box on ALL of the features I have pictures below.
- Once that is done, click on "Install".
<p align="center">
<img src="https://i.imgur.com/0Qpv5qO.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/5ZFwLgt.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/H21ajDf.png" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/aU4zsXR.png" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
<br/>

- Once installed we want to restart our computer so our new features work properly.
- Right-click the start button on the Windows 10 homescreen.
- Hover over to "Shut down or sign out" and click on "Restart".
<p align="center">
<img src="https://i.imgur.com/3qVdMlq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>
 
<b>Step 6: Add our Windows 10 VM to our Domain</b>

- Once the features are downloaded, log back into Administrator on the Windows 10 VM. While loggin in, we will also be opening our Server 2016 VM and logging in the Administrator on that VM.
- We will need the IP address of our domain so we can add our Windows 10 account to the domain. Earlier, we created an static IP address for the domain to "10.1.10.2" but if you happen to not being able to recall that, then you can open up the command script and type in "ipconfig" and press enter.
<p align="center">
<img src="https://i.imgur.com/hmTcWGW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">

- Next we will rename our Windows 10 computer to "Desktop1". Go to "File Explorer" at the bottom of the home screen at the task bar.
 <p align="center">
<img src="https://i.imgur.com/wKzueiy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
 <p align="center">
<br/>

- Then, guide your cursor over to left panel of the window to "This PC" and click on "Properties".
<p align="center">
<img src="https://i.imgur.com/LECDpvZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
<br/>

- Click on "Rename this PC" on the "About" page about your computer.
<p align="center">
<img src="https://i.imgur.com/HXrDCwZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
<br/>

- Under where it states the current name of the PC, there is a box to type in the new name we want for the PC, we will be doing "Desktop1". 
<p align="center">
<img src="https://i.imgur.com/wekmJdb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
<br/>

<p align="center">
After following these steps, it will ask you to restart the PC in order to apply the name change we just did. After done restarting, your PC should officially be renamed "Desktop1"!

If you were to try to ping the domain with our Windows 10 PC, it would be unable to do so. So first what we will have to do is create a static IP address for our Windows 10 PC.

- After the PC restarts, type in "Control Panel" in the Windows search bar and open it.
<p align="center">
<img src="https://i.imgur.com/WSjEwuX.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on "view network status and tasks" under the Network and Internet section.
<p align="center">
<img src="https://i.imgur.com/FvlrUlN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on "Change adapter settings" on the left-hand side of the window.
<p align="center">
<img src="https://i.imgur.com/CCsLkpP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on "Ethernet".
- Then, click on "Properties" on the pop-up window.
<p align="center">
<img src="https://i.imgur.com/0oBykIW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- On the Ethernet Properties window, double-click on "Internet Protocol Version 4 (TCP/IPv4).
- Next, on the Internet Protocol Version 4 (TCP/IPv4) properties window, select the "Use the following IP address:" option.
- For the IP address, type in "10.1.10.3", click in the Subnet Mask section then the Subnet Mask will then fill itself out with "255.0.0.0" automatically. For the Default Gateway, we will type in "10.1.10.1"
- Finally, leave the Use the following DNS server addresses:" option selected. In the "Preferred DNS server:" section we will type in "10.1.10.2". For the "Alternate DNS Server:" we will type in "10.1.10.1".
- Click "OK" on all pop-up windows.
<p align="center">
<img src="https://i.imgur.com/eJ8PPw4.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">
<br/>

<p align="center">
Still, we will not be able to ping our domain so there will be a few more steps to accomplish that task.
<br/>
 
- At the top of the VM screen, click on "Devices", hover over Network to the click on "Network settings".
<p align="center">
<img src="https://i.imgur.com/ikX6fm6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

- Click on the "Attached to:" drop-down box and switch it from "NAT" to "Host-only Adapter"
- Click "OK"
<p align="center">
<img src="https://i.imgur.com/vSfRzuw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">

<b>Step 7: Test Command on the Command line</b>

- There may come a time when you will have to use the command line to verify a user’s account and Important metadata about the server.
- In the search bar on the home screen, type in "command" to open up the command prompt.
 <p align="center">
<img src="https://i.imgur.com/A1Wvm6i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- On the command line enter the following: "ipconfig /all"
- Press Enter to run the command

<p align="center">
<img src="https://i.imgur.com/N2Orifw.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- The following command "net user helpdesk /domain" will bring up more data in regards to the users in the active directory. Using this command line will bring our helpdesk user account and see info in regards to it.
- This command is extremely useful to quickly get information in regards to a user’s account info and what things they have access to.

 <p align="center">
<img src="https://i.imgur.com/oN04STA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p align="center">
<b>Finally, an Active Directory User account has been created and special privileges were assigned to it to be able to perform certain tasks and being apart of various organizations.</b>
