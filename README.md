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
<img src="https://i.imgur.com/wYl4OlK.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
The same results happens if we attempt an nslookup of the mainframe (command line nslookup mainframe) because we do not have a DNS record
<p>
To create a DNS A Record go to the Domain Controller vm and open the DNS Manager. In the Server Manager Board go to the domain created within the Forward Lookup Zones tab (mydomain.com)
<p>
Right click on the page and create a New Host (A or AAA). Name the host mainframe and IP Address the same as domain controller. Then Add Host and refresh the DNS server so the new record can be updated.
<p>
<img src="https://i.imgur.com/56KGMBo.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
In the Client vm on Command Prompt ping mainframe again, you'll see that its working
<p>  
<img src="https://i.imgur.com/Cn1oveu.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Perform nslookup
<p>
<img src="https://i.imgur.com/pVdQFGL.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
</p>
</p>

<br />

<h3>Local DNS Cache</h3>

<p>

Go to Domain Controller vm, on mainframe properties edit the IP Address to 8.8.8.8
<p>

</p>
<img src="https://i.imgur.com/naBbQcK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
<p>
On the Client vm  ping mainframe, observe that it still pings the mainframes old IP Address, this is because the cache needs to be updated. To see the old cache enter ipconfig /displaydns.
<p>
<img src="https://i.imgur.com/fILT6Mw.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Close command prompt and open it as administrator, enter ipconfig /flushdns. Observe that the cache is empty.
<p>
<img src="https://i.imgur.com/CKdx9tk.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
Ping mainframe again, observe the address of the new record. Enter ipconfig /displaydns, observe the A record information
<img src="https://i.imgur.com/WC4kHRH.png" height="60%" width="60%" alt="Disk Sanitization Steps"/>
<p>
</p>

<br />

<h3>CNAME Record</h3>

<p>

<p>
A canonical name (CNAME) record points from a domain to another domain, never to an IP Address.
<p>
To create a DNS A Record go to the Domain Controller vm and open the DNS Manager. In the Server Manager Board go to the domain created within the Forward Lookup Zones tab (mydomain.com)

Right click on the page and create a New Alias (CNAME). Name the alias search and the fully qualified domain name to a website such google. Enter the information and refresh the DNS server so the new record can be updated
<p>
