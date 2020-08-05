---
layout: post
title:  "Journal #Four [SEC602]"
author: d-stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J4.jpeg
featured: true
hidden: true
---
<i>Network Vulnerabilities</i>

JOURNAL #FOUR [SEC602]

<h2>Network Vulnerabilities - Part 2</h2>

This weeks class session was particularly enjoyable. We discussed ciphers and actively participated in 'cracking' a cipher. The exercise gave a good insight in to how this functionality works in practice when the information we share online everyday is encrypted and decrypted - plus it was a lot of fun! 

The first Lab this week continued from last weeks network vulnerabilities: 

<h3>Q1 - Explain in your own words the DOS attack scenario.</h3> 

The Lab attack scenario utilised the Wireshark Network Analyzer to capture packets transmitted on a 'tcp port 80' connection. The scenario itself was a TCP 3-way handshake, or SYN > SYN/ACK > ACK. 

I wanted to be clear as to what was happening here so carried out some further research. Put simply there are three messages that make up the 3-way handshake, these are transmitted by TCP in order to begin a session between two computers attempting to communicate. 

By establishing a connection over the network the computers can then begin to transmit other data such as SSH and HTTP. This type of communication occurs frequently across networks and in itself is not a cause for concern.

<i>Reference:</i> TCP 3-Way Handshake (SYN,SYN-ACK,SYN), https://www.inetdaemon.com/tutorials/internet/tcp/3-way_handshake.shtml

The attack is carried out through the 'hping3' tool ,designed to overload the system by sending a large number of packets at set intervals to a specific target. These purpose of the request is to send packets at a rate that is faster then the target machine can handle them. 

In a commercial organisation or public sector setting the effect of such an attack can lead to operational loss in the form or employee downtime, to an inability to fulfill mandated services such as those provided by the public sector.

We are able to view the effects and severity of this attack in the Wireshark capture.

<h3>Q2 - Explain in your own words how the Hping3 attack causes the denial of service.</h3>

The hping3 command carries out the DOS attack by effectively 'flooding' the server. The effect of this type of attack is to make the server inoperable to the legitimate users of the network. 

The hping3 command is targeting a computer at a specific destination address, in this instance 192.168.0.2. The command targets the destination host through port 80 which is assigned to HTTP, it does this at set intervals which is how the attack intends to overload the system.

The command sends SYN packets which are empty, at set intervals. It does this using IP addresses which are generated at random. The packets appear like legitimate requests to establish communication - this means that the targeted device responds to each attempt and staying open whilst it waits. The connection will eventually time out, but before that happens another packet will have already been sent and this cycle continues. 

<i>Reference:</i> TCP SYN Flood, https://www.imperva.com/learn/application-security/syn-flood/

This is in effect a relatively simple but effective attack. The aim is to either severely restrict access to the machine or network, or make it completely unresponsive as it exploits the normal 3-way handshake.

These port 80 attacks are often used to attack banks and other organisations where customers rely on accessing their information through web servers. It's not difficult to imagine the effect not being able to access your online banking or credit card statements would have, or not being able to access your favourite news media site or video streaming service.   

<h3>Q3 - Discuss the benefits of using anti-phishing functionality.</h3>

Anti-phishing functionality is an essential part of any security set-up, and should sit alongside other precautionary measure such as firewalls and antivirus programs. There are several tools to consider including:

<b>Anti-phishing Toolbars</b>

These can be installed to web browsers as 'add-ons'. They help users to detect phishing websites. These tools block anything they detect as malicious, in real-time to keep computers and networks safe. 

These are particularly useful for those who are not as tech-savvy or familiar if the potential harm caused by phishing attacks. 

<b>Antivirus Solutions</b>

Antivirus software can help identify and block these types of phishing attacks. As part of the solution the firewall stops malicious traffic attempting to infiltrate the network. 

Fortunately, vulnerable operating systems such as Windows now include well tested anti-virus applications such as Defender. There are also plenty of free alternative 'home-use' antivirus applications available on the market, with paid solutions for businesses and organisations. 

<b>Anti-phishing Solutions</b>

This is specifically targeted software designed to stop phishing, malware, spoofing and spam by intercepting and scanning incoming traffic, if it suspect it could be harmful it will takes steps to protect the user. 

It does this by blocking .exe file and filtering emails so only safe emails make it into your inbox. As a result of this real-time system monitoring these types of software can be very effective at securing devices and networks. 

<b>Conclusion</b>

Phishing attacks are everywhere and they can often be hard to detect and protect against. It is good practice to use more then one anti-phishing tool. No one method is perfect, and there will always be flaws that can be taken advantage of, by using multiple tools you increase the likelihood of maintaining your system security. 