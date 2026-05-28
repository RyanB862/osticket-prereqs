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
<img width="936" height="817" alt="image" src="https://github.com/user-attachments/assets/2e576679-c706-4d61-9436-db195f6d1207" />

</p>
<p>
Here I set up the actual OSTicket VM to house our Active Directory system.
</p>
<br />
<p>

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
