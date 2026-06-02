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

- Windows 11</b> (21H2)

<h2>List of Prerequisites</h2>
- Create a VM with specifications to house AD system in Microsoft Azure
- Download and extract files from the provided OS ticket file pack
- Enable information services
- Install the PHP file and rewrite module
- Install MySQL and set up user credentials and C++redistributable 
- configure permissions and install OS ticket

<h2>Installation Steps</h2>


<p>
<img width="1920" height="1032" alt="Screenshot 2026-06-01 151736" src="https://github.com/user-attachments/assets/5e5cd95f-a52d-4d2e-b1e0-6a74fbc6661c" />


</p>
<p>An Azure region is the location of the datacenter where my VM runs. 
Here I set up the VM in Azure. I added it to a resource group and gave the VM a name. I also used US East 2 region. Choosing the right region helps with speed, cost, and keeping services available if a problem happens.
</p>
<br />
<p>

<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/f2f2178f-57ea-4fc9-9cd3-a178430c5546" />
Here is where I gave the VM a username and password. These are very important as they allow me to successfully login to the VM using port 3389 RDP (Remote Desktop Protocol). Remote Desktop Protocol is important because it allows the helpdesk to remotely access an endpoint without being in person.


<img width="1920" height="1032" alt="Screenshot 2026-06-01 151909" src="https://github.com/user-attachments/assets/2d55fe10-f9d0-424f-86c7-ff83d78ce0c6" />
Here I select the operation system (os) disk size and image. The disk image is important in Azure VM deployment because it acts as the template (operating system + setup) used to quickly create a new virtual machine. A standard HDD is important because it provides a low-cost storage option for the VM’s disk when high performance isn’t required. I then select to delete when VM is deleted. This is to help avoid extra storage charges and 
keeps the environment clean. I delete the disk with the VM so I don’t pay for something I'm no longer using.


<img width="1920" height="1032" alt="Screenshot 2026-06-01 151930" src="https://github.com/user-attachments/assets/18310723-385c-4637-b955-c76831f528ec" />
Here I select the VNet and subnet so the VM can communicate on the network, assign a public IP for remote access, and choose to delete the public IP and NIC with the VM to avoid leaving unused resources and extra costs. Virtual Network (VNet) is the VM's network. It allows the VM to communicate with other Azure resources and systems, similar to how a home Wi-Fi network connects devices.
Subnet: This is a smaller section inside the VNet that helps organize and control traffic between resources.
Public IP Address: This gives the VM an address that can be reached from the internet, allowing remote access such as RDP port 3389.
Delete Public IP and NIC when VM is deleted: The NIC (Network Interface Card) is the VM's network adapter. Selecting these options ensures that when the VM is deleted, its public IP and network adapter are also removed, preventing unused resources from remaining in Azure and generating unnecessary costs.


<img width="1920" height="1032" alt="Screenshot 2026-06-01 152136" src="https://github.com/user-attachments/assets/b6782bba-1995-4e4f-ab3c-d25979f8f698" />
The Review + Create step is important because it lets me verify all VM settings before deployment, helping prevent configuration mistakes that could affect performance, security, or cost. It also shows the estimated pricing so I can confirm the VM meets the project's requirements and budget before creating it.


<h2>Ways To Connect to Windows VM:</h2> 
<img width="403" height="239" alt="RDP" src="https://github.com/user-attachments/assets/9e983087-37bc-44f0-968c-553baa04b0c4" />

This makes accessing a computer easy by using remote desktop protocol (RDP) port 3389. 
To gain access the public IP address is used along with the VM Admin username and password. 


<img width="1920" height="1032" alt="image" src="https://github.com/user-attachments/assets/08f087cb-bbda-4347-a5c7-a757b3a27f7f" />
The second option is using Azure's Baston. Bastion can deploy a windows VM but typing the VM Admin username and password for access.

<p></p>

<img width="1920" height="1080" alt="OsTicket Download Zip File" src="https://github.com/user-attachments/assets/e3e254ca-3ba0-4f41-ad68-c3b41cbab34b" />
Once logged into the VM I then download.
<img width="1920" height="1080" alt="OsTicket Extract File" src="https://github.com/user-attachments/assets/fd12f401-a469-42ac-b8d9-e0a03ca9d2a3" />
I unzip the OsTicket file. I also put files in this folder to install osTicket and some of the dependencies. 

<img width="1920" height="1032" alt="Screenshot 2026-06-01 170200" src="https://github.com/user-attachments/assets/eca35c9b-6047-43ae-9bca-40d93062c0a7" />
I then go to the control panel then click windows features on or off on the upper left side of screen.

<img width="1920" height="1032" alt="Screenshot 2026-06-01 170618" src="https://github.com/user-attachments/assets/a2995fd9-fa32-4bce-863e-c0820300654c" />
I then scroll down to world wide web services. Then click CGI. IIS provides the web server that hosts the osTicket website, while CGI allows IIS to process PHP scripts required by osTicket.
<img width="1920" height="1080" alt="Screenshot 2026-06-01 170825" src="https://github.com/user-attachments/assets/6162e921-bd26-4f6e-84f5-4b13d7799df9" />
A search is created to for the files. 

<img width="1599" height="881" alt="image" src="https://github.com/user-attachments/assets/127d499d-16b5-4059-a618-13be483f7b5d" />
I then click the PHP Manager file. PHP Manager simplifies configuring and managing PHP settings within IIS so osTicket can run properly.

<img width="1587" height="868" alt="image" src="https://github.com/user-attachments/assets/ecb5eb93-7ff9-4049-b3d3-6d24570847f2" />
I then click the rewrite file and install it. The Rewrite Module allows IIS to handle friendly URLs and web requests used by osTicket.
<img width="1547" height="880" alt="image" src="https://github.com/user-attachments/assets/45462cb3-5b47-4bdd-af86-ba71819cca44" />
Heres the install working.

<img width="1611" height="876" alt="image" src="https://github.com/user-attachments/assets/2a505b2a-48c2-427c-81f3-6e35348d1447" />
I then click on file explorer. 
<img width="1587" height="880" alt="image" src="https://github.com/user-attachments/assets/d1fd3669-1c18-4abd-95c9-4afa65ec63d1" />
I then head to C drive to create PHP file. This folder stores the PHP installation files that osTicket relies on to execute PHP code.
<img width="1592" height="725" alt="image" src="https://github.com/user-attachments/assets/9b6a3e13-32eb-4522-beea-ea8512cc8731" />
<img width="1583" height="871" alt="image" src="https://github.com/user-attachments/assets/a4044fb9-223b-421a-b6c9-c8255322a7c0" />
I then extract PHP 7.3.8 into C:\PHP. PHP is the scripting language that runs osTicket's application logic and web pages.

<img width="1597" height="882" alt="image" src="https://github.com/user-attachments/assets/2284faf1-792e-4bee-8273-6cfeca72b82d" />
<img width="1602" height="883" alt="image" src="https://github.com/user-attachments/assets/4dfcd52d-e0ab-4b02-9c29-5aea821a3467" />
I then install VC_redist.x86.exe andMySQL 5.5.62. The Visual C++ Redistributable provides required runtime libraries that PHP needs to function correctly.
MySQL serves as the backend database where osTicket stores tickets, users, departments, and system settings.

<img width="1591" height="879" alt="image" src="https://github.com/user-attachments/assets/c46e6253-2997-4071-8bdb-cb83dbb9b10d" />
<img width="1593" height="877" alt="image" src="https://github.com/user-attachments/assets/f7ea6b5c-7c3f-4110-951b-aad5eb2a9106" />
I then configue MySQL Server. Then I configure MySQL with root account.
Creating the root account establishes administrative access needed to create and manage the osTicket database.

<img width="1598" height="880" alt="image" src="https://github.com/user-attachments/assets/f6e290f6-f0e6-45b2-a2f2-9386aa3a0032" />
I then click start and open IIS as Administrator. Administrative privileges are required to modify web server settings and register PHP.

<img width="1587" height="874" alt="image" src="https://github.com/user-attachments/assets/3c798970-9c11-4e4a-8ad2-1a8edf056986" />
<img width="1586" height="873" alt="image" src="https://github.com/user-attachments/assets/b6f7bbee-ca41-427c-91d8-a5e527cf357e" />
I then register PHP in IIS. Registering php-cgi.exe connects PHP to IIS so PHP files can be processed and displayed in the browser. Then I restart IIS by clicking stop then start.
Restarting IIS applies the PHP configuration changes and ensures the web server loads them correctly.

<img width="1590" height="877" alt="image" src="https://github.com/user-attachments/assets/dab4a823-8c52-4a55-a415-27b1c51ec658" />
<img width="1586" height="870" alt="image" src="https://github.com/user-attachments/assets/a195a91d-52aa-40ac-8b5f-0d9a06d9c3df" />
<img width="1592" height="871" alt="image" src="https://github.com/user-attachments/assets/67a5ee75-a52b-4eef-b6c1-056aad887055" />
Then I install osTicket files by extract all. Copying the osTicket files places the application on the web server so it can be accessed by users.
Then I rename the upload folder to osTicket. Renaming the upload folder creates a cleaner and more recognizable URL for accessing the helpdesk.
Then I copy the upload folder into c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, Rename upload file to osTicket.

<img width="1597" height="874" alt="image" src="https://github.com/user-attachments/assets/2d5ffd55-69b1-431c-a379-e26af4cecce2" />
Restart IIS again by clicking osticket vm in IIS (stop then start). Restarting IIS ensures the newly added osTicket application is recognized by the web server

<img width="1583" height="871" alt="image" src="https://github.com/user-attachments/assets/016c1959-bf43-4384-b0fd-64974c0ea7e9" />
While inside IIS I then go to sites then default website then osTicket. Navigate to the right then click Browse :80.

<img width="1587" height="876" alt="image" src="https://github.com/user-attachments/assets/99333029-416c-4344-85d9-b77730ad979b" />
Now see the osTicket site. Opening the site verifies that the web server and osTicket files are configured correctly.

<img width="1654" height="889" alt="image" src="https://github.com/user-attachments/assets/2a181fad-58bd-4921-8088-d1e7f417436c" />
<img width="1653" height="887" alt="image" src="https://github.com/user-attachments/assets/ceec861e-9c2f-4b4c-a32e-fbf47cf2e134" />
<img width="1660" height="884" alt="image" src="https://github.com/user-attachments/assets/1d3bd933-71e8-4d5e-84fb-ca9ee56c9a02" />
Back to IIS I click sites then default then osTicket. By double-click PHP Manager then Click “Enable or disable an extension”.
I then enable php_imap.dllEnable, php_intl.dllEnable, php_opcache.dll. IMAP support allows osTicket to retrieve and convert incoming emails into support tickets.
By enable php_intl.dll the Internationalization extension improves language, date, and character handling within osTicket.
Enable php_opcache.dll OPcache improves performance by caching PHP scripts and reducing processing time.
Refresh the osTicket site in your browser and observe the changes. Refreshing confirms the required PHP extensions are successfully enabled and functioning.

<img width="1659" height="890" alt="image" src="https://github.com/user-attachments/assets/a45a228c-204e-4abd-a89f-1eaa6d979eb3" />
 Go to File explorer and click C drive then to inetpub then wwwroot to osTicket to include and rename sampleconfig.php to config.php
This creates the active configuration file where osTicket stores its system settings.

<img width="1654" height="882" alt="image" src="https://github.com/user-attachments/assets/87228e8e-d484-4fca-8335-65feb2cc6e81" />
Then assign permissions to ost-config.php. Right click ost-config.php file then select properites then click security tab then click advanced

<img width="1656" height="889" alt="image" src="https://github.com/user-attachments/assets/06465ca6-7b15-4d69-8734-927d372aed83" />
<img width="1653" height="883" alt="image" src="https://github.com/user-attachments/assets/99b2b6a6-6114-4f6c-a19d-e0021cd5a852" />
Click disable inheritance then Remove All. Removing inheritance strengthens security by limiting who can access the configuration file.  

<img width="1662" height="881" alt="image" src="https://github.com/user-attachments/assets/5d2ece10-c26e-417f-ad27-93b0ef0cc40e" />
<img width="844" height="546" alt="image" src="https://github.com/user-attachments/assets/836c7f4c-adc3-4b91-9833-4ca64239bf75" />
Then add new permissions everyone to all in ost-config.php. Click Add then select principle then type Everyone. Click ok then click full control then click apply.
This gives temporary permissions to allow the web installer to write configuration settings during setup.

<img width="966" height="814" alt="image" src="https://github.com/user-attachments/assets/d5f6dba6-997a-42b7-99d3-150512454382" />
Continue setting up the osTicket in the browser and click Continue.
Configure Helpdesk Name and Email.	This establishes the helpdesk identity and defines where customer communications are received.
Then web installer guides the final configuration of the helpdesk environment.

<img width="809" height="816" alt="image" src="https://github.com/user-attachments/assets/63937439-3a09-4fb6-8111-5666404d6ae9" />
<img width="552" height="427" alt="image" src="https://github.com/user-attachments/assets/f759c3d9-034e-46d9-bd85-188603dece93" />

Then go to file “osTicket-Installation-Files” folder and install HeidiSQL.
Open Heidi SQL.
HeidiSQL provides a graphical interface for managing the MySQL database used by osTicket.

<img width="635" height="431" alt="image" src="https://github.com/user-attachments/assets/c8e0b5d9-9a66-4345-a3d3-78ccda5b4787" />

Click a new session and type admin username and password
This creates a root/root database session.	Connecting with administrative credentials allows database creation and management tasks.
Connect to the session

<img width="446" height="559" alt="image" src="https://github.com/user-attachments/assets/691a04f4-2f73-41f0-890d-343afc803eb1" />

Create a database called “osTicket”. Right click unnamed then select create new then database. 
Then type “osTicket”.
Then create a osTicket database.	The database provides a dedicated location for storing all helpdesk data and records.

<img width="795" height="445" alt="image" src="https://github.com/user-attachments/assets/6c770608-50a9-45be-9cd9-230ec8898e43" />
<img width="761" height="587" alt="image" src="https://github.com/user-attachments/assets/c962be2b-0f21-42c2-a883-aacfadf66906" />

Continue Setting up osTicket in the browser
Type MySQL Username and Password: root
Click “Install Now!”

<img width="638" height="485" alt="image" src="https://github.com/user-attachments/assets/1747fcd8-3747-4385-994e-53a9c22199e1" />

Then log in to OsTicket using admin username and password

















