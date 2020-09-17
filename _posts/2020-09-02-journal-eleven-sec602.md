---
layout: post
title:  "Journal #Eleven [SEC602] - Firewall Rule Based Management"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J11.jpeg
featured: true
hidden: true
---
<i>Firewall Rule Based Management</i>

JOURNAL #ELEVEN [SEC602]

<h2>Firewall Rule Based Management</h2>

<h3>Q1 - Investigate and discuss the configuration required on a firewall for a web server providing</h3> 

<h4>HTTP and HTTPS</h4>

HyperText Transfer Protocol (HTTP) and HyperText Transfer Protocol Secure (HTTPS) allows uses to access web pages through their browsers. Websites are retrieved from the web servers hosting the websites, in order for a connection between the user and the server to be established the firewall must be configured to allow inbound traffic from port 80. Server management ports or database ports should not configured to allow access in this way.

It is appropriate to allow for all source IP addresses to access the web server hosting HTTP, businesses, organisations and blog sites for example want their websites to be found online and so this would be an acceptable best practice. In this case the public IP address of 103.28.250.99 would be made available, much like google maintains the public IP addresses 8.8.8.8 and 8.8.4.4.

<i>Reference:</i> Port 80, [https://www.techopedia.com/definition/15709/port-80](https://www.techopedia.com/definition/15709/port-80)

<i>Reference:</i> Best practices for firewall rules configuration
[https://support.rackspace.com/how-to/best-practices-for-firewall-rules-configuration/](https://support.rackspace.com/how-to/best-practices-for-firewall-rules-configuration/)

<h4>FTP over TLS/SSL</h4>

File Transfer Protocol (FTP) is a network protocol that allows for the transfer of files between a server and a client node on a network. FTP over Transport Layer Security (TLS) and Secure Sockets Layer (SSL) is an extension to FTP that supports the TLS and SSL. The default port for FTP is 21 and for FTP over TLS/SSL it is 990.

To allow connections to be established the FTP server will need to know the external IP address, in this case example 103.28.250.99. Port 21 will need to be configured to allow traffic, additionally an implicit TLS/SSL FTP port 990 may need to be configure to allow traffic. Ports will then need to be opened for the data connections, depending on the firewall it may have functionality that monitors FTP control connections and open and close data connection ports as required, this is done automatically. 

If the firewall can not perform this function automatically it would not be best practice to open the entire default port range of 1024-65535. The FTP server should have a defined useable range that is configured as 'open' for the necessary data connections. Internal Windows firewall is configured with default rules for both port 21 and 990 in additional to the 1024-65535 range when FTP sever is installed. 

<i>Reference:</i> FTP and FTPS Ports: An Overview, [https://www.cerberusftp.com/ftp-and-ftps-ports/](https://www.cerberusftp.com/ftp-and-ftps-ports/)

<i>Reference:</i> Installing a Secure FTP Server on Windows using IIS [https://winscp.net/eng/docs/guide_windows_ftps_server](https://winscp.net/eng/docs/guide_windows_ftps_server)

<h4>SMTP for sending emails from the websites</h4>

Simple Mail Transfer Protocol (SMTP) sends outgoing email using ports 587, 465 or 25. Mail servers should operate best practices, this is important because email delivery depends on the reputation of the sender. 

<b>Port 587</b> - When an mail client such as Windows or Apple Mail, Outlook or Thunderbird sends an email via a proper mail server, SMTP port 587 should be the default used port. Port 587 ensures that the email is submitted securely, particularly when it is coupled with TLS encryption. Because of this it is advised that this port is configured as open for outgoing traffic, the only reasons this would not be used is if the hosting provider or upstream network block the port.

<b>Port 465</b> - This port has been reassigned to a new service and should not be used for SMTP communications. Legacy systems are still capable of deploying the port and as such these applications still demand that this port be used. This port should remain closed for the purpose of SMTP.

<b>Port 25</b> - Email clients like those mentioned in port 587 section, should not use port 25. Port 25 is commonly blocked by residential ISPs and Cloud Hosting Providers in an effort to reduce the amount of spam mail being relayed from compromised servers or computers. If a mail server is being managed there may be a case for configuring this port as open, otherwise there should be no traffic traversing this port. 

<i>Reference:</i> Sending email and SMTP best practices, [https://upcloud.com/community/tutorials/sending-email-smtp-best-practices/](https://upcloud.com/community/tutorials/sending-email-smtp-best-practices/)

<i>Reference:</i> Which SMTP Port Should I Use? Understanding Ports 25, 465, & 587, [https://www.mailgun.com/blog/which-smtp-port-understanding-ports-25-465-587/](https://www.mailgun.com/blog/which-smtp-port-understanding-ports-25-465-587/)

<h4>Remote Administration</h4>

The remote desktop client in Windows is a tool that allows users with administrator access to operate a server in a remote environment. The default port for remote desktop is 3389 and the firewall configuration rule should be open to ensure accessibility. This allows remote access over the LAN, it is not recommended that this port be made accessible over the internet. If this is a requirements of the network however, then the port should be forwarded through the main router.

To allow access to remote administration over the internet port 3389 must go through the public network and through the router providing internet connectivity. The incoming rule will allow port 3389 to the computer that the user is accessing the network server. 

Another consideration is changing the default port 3389, as this is a potential security threat. Best practice recommends that the port be changed to something above 10000, this is because port scanners used by threat actors will start scanning from port 1.  

<i>Reference:</i> How To Open RDP Port To Allow Remote Desktop Access To Your System, [https://www.itechtics.com/rdp-port/](https://www.itechtics.com/rdp-port/)

<h3>Q2 - Investigate and discuss the configuration required on a firewall for a database server providing.</h3> 

<h4>MariaDB</h4>

MariaDB is a relational database management system (DBMS) that uses a Structured Query Language (SQL). MariaDB operates through port 3306, this must be configured to allow incoming and outgoing traffic. Incoming traffic may be required to allow requests from remote clients to allow TCP access to MySQL through the firewall. 

A decision must be made to how the granting of access to remote hosts is determined which includes:

- Allowed privileges 
- The databases that those privileges apply 
- Hosts that allow user access
- Authentication 

Opening up a MariaDB server to the internet and granting access to all hosts goes against best practices. Access to the database should be based around least privilege principles and IP address access through firewall configuration supports this principle.

<i>Reference:</i> Getting Started with MariaDB MaxScale Database Firewall Filter, [https://mariadb.com/resources/blog/getting-started-with-mariadb-maxscale-database-firewall-filter/](https://mariadb.com/resources/blog/getting-started-with-mariadb-maxscale-database-firewall-filter/) 

<i>Reference:</i> Configuring MariaDB for Remote Client Access, [https://mariadb.com/kb/en/configuring-mariadb-for-remote-client-access/](https://mariadb.com/kb/en/configuring-mariadb-for-remote-client-access/)

<h4>Remote Administration</h4>

Remote administration allows access to an SQL Server from another location, it grants the ability to access and manipulate data located on the server. 

Configuration settings to allow this connection include access through the firewall and the SQL Server instance to allow the protocol being requested.

To enable the server instance, TCP/IP protocol must be enabled which allows resources to be shared over the network. TCP port 1433 is the appropriate port to be configured to allow the remote connection. 

If multiple named instances are installed then a port number that corresponds to a named instance must be used. Named instance uses dynamic ports which means a new port number is assigned when the database engine starts, this makes it difficult to configure the firewall to enable access. 

This is resolved through the SQL browser service which provides the TCP port that corresponds with the named instances, the services use UDP port 1434.

<i>Reference:</i> How to connect to a remote SQL Server, [https://www.sqlshack.com/how-to-connect-to-a-remote-sql-server/](https://www.sqlshack.com/how-to-connect-to-a-remote-sql-server/)

<h4>Firewall Filtering - Summary</h4>

Firewall is used to protect the network from external threats. This is achieved by utilising a variety of methods covered under the following 5 functions:

1.	Port filtering 
2.	MAC filtering
3.	IP filtering 
4.	Content filtering
5.	Dynamic filtering

The first four functions are simple static filtering, this means packets are examined independently based on a set of variables as defined by the system set-up. This type of filtering does not refer to packets which may have previously passed the firewall. 

The fifth function examines packets as a stream and decides on whether to pass a packet depends on packets that have already been through the firewall. This means a packet is examined as a whole and not as a sum of the parts. Packets will be analysed for authenticity to ensure it has not been altered during the transmission process.

<b>Port Filtering</b>

Different applications use different port numbers, for example emails use port 587 and web pages use port 80. Port filtering can allow or deny a certain application by opening or closing the related port number. 

<b>MAC Filtering</b>

Median Access Control address is assigned to devices Network Interface Card (NIC). A devices MAC address never changes and so this type of filtering is useful for blocking specified devices. 

<b>IP Filtering</b>

This blocks packets based on IP addresses represented in layer 3 of the OSI model. Either single IP addresses can be blocked, or a range of IP addresses.

<b>Content Filtering</b>

Can be referred to as information filtering and is used to block websites by matching strings of characters such as hate, violence or pornography. When the strings match then the content is denied access.

<b>Dynamic Filtering</b>

This type of filtering is the most comprehensive method and makes its decision based on the whole picture. The process involves the checking of packets from layer 2 to layer 7 of the OSI model. This includes looking at the source and destination of IP addresses and port numbers, in addition performs a close inspection of the contents up to the application layer. 