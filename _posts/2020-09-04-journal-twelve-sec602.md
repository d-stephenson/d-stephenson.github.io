---
layout: post
title:  "Journal #Twelve [SEC602]"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J12.jpeg
featured: true
hidden: true
---
<i>Wi-Fi Access Point Security</i>

JOURNAL #TWELVE [SEC602]

<h2>Wi-Fi Access Point Security</h2>

<h3>Q1 - Identify issues affecting Wi-Fi security and compare with what you can observe from the NMIT Wi-Fi network that is publicly available or where you have access to connect.</h3> 

After a review of the 'School Wireless LAN Guidelines – Building and Maintaining a Wireless Network' it is reasonable to categorise NMIT as a medium to large sized educational provider, covering multiple departments housed in multiple buildings, spread across several sites. 

NMIT is an excellent example of the unique properties that make up the physical structure of medium and large educational providers, including  some of the common challenges that can be identified which include special use buildings, high-density environments and remote buildings. These challenges increase complexity and make security maintenance more difficult. 

The recommended approach for NMIT based on the guideline would be to set up a WPA2 Enterprise, with mutual authentication and authorisation via 802.1X/EAP (Extensible Authentication Protocol).  

<img src="/assets/images/SEC601-J12a.jpeg" alt="Screenshot of WiFi settings">

The above screenshot of the NMIFI wi-fi connection shows that port 802.1X is deployed by NMIT, meaning the institution deploys the port based access control standard. The benefit of this standard is that it restricts access to the available resources until the user is authenticated. Further benefits of this standard includes the flexibility to use a range of authentication methods. 

Authentication is likely conducted through an Authentication Server (AS) (RADIUS Server) to confirm the credentials of the client device. The authentication is also used for Office 365 and MyNMIT. EAP provides the authentication framework for the client device, authenticator and authentication server, whilst the MSCHAPv2 (Microsoft Challenge-Handshake Authentication Protocol) is the authentication option used. MSCHAP is based on username and password credentials, this means that the level of complexity in password choices by users of the system is very important to maintain security. 

MSCHAPv2 also plays a role in authentication, v2 superseded v1 on Windows Vista and is commonly used as the authentication option in:

- Microsoft's implementation of the PPTP protocol for virtual private networks
- RADIUS[2] servers which are used with IEEE 802.1X i.e. Wi-Fi security using the WPA-Enterprise protocol
- Protected Extensible Authentication Protocol (PEAP) which encapsulates the EAP within an encrypted and authenticated Transport Layer Security (TLS) tunnel

Security is a continuing balance between managing the risks whilst mitigating costs, and wireless LANs have some specific risks associated with them. Wireless signals can often extend far beyond the edge of a building, in some cases this is preferred, such as at home having wi-fi extend out to the garden, but for a secured school network this is often and undesired consequence of the service. Mitigating this can be achieved by rotating the access points (APs) so they direct away from public areas, or as far away as possible to mitigate unwanted access attempts. This must be achieved without comprising access for users that use the network legitimately. 

Based on the limited information that is available to us, without vulnerability or penetration testing, it seems clear that NMIT are following the recommendations regulated in the documentation. It is not possible to determine if the more practical responsibilities of securing wi-fi networks is being conducted, such as hardware maintenance and reviewing operational failures. However, I have personally not experienced significant downtime or problems during my time at NMIT. 

<i>Reference:</i> How 802.1x authentication works, [https://www.computerworld.com/article/2581074/how-802-1x-authentication-works.html](https://www.computerworld.com/article/2581074/how-802-1x-authentication-works.html)

<i>Reference:</i> Responsibilities of an ICT contractor, [https://www.education.govt.nz/school/property-and-transport/suppliers/technical-information/responsibilities-of-an-ict-contractor/](https://www.education.govt.nz/school/property-and-transport/suppliers/technical-information/responsibilities-of-an-ict-contractor/)

<h3>Bridging the NMIT Network</h3> 

Following an informal conversation with, and recommendation from the tutor, I have investigated the reasons behind network bridging and why the NMIT wi-fi networks are shut down, or become inoperable when this occurs. 

Bridging makes connections between networks possible, this can be beneficial when connecting wi-fi networks with older wired networks. When setting up a bridge the device must have at least 2 network adapters, one to access the internet connector and another to connect to the other computer.

On Windows 10, once the bridge is created, the host machine loses its access to the internet connection. Access can be regained by setting the IP address to static using the settings that were previously assigned to the machine dynamically. This is however, only a temporary solution, and it is best practice to assign the host machine with a static IP address in a range outside the DHCP configuration.

Bridging on wireless computer networks require that APs communicate with each other in a mode that supports the traffic between them. Bridging mode can be activated on an AP either through the settings assigned by an administrator, or a physical switch on the machine. In this case administrator settings are not available to us and the APs are positioned in such a way that they are difficult to access. It may be the case that the APs simply do not support bridging mode and indeed not all models support this feature. 

In any event, from a security perspective it is completely understandable that the institution would not wish for students using BYOD (Bring Your Own Devices) to bridge the wi-fi network, potentially to individuals who are not authentication and who are not authorised to access the Wi-Fi service. 

There have been several instances where students have inadvertently used this function in NET classes, and this has resulted in connectivity issues for other users attempting to access the wi-fi. Even though this was not intended maliciously, it is important the network mitigates the risks involved and I believe the choice to operate in this way is sensible. 

<i>Reference:</i> Wi-Fi Wireless Bridging Explained, [https://www.lifewire.com/wireless-bridging-explained-816563](https://www.lifewire.com/wireless-bridging-explained-816563)

<i>Reference:</i> How to set up and manage a Network Bridge connection on Windows 10, [https://www.windowscentral.com/how-set-and-manage-network-bridge-connection-windows-10](https://www.windowscentral.com/how-set-and-manage-network-bridge-connection-windows-10)

<i>Reference:</i> Use a Bridge to Expand Your Local Network, [https://www.lifewire.com/how-network-bridges-work-816357](https://www.lifewire.com/how-network-bridges-work-816357)


