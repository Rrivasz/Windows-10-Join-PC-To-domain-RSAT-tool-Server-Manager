<h1>Windows-10-Join-PC-To-domain-RSAT-tool-Server-Manager</h1>

 

<h2>Description</h2>
This lab focused on creating a new user account in Active Directory on a Windows Server 2016 environment. Using the “Copy” function in Active Directory Users and Computers, the new “helpdesk” account was configured to inherit the same permissions and group memberships as the Administrator account. Command-line tools such as ipconfig /all and net user /domain were then used to verify network details and confirm account settings. This process demonstrates essential skills in user provisioning, permissions management, and account verification
<br />


<h2>Utilities Used</h2>

- <b>Windows Server 2016</b> 
- <b>Server Manager</b>
- <b>Active Directory Users and Computers</b>
- <b>Command Prompt</b>
- <b>Group Memberships</b>

<h2>Environments Used </h2>

- <b>Windows Server 2016</b> 
- <b>VirtualBox</b> 
<h2>Walk-through:</h2>

<b>Step 1: Login and Open Server Manager</b>

- Login into the Windows server through VirtualBox.

- Open up Server Manager and under the “Tools” tab select the “Active Directory Users and Computers”. We will create an Active Directory User and assign this user with a permissions to be able to access certain files within an organization <br/>
<p align="center">
<img src="https://i.imgur.com/TAvUsKx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
 
 
  <br/>

<b>Step 2: Copying Administrator Permissions</b>
- Under the Active Directory Users and Computers, select “Users”. For the user we will be creating will assumed the same permission policies as the administrator.
- Click on “Administrator” and right click to bring up the menu. Click “Copy” to bring up the user properties.
 <p align="center">
<img src="https://i.imgur.com/9d3ZR9s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p align="center">
 
 <br/>

<b>Step 3: User Account</b>

- The user creation menu will open up, where you will enter the user information. For the first name and logon name, enter “helpdesk” and click next.
<p align="center">
<img src="https://i.imgur.com/Qj0BOl0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/><p align="center">
<p align="center">


<br/>
 
 <b>Step 4: Create a password for the User</b>

- Choose a password for the new user. For the project, I recommend you use the same password as the one you made for the Windows server login.
- Click “Next”
 <p align="center">
<img src="https://i.imgur.com/PJiLWku.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<br/>
 
<b>Step 5: Review</b>


- Review everything and click “Finish” to complete the user creation.
 <p align="center">
<img src="https://i.imgur.com/SOVsttv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<br/>


<b>Step 6: Verify User Account</b>

- Under the users directory you should see the user “helpdesk” account that we just created. Under the helpdesk user properties you will see all the things that the user has access to. You can see that “helpdesk” has the same membership access as the system administrator.

<p align="center">
<img src="https://i.imgur.com/3KamUMi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


- Click “OK”
 <p align="center">
<img src="https://i.imgur.com/8aHZjED.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


<br/>

<p align="center">
Congratulations we just created our first Active Directory user account and assigned it administrative permissions and memberships!

<br/>

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
