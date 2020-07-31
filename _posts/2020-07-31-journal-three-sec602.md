---
layout: post
title:  "Journal #Three [SEC602]"
author: d-stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J3.jpeg
featured: true
hidden: true
---
<i>Network Vulnerabilities</i>

JOURNAL #THREE [SEC602]

<h2>Network Vulnerabilities - Part 1</h2>

The second Lab this week looked at identifying network vulnerabilities. The Lab involved the completion of two tasks, Network Footprinting and Packet Sniffing. 

Looking at these two areas of vulnerability including using Kali Linux, which is used for digital forensics and penetration testing, and Wireshark. I was unfamiliar with both applications prior to this week. 

I have already discussed class sessions this week so will dive straight into the questions relating to this Lab:

<h3>Q1 - What information can you obtain by network footprinting using Nmap?</h3> 

Footprinting is a process used to gather information about an individual computer system or an entire computer network. Footprinting is carried out in two ways:

1. Passive - Such as reviewing company information online
2. Active - Utilising aspects of social engineering to gain access to a computer network

<i>Reference:</i> Footprinting and Reconnaissance, http://www.techtrick.in/Description/39-footprinting-and-reconnaissance

An attacker can gain a lot of information through effectively footprinting the target network or organisation including:

- The structure of the organisation
- Organisational proprietary information
- User and customer data 
- The range of IP addresses used in the network 
- The names of the network hosts
- The details of the hosts exposed 
- Applications on the hosts that are exposed
- The OS the system is running including any applications
- The patch state of the host machine and the applications
- The structure of the servers and the applications utilised
- Any network implementation details publicly available 

<i>Reference:</i> Anatomy Of A Hack - The Rise And Fall Of Your Network, https://www.informit.com/articles/article.aspx?p=397660&seqNum=4

The methods attackers use include:

1. Passive footprinting
	- Information publicly available through search engines 
	- Using web services to:
		○ Discover top-level domains and sub-domains 
		○ Collect location data
	- Use financial service data to analysis the financial position of the organisation
	- Use job adverts to understand the organisational structure and identify key roles and responsibilities 
	- Social network sites can be used to learn a great deal about employees and unwritten rules of the organisation
	
2. Active footprinting 
	- Target the name servers 
	- Gather documents and files publicly available to extract metadata 
	- WhoIs lookup to provide organisational information or of those managing domains 
	- Use email tracking to gain real-time information
	- Obtain DNS information
    - Analysis traceroute information

<h3>Q2 - How could an attacker use this information?</h3>

An attacker can use the information gained from this technique to learn as much about the network as they possibly can. This can include the networks remote access abilities, the ports being used over the network, the services the network employs to the benefit the organisation, and the security it deploys to protect the network.

<i>Reference:</i> Footprinting: The Basics of Hacking, https://news.hitb.org/node/5359

The more information an attacker gains, the greater success they will have at infiltrating a network. An attacker can use the information to:

- Identify the security deployed on the network it order to understand how best to target weak links and circumnavigate them in order to gain access or control over the network 
- Limit the scope of the attack by targeting specific IP address and or domains that contain the most valuable information
- Exploit the network or organisation in a way that allows the attacker to target vulnerable areas of the system  
- Create a "road map" of the organisations network prior to carrying out an attack 

Footprinting is an form of attack that organisations should take seriously. It is often the first step for attackers to start gathering information, and is successful because it uses different means to obtain the information they need to perform their attack.

<i>Reference:</i> What exactly is footprinting and reconnaissance?, https://quadrant360.com/blog/what-exactly-is-footprinting-and-reconnaissance/

<h3>Q3 - How can packet sniffing be used to detect potential threats on a network?</h3>

Packet sniffers (also known as protocol analysers) are incredibly useful tools that can help network administrators to route out problems on a network. These tools have however, found less legitimate uses. Attackers will use packet sniffers to collect network traffic data. 

Most packet sniffers are now software applications, they are used to capture traffic so a user can view either the entire network of segments of the network. How much is visible is dependent on the configuration of the network switches.

The information gathered by the software is analysed and presented to the user in a format that is readable, so threats can be easily identified. Once a threat has been discovered the network administrators can take steps to secure the network. Packets sniffers can help to identity:

- Flaws and breaches in security at the point of intrusion
- Identify the point at which data is leaked
- Detect occurrences of events that are not preferred
- Retrieve stolen or lost data packets
- Determine the extend of an infection including worms and viruses

Using encryption such as Secure Sockets Layer (SLL) or Transport Layer Security (TLS) is an important step in protecting user information. This doesn't prevent the viewing of source and destination information but it does protect the data included in the packet.

It is useful for network administrators to be familiar with packet sniffers so they understand how they work and what steps an attacker might take to infiltrate their network. By understanding the routes an attacker could take, the better they will be able to protect against them.

<i>Reference:</i> What Are Packet Sniffers and How Do They Work?, https://www.lifewire.com/what-is-a-packet-sniffer-2487312

<h3>Q4 - How can packet sniffing be used to detect potential threats on a network?</h3>

The packet capture shows us a huge amount of traffic occurring, totalling 2532 separate instances. 

The information is recorded into the following categories:

- Time 
- Source address - where the packet originated 
- Destination address - where the packet is being sent 
- Protocol - the protocol the package is using 
- Length - length of the packet in bytes 
- Info - Information relating to the packet

The source of many of the packets originated from IP address 192.168.70.5. Likewise the intended destination IP address is 192.168.70.1. 

The protocols used in the transmission are primarily TCP and ARP.

Clicking one of the packets reveals further information that could be used by an attacker. This can be viewed in the following screen shot:

<img src="/assets/images/SEC601-J3-a.png" alt="Packet Analysis"><br>

There is a lot of useful information within the packet details as follows:

- Time zone giving a location 
- Arrival date and time of the packet
- Source port being 48440
- A description of the interface used being VirtualBox
- Device connection being ethernet 

<b>Conclusion</b>

Packet Sniffers are in a lot of ways a double edge sword, like a lot of technology they are force for good, but also a force wrongdoing. It is important for network administrators to remain vigilant in monitoring the security of their network. 

It is clear from the above analyse that best practice is to encrypt all transmissions. This action does not stop all information gathering, it does however maintain the security of sensitive informaiton contained within the packet.