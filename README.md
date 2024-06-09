
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>


1.) Create a Windows 10 (with 2-4 Virtual CPUs) Virtual Machine through Azure https://portal.azure.com/#view/HubsExtension/BrowseResource/resourceType/Microsoft.Compute%2FVirtualMachines. 
  - Allow it to create a new Virtual Network. 

2.) Connect to virtual machine using it's public IP address. 
</p>
<img width="1091" alt="Screenshot 2024-06-03 at 4 54 06 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/15e53c3a-2471-4aab-ba8a-f06c23fe6d44">
  - Copy IP address then paste in Remote Desktop Connection. 
<p>

</p>
<p>
<p>
<img src="https://imgur.com/Zf2jw07.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3.) Once you have connected to your virtual machine you will want to go to your control panel. From the control panel open up programs. Select, Turn Windows features on and off.

<p>
<img width="480" alt="Screenshot 2024-06-03 at 5 05 52 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/2bb99dfd-e774-4760-87ee-1843e7a9bac8">

</p>
<img width="478" alt="Screenshot 2024-06-03 at 5 06 21 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/69fd0d56-ace1-4ea1-91ef-df41cdf86cb0">

  
<p>

</p>
<p>
  
4.) Install / Enable IIS in Windows with CGI and Common HTTP Features
  - Internet Information Services -> World Wide Web Services -> Application Development Features->
    
    [X] CGI
  - Internet Information Services -> World Wide Web Services -> Common HTTP Features
    
    [X] Everything under it.
    
<img width="707" alt="Screenshot 2024-06-04 at 4 26 15 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/afa8c477-fdb4-490a-a75d-497762656ffe">

<img width="708" alt="Screenshot 2024-06-04 at 4 26 46 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/7c67f020-dc2d-4893-ac95-c361d91f43d9">
<img width="709" alt="Screenshot 2024-06-04 at 4 27 19 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/1c941fdd-7c77-4f12-a218-536a1c3ceb5f">
<img width="708" alt="Screenshot 2024-06-04 at 4 27 42 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/6819a85c-bf11-4e42-b841-0c5301fcf552">

<p>
<p>

5.) Write 127.0.0.1 in internet explorer and if this shows up then IIS has been setup. 
<p>
<img width="1390" alt="Screenshot 2024-06-04 at 4 30 37 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/43f03425-3693-4f45-ad97-2f6f5448a831">

6.) Install PHPManager (PHPManagerForIIS_V1.5.0.msi) from Installation Files folder and go through the install wizard.
<p>

<img width="496" alt="Screenshot 2024-06-04 at 4 49 23 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/fe38f65a-417d-4b86-8577-8db3690bfb6a">

7.) Install Rewrite Module (rewrite_amd64_en-US.msi) and go through the install wizard. 
<p>
<img width="488" alt="Screenshot 2024-06-04 at 4 53 18 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/0f773a64-e2fd-4205-ae2d-f662f8bcd1df">
<p>
8.) Create the directory C:\PHP: 
- Open File Explorer -> This PC -> Windows (C:) -> Create folder "PHP"
  <p>
<img width="844" alt="Screenshot 2024-06-04 at 4 57 13 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/034d6fb7-eb9e-4dec-9b31-370223316235">
<p>

9.) Install PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP. 
!! ATTENTION !!
If this appears, choose to “Keep” the file
<p>
<img width="396" alt="Screenshot 2024-06-04 at 5 00 44 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/0d4cb472-e972-4a8d-9025-cce046619eed">
<p>
<img width="351" alt="Screenshot 2024-06-04 at 5 01 06 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/d5f3288d-dcf5-4357-ad4f-c4fc156361c4">
<p>
10.) Install VC_redist.x86.exe. and go through the install wizard.
<p>
<img width="479" alt="Screenshot 2024-06-04 at 5 45 29 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/057cc93c-bdb4-40cc-b5d2-af59873a0b64">
<p>
11.) Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) and go through the install wizard choosing these options:
Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration -> Password1
<p>
<img width="212" alt="Screenshot 2024-06-04 at 5 51 34 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/cb223041-603f-4333-b160-e59287fa8148">
<p>
12.) Open IIS as an Administrator: 
<p>
<img width="814" alt="Screenshot 2024-06-04 at 5 53 32 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/77000faf-6718-440e-80c1-201889521172">
<p>
<img width="1266" alt="Screenshot 2024-06-04 at 5 55 09 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/e753ebc8-212a-42a2-b19c-f4d9bf88e800">
<p>
13.) Register PHP from within IIS by first clicking on PHP Manager. 
<p>
<img width="1262" alt="Screenshot 2024-06-04 at 7 15 16 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/56e5747f-2221-485a-9389-5e6545f1fb9f">
<p>
Click on Register new PHP version.
<p>
  
<img width="1264" alt="Screenshot 2024-06-04 at 7 16 49 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/83a53866-72b0-424e-bf74-99a1e28be99a">
<p>
  
Click on these three dots to open file explorer. 
  <p>
<img width="504" alt="Screenshot 2024-06-04 at 7 20 32 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/1ab7e53c-8177-40df-8588-9004c8676c30">
<p>
Go to this folder and click php-cgi.
<img width="1007" alt="Screenshot 2024-06-04 at 7 18 46 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/3fe72f3b-45e2-47c8-90fe-f8b32f2ce941">
<p>
Click on Restart. 
  <p>
<img width="1268" alt="Screenshot 2024-06-04 at 7 22 41 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/cef29ddf-83cf-43ce-982a-c1b586de8032">
<p>
14.) Install osTicket v1.15.8 
- Open two file explorer tabs next to each other. 
- Extract and copy (drag) "upload" folder over to "wwwroot"
<p>
<img width="1367" alt="Screenshot 2024-06-04 at 7 28 30 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/bb4b0121-7f15-42f2-8454-d830b952f119">
<p>
Rename the "upload" folder to EXACTLY "osTicket" (if it isn't exactly "osTicket" then it will not work). 
- Restart IIS again.
<p>
15.) On IIS go to Sites -> Default Web Site -> osTicket -> On the right, click “Browse *:80”
<p>
<img width="1266" alt="Screenshot 2024-06-04 at 7 51 43 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/39502f1b-74a7-44c0-8a16-84318da43c7c">
<p>
If this shows up then the lab has been executed correctly so far. Good job! 
What this is showing is that some extensions are not enabled. 
<img width="821" alt="Screenshot 2024-06-04 at 7 55 09 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/814a3062-49ef-403e-8bbb-f118e6246741">
<p>
Enable the extensions: -> Go back to IIS -> Sites -> Default -> osTicket -> Double click PHP manager -> Click "Enable or disable an extension"
<p>
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll

<p>
<img width="1263" alt="Screenshot 2024-06-04 at 7 58 03 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/fff6d304-8e04-4790-8653-49d199aeb2ec">
<img width="1261" alt="Screenshot 2024-06-04 at 7 59 00 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/4d661d9b-bdfa-4061-a33b-0987e10b0775">
<p>
Refresh the osTicket website and if it looks like this then it worked! 
<p>
<img width="822" alt="Screenshot 2024-06-04 at 8 00 05 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/15c2d4df-c393-4768-9a7c-fc65df854f94">
<p>
16.) Rename ost-sampleconfig.php to ost-config.php: 
File Explorer -> This PC -> Windows (C:) -> inetpub -> wwwroot -> osTicket -> include 
<img width="1296" alt="Screenshot 2024-06-04 at 8 06 21 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/a2e45d0b-6bce-41d2-9570-3be100eea6de">
<p>
Right click on ost-config.php and select "Properties"  
  <p>
From there click Security -> Advanced -> Disable the inheritance -> Remove all inherited permissions from this object.
<p>
Add new permissions 
<p>
<img width="763" alt="Screenshot 2024-06-04 at 8 17 39 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/15999817-47f8-46a2-a524-53bf579cbe15">
<p>
Select a principal
<p>
<img width="915" alt="Screenshot 2024-06-04 at 8 17 49 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/77f54fb6-df84-4e6d-ba56-bbcff3f83cc7">
<p>
Type "Everyone" -> Check Name -> "Ok" 
<p>
<img width="454" alt="Screenshot 2024-06-04 at 8 18 01 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/e14effcc-c47d-4458-b2d0-ee1603a0d8f7">
<p>
Check "Full Control" 
<p>
<img width="914" alt="Screenshot 2024-06-04 at 8 18 12 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/73b92fc6-68c3-41f7-b90c-ec6b55eac438">
<p>
Click "Apply" -> "Ok" 
<p>
17.) Go to osTicket browser page and refresh it. Click Continue on the osTicket browser page. Fill out the page as required except the Database Settings at the bottom of the page. 
<p>
18.) Install HeidiSQL 
  <p>
<img width="401" alt="Screenshot 2024-06-04 at 8 27 36 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/b8acbbcb-4c74-4764-b399-50a9c5744932">
<p>
Create new session
<p>
<img width="403" alt="Screenshot 2024-06-04 at 8 29 22 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/4ca1ad1c-1a13-4f6f-b1aa-9dc91b6e3797">
<p>
Make username "root" and password "Password1" 
<p>
<img width="399" alt="Screenshot 2024-06-04 at 8 30 37 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/4817f2c7-6159-4915-966f-b98d168eeac5">
<p>
  Press "Open" 
<p>
  <img width="683" alt="Screenshot 2024-06-09 at 3 30 38 PM" src="https://github.com/samparkercc/osTicket-prereqs1/assets/171518500/340accc7-6d6f-49f8-a0de-69590431a032">
<p>
  Go then go back to the osTicket browser page and under the Database Settings in the browser the username will be "root" and the password will be "Password1".
<p>
In HeidiSQL, right click Unnamed -> Create New -> Database
<p>
<img width="399" alt="Screenshot 2024-06-04 at 8 36 43 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/5ffa2e4a-4924-45c4-a0d0-9205b6574767">
<p>
Name it, "osTicket" 
<p> 
<img width="135" alt="Screenshot 2024-06-04 at 8 38 28 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/7917eedf-9ec1-43cb-b9aa-2368d3f3e2fd">
<p>
  Fill in SQL Database with, "osTicket" 
<p>
<img width="848" alt="Screenshot 2024-06-09 at 3 32 39 PM" src="https://github.com/samparkercc/osTicket-prereqs1/assets/171518500/e34b5a4c-b045-4e36-94fe-a2963abe1d3d">
<p>
  Congratulations! You've successfully setup osTicket! 
  <p>
    <img width="817" alt="Screenshot 2024-06-09 at 3 33 00 PM" src="https://github.com/samparkercc/osTicket-prereqs1/assets/171518500/f09950a3-d018-440c-80e0-f1b1b35a1d6f">
<p>
  Then for cleanup: 
  <p>
19.) Delete "setup" folder within the osTicket file
<p>
<img width="829" alt="Screenshot 2024-06-04 at 8 43 07 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/3f6804d5-794e-4598-b5cc-c331fee8e5e1">
<p>
20.) Go to ost-config.php file -> Properties -> Security -> Advanced ->  set permissions to "Read" and "Read & execute" 
<p>
<img width="761" alt="Screenshot 2024-06-04 at 8 46 14 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/5477c96e-2668-4d32-b1ba-f31b1ff872cb">
<p>
<img width="914" alt="Screenshot 2024-06-04 at 8 46 46 PM" src="https://github.com/joshmadakorcc/osticket-prereqs/assets/171518500/e59104f2-08fc-4571-9a4e-3d3906f2f1bd">
<p>
Once all of this is completed then we can login to osTicket. Congratulations and great job!
<p>
