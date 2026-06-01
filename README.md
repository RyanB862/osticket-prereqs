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


<img width="1909" height="938" alt="Baston Connection " src="https://github.com/user-attachments/assets/52cb0744-3ecf-4042-b9f3-6ac4f9321706" />
The seond option is using Azure's Baston. Baston can deploy a windows VM but typing the VM Admin username and password for access.



























<p>
<img width="797" height="302" alt="image" src="https://github.com/user-attachments/assets/f5be735d-b86f-48e4-8d7a-9eac2f1c1738" />
</p>
<p>
Here I downloaded and extracted all the necessary dependencies from the provided ticket installation files.
</p>
<br />

</p>
<img width="615" height="414" alt="image" src="https://github.com/user-attachments/assets/eca2d548-1c45-4afe-81f0-13db31d84830" />

<img width="493" height="381" alt="image" src="https://github.com/user-attachments/assets/843172ee-848e-48c9-a99f-3df1e9b4a2f3" />

<p>
Here, I enabled IIS Windows features within the Virtual Machine along with installing CGI.
</p>
<br />

<p>
<img width="680" height="338" alt="image" src="https://github.com/user-attachments/assets/deae84a6-fcf1-4368-937d-1996f0354e2d" />


</p>
<p>
Here I installed and setup PHP directory along with the necessary rewrite module
</p>
<br />


<p>
<img width="679" height="335" alt="image" src="https://github.com/user-attachments/assets/f1fcb5ca-02f7-4ab8-955f-25492ee168e0" />

<img width="560" height="357" alt="image" src="https://github.com/user-attachments/assets/ce130f76-cbfb-407c-a6f2-ebbc12349c9c" />


</p>
<p>
Here I installed MySQL and set up user credentials and C++redistributable 
</p>
<br />
<p>

<img width="717" height="558" alt="image" src="https://github.com/user-attachments/assets/04c5e16d-0c5a-4611-8081-a156b14f1c8d" />


</p>
<p>
Here we finally installed the OSticket platform on the VM within Microsoft Azure
</p>
<br />
