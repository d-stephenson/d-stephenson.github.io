---
layout: post
title:  "Journal #Ten [SEC602]"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J10.jpeg
featured: true
hidden: true
---
<i>Implementing NAT and OpenSSH</i>

JOURNAL #TEN [SEC602]

<h2>Implementing NAT and OpenSSH</h2>

No class discussion this week.

<h3>Q1 - Investigate and discuss the use and function of the NAT Firewall in a security context.</h3> 

Network Address Translation (NAT) allows computers and devices within a private network to share a single public IP address gateway to the internet. Each computer or device retains a private IP address that identifies it on the network whilst sharing the public IP address through the router.

<i>Reference:</i> What is a NAT firewall and how does it work?, [https://www.comparitech.com/blog/vpn-privacy/nat-firewall/](https://www.comparitech.com/blog/vpn-privacy/nat-firewall/)

The main function of NAT is to server as the gateway between a private LAN network and the public WAN internet. Because of the benefit of NAT in preserving the limited IPv4 address space, its inherent security benefit as a hardware firewall is considered a byproduct - but it's a very important and useful byproduct. 

So what do we mean by hardware firewall? Effectively, what this does is stop the following types of traffic getting into a private LAN from the internet:

- Unsolicited
- Unexpected
- Unwanted
- Annoying
- Dangerous

It is capable of doing this because all the traffic sent to the internet from the private LAN must pass through the NAT router. Data can flow out of the LAN without any problems, but is blocked before it is allowed to come in. The router performs this function by recording the destination IP and port number of each packet leaving the LAN in a connections table, it is then able to accept the returning traffic by identifying the IP and port that was assigned to it and recorded in a current connections table.

When incoming packets are received by the NAT router in can scan the current connections table to determine if it is expected, this is done by comparing the tables to look for a match. If a match is found the router sends the packets to the computer or device on the LAN that is expecting it.

The real benefit of this process is that traffic received by the router, that does not match, is simply discarded and as such provides security to the private LAN. This means that threat actors are unable to infiltrate the computers and devices on a network. As a result NAT firewalls are often viewed as the first line of defence for PCs. 

NAT firewalls are even more useful when considering other devices such as smartphones, tablets and other connected devices that don't have the hardware we're available on PCs. Firewall software often doesn’t run on mobiles devices or gaming consoles for example, so the NAT firewall protects these devices from potential attack.

NAT firewall is most effective however when combined with firewall software. No system is bullet proof, so using NAT firewall and software firewall in conjunction help you to maintain network security by filtering out as many unwanted packets as possible.

<i>Reference:</i> NAT Router Security Solutions, [https://www.grc.com/nat/nat.htm](https://www.grc.com/nat/nat.htm)

<i>Reference:</i> What is a NAT Firewall? How Does It Work and Do You Need One?, [https://www.addictivetips.com/vpn/nat-firewall/](https://www.addictivetips.com/vpn/nat-firewall/)

<h3>Q2 - Investigate and discuss at least two uses of OpenSSH on either Windows or Linux.</h3> 

Open Secure Shell (OpenSSH) is a protocol that is used to encrypt data and send it from its source to its intended destination. This protocol is commonly used by developers using Linux systems, however it is also supported on Windows 10. Prior to Windows 10 support, many users operating this OS used the Putty Client which formed part of one of the earlier Labs in this series.

<i>Reference:</i> What is OpenSSH? How to enable & use OpenSSH on Windows 10, [https://www.thewindowsclub.com/openssh-on-windows-10](https://www.thewindowsclub.com/openssh-on-windows-10)

The encryption process in SSH means that any threat actors attempting to infiltrate your data, will not be able to access or read the information. The encryptions use symmetric, asymmetric and hashing mechanisms to secure these connections.

Because of the security provided by OpenSSH it has multiple practical uses, and there are many features included in its support of nearly all operating systems, I will discuss two here:

<h6>Remote Login with secure authentication</h6>

SSH is used to allow a secure remote connection between a user and a different machine such as a server. In this instance a remote server would be running an SSH server, and the local machine connects via an SSH client authenticated through a password or SSH keys. The authentication process is used to determine the identity of the user and is therefore capable of filtering out threat actors. Using an SSH key option will produce a more secure connection then password logins, keys also means you don't always have to log in. 

This is an extremely useful service for network administrators who need to manage systems securely from a remote location. It allows administrators to navigate the files and folders on a server, access applications, configurations, settings, even rebooting the server with ease and convenience.

<h6>Tunneling between machines secure file copying</h6>

SSH tunneling is used to establish a channel between two client machines or a client and server through an end-to-end encryption through TCP (port 22). In order for the service to operate on a network it will need to be enabled on the server. Services can be transmitted through this secure encrypted channel.

Once a secure tunnel Is created SFTP and SCP support the copying of files securely over the SSH tunnel. In addition, OpenSSH supports the compression of data which reduces the network chatter, leaving more bandwidth for other tasks and nodes.

A further benefit of OpenSSH tunneling is that it support protocols such as Telnet and TFTP, which are considered legacy protocols. These protocols effectively piggy-back over an authenticated SSH tunnel. This support also extends to more secure protocols including Kerberos and AFS ticket passing.

<i>Reference:</i> Some uses of Secure Shell (SSH), [https://www.supinfo.com/articles/single/6698-some-uses-of-secure-shell-ssh](https://www.supinfo.com/articles/single/6698-some-uses-of-secure-shell-ssh)

<i>Reference:</i> Remote Login with SSH, [https://medium.com/@celinedelta/remote-login-with-ssh-dbb804f82ebf](https://medium.com/@celinedelta/remote-login-with-ssh-dbb804f82ebf)

<b>Conclusion</b>

OpenSSH is considered to be a secure and robust network protocol that, as a result has many practical uses. OpenSSH is now widely used for transmitting data, files, or commands from one computer to another anywhere in the world, and can even do this across platforms such as Windows, MAC, Linux, Android, OSX etc. 

In replacing older data transfer systems such as Telnet with OpenSSH network administrators, the chance of threat actors hacking your data over LANs and WANs is greatly reduced, leaving your system more secure. 

<i>Reference:</i> Benefits Of OpenSSH, [https://www.valencynetworks.com/articles/benefits-of-openSSH.html](https://www.valencynetworks.com/articles/benefits-of-openSSH.html)