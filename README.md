<p align="center">
<img src="https://github.com/ColtonTrauCC/dns/assets/147654000/8efa60be-b00d-4932-9438-3a8640ff3cd5" height = 20% width = 20%/>
</p>

<h1 align = "center">Understanding & Building Intuition for DNS</h1>
This lab demonstrates the use of DNS and how to configure it. Domain Name System is a naming database in which internet domain names are located and translated into IP Addresses. It maps the name people use to locate a website to the IP address that a computer uses to locate that website. When configured and installed, we'll perform excercises with the client and domain controller virtual machines in order to understand DNS more.
<br />

<h2>Environments and Technologies Used</h2>
<ul>
  <li>Microsoft Azure (Virtual Machines/Compute)</li>
  <li>Remote Desktop</li>
  <li>Active Directory Domain Services</li>
  <li>Command Prompt</li>
</ul>

<br />

<h2>Operating Systems Used</h2>
<ul>
  <li>Windows Server 2022</li>
  <li>Windows 10 Pro (21H2)</li>
</ul>

<br />

<h2>DNS Exercises</h2>


<h3>A-Record</h3>

</ul>

<br />
The "A" in A Record stands for address and this is the most fundamental type of DNS record: it indicates the IP address of a given domain. They only hold IPv4 addresses.
</p>
Connect and log into the Domain Controller and Client virtual machines as admins (mydomain.com\jane_admin)
<p>
In the Client vm open Command Prompt and ping mainframe, you will notice that it failed.
</p>
