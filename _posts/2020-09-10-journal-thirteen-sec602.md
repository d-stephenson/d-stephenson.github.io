---
layout: post
title:  "Journal #Thirtenn [SEC602]"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J13.jpeg
featured: true
hidden: true
---
<i>Implementing a Network Policy Server</i>

JOURNAL #THIRTEEN [SEC602]

<h2>Implementing a Network Policy Server</h2>

Network Policy Server (NPS) involves the implementation of security features as part of a Remote Authentication Dial-in User Service (RADIUS) installation. NPS was set-up to provide authentication of dial-in VPN users, authorisation to permit access to resources on the network, and accounting purposes - specifically the time users spent dialed in to the remote session. Together, these protocols are known as 'AAA' and are used to mediate network access. 

A discussion of 3 security features implemented in the Windows Server 2016 NPS set-up:

<h3>1 - The authentication method used:</h3> 

The authentication method used is MS-CHAPv2. This can be obtained from the Point-to-Point Tunneling Protocol (PPTP) information provided during the VPN connection set-up. PPTP tunneling communicates with the peer on TCP port 1723, but is now recognised as an obsolete protocol which was originally designed for implementing VPNs. The reason it is now obsolete is due to the quantity of commonly known and serious security vulnerabilities.

The Microsoft implementation of the tunneled PPP traffic can be authenticated in several ways, PAP, CHAP, MS-CHAPv1 and as is the case in this instance, MS-CHAPv2. MS-CHAPv2 problems have been known for some time and Microsoft has released warnings instructing that it should not be used. In fact, Moxie Marlinspike presented CloudCracker web service at the Black Hat conference in 2012, it showed how any PPTP connection with MS-CHAPv2 can be cracked within 24 hours.  

The RADIUS Server authenticates the remote users accessing the network through a central database, when a user is granted access the server generates an individual encryption key which is assigned to the user. The main advantage of a RADIUS Server is the centralisation of the AAA capabilities, providing greater security and improved efficiency.

<h3>2 - The security policy created:</h3> 

The NPS provides the infrastructure that authorises users on the network to access resources. Test attempts to gain access can be carried out in order to check that only authorised users can gain access remotely. 

Configuring Routing and Remote Access Service (RRAS) provides the user with remote access to the server utilising a secure VPN. In many set-ups the deployment is through a configured IP-based range, the policy can then be applied to user groups and takes on the role of verification. The group of services including with RRAS are:

- Remote Access
- Dial-up Remote Access Server 
- VPN Remote Access Server 
- IP Router (Connecting network subnets)
- Network Address Translation (NAT) Services 
- Services specific to routers
- Dial-up and VPN site-to-site demand-dial router

<h3>3 - The accounting method used:</h3> 

The last pillar of network security is the ability of those charged with protecting the system to view and analyse the file logs. This can be achieved in two ways, firstly they can be viewed within the 'Log Files' stored on the server, which opens in Notepad on Windows. Due to the formatting of the logs they can be difficult to study, however it does include information including the IP address, network user, start access date and time and stop access time date and time.

The other method used to view these logs is through a third party administrative tool such as IAS Log Viewer, which acts as a reporting tool for Windows IAS/NPS Server. This application comes with many additional features starting with an interactive user friendly interface that makes the analysing of information far easier, a result of the clear titles for headings and inclusion of the connection results which is useful in instances where a connection is rejected.

Other features which would be useful for those tasked with network security to take advantage of include:

- Ability to work with large log files
- Open several log files or directories 
- Work with and view log files in real time 
- Analyse metrics in real time 
- Export files to XML or CSV files
- Create customisable reports 
- Command-line functionality for processing log files
- Data filtering for specific report creation
- Alerts to identified events if and when they occur
- Create user defined columns in reports

<i>References</i> 

Network RADIUS. (n.d.). How a RADIUS Server Works. Network RADIUS. Retrieved September 10, 2020, from [https://www.techopedia.com/definition/3424/routing-and-remote-access-service-rras](https://www.techopedia.com/definition/3424/routing-and-remote-access-service-rras)

DeepSoftware. (n.d.). IAS Log Viewer. Retrieved September 10, 2020, from [https://www.deepsoftware.com/iasviewer/](https://www.deepsoftware.com/iasviewer/)

The H Security. (2012, August 22). Microsoft says don’t use PPTP and MS-CHAP - The H Security: News and Features. [http://www.h-online.com/security/news/item/Microsoft-says-don-t-use-PPTP-and-MS-CHAP-1672257.html](http://www.h-online.com/security/news/item/Microsoft-says-don-t-use-PPTP-and-MS-CHAP-1672257.html)

Point-to-Point Tunneling Protocol. (2020). In Wikipedia. [https://en.wikipedia.org/w/index.php?title=Point-to-Point_Tunneling_Protocol&oldid=966505086](https://en.wikipedia.org/w/index.php?title=Point-to-Point_Tunneling_Protocol&oldid=966505086)

What is Routing and Remote Access Service (RRAS)? - Definition from Techopedia. (2012, June 12). Techopedia.Com. [http://www.techopedia.com/definition/3424/routing-and-remote-access-service-rras](http://www.techopedia.com/definition/3424/routing-and-remote-access-service-rras)




