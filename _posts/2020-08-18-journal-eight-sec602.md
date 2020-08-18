---
layout: post
title:  "Journal #Eight [SEC602]"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J8.jpeg
featured: true
hidden: true
---
<i>Understanding PKI Concepts</i>

JOURNAL #EIGHT [SEC602]

<h2>Understanding PKI Concepts</h2>

Today's class session looked at Public Key Infrastructure (PKI), specifically the Lab focussed on setting up certificates and some of the processes that make up the steps of the certificate lifecycle, which leads to the Lab question:

<h3>Q1 - Investigate and discuss the two uses of PKI in an organisation such as NMIT.</h3> 

Public Key Infrastructure (PKI) is a system that enables communications between computers to be carried out securely. It accomplishes this in two ways:

<b>Authentication</b> - which allows a user to be certain that the system they are communicating with is legitimate and trustworthy

<b>Encryption</b> - which ensures that even if the communication is intercepted by unintended recipients, it cannot be viewed 

Most of this occurs without the user being aware, with Secure Sockets Layer (SSL) being the most common use. SSL is the technology used between web servers and browsers to ensure a secure, encrypted link. There are however other uses, including:

- Secure private messaging 
- Encryption for emails
- Recovery keys for hard drives with encryption
- Secure communication with database servers
- Digital signatures
- Secure access to devices 
- Local network security 

<i>Reference:</i> What is PKI? And how it secures just about everything online, [https://www.csoonline.com/article/3400836/what-is-pki-and-how-it-secures-just-about-everything-online.html](https://www.csoonline.com/article/3400836/what-is-pki-and-how-it-secures-just-about-everything-online.html)

<i>Reference:</i> A Beginner's Guide to SSL: What It is & Why It Makes Your Website More Secure, [https://blog.hubspot.com/marketing/what-is-ssl](https://blog.hubspot.com/marketing/what-is-ssl)

Organisations need to be aware of the importance of PKI in order to keep their employees and customers secure when operating and accessing information online. Furthermore, they need this to stay compliant with both privacy laws within their jurisdiction, and with regulatory requirements surrounding the security of the data they transmit. 

In order to satisfy these requirements PKI uses several ways to authentic and secure:

- Cryptographic technologies
- Clearly defined policies and procedures
- Elements that make up the certificate lifecycle

<i>Reference:</i> Your Guide to How PKI Works & Secures Your Organization, [https://www.thesslstore.com/blog/how-pki-works/](https://www.thesslstore.com/blog/how-pki-works/)

The authentication is performed through the use of digital certificates which make the process trustworthy. They act as a way to certify the system or network identities, so the user knows it is connecting to a trustworthy source - it is often easier to think of it like a passport that validates a traveler before being let into a country. In the same way a passport is issued by a government agency, digital certificates are issued by certification authorities (CA). 

These authorities operate either as businesses which charge for certificate services with others being free, open-source alternatives such as [Let's Encrypt](https://letsencrypt.org), which is a nonprofit organisation part of the [Internet Security Research Group](https://www.abetterinternet.org/) (ISRG).  

It is important to understand that digital certificates do not last forever and this  depends on the issuing organisations policy. Most expire between one and three years, but the timescale can vary. This certificate lifecycle is depicted in the following diagram and reflects some of the tasks involved in todays Lab.

<img src="/assets/images/SEC601-J8-a.png" alt="Certificate Lifecycle"><br>

For organisations such as NMIT it is important that an adequate level of oversight in maintained, a failure to do so could lead to potential vulnerabilities in the certificate being identified and exploited by threat actors. For educational institutions like NMIT this could result in sensitive data such as student information, tutor details, or financial records being leveraged for personal gain.

<i>Reference:</i> What Are the Stages of the Certificate Lifecycle?, [https://dzone.com/articles/what-are-the-stages-of-the-certificate-lifecycle](https://dzone.com/articles/what-are-the-stages-of-the-certificate-lifecycle)

From a student perspective it's important when logging into services such as MyNMIT, that we know we can trust the server. In the case of MyNMIT the web browser authenticates the server using DigiCert Inc. NMIT currently operates multiple buildings and site locations, data sharing between these locations will also require secure, encrypted means of communications whether over the internet or locally through the intranet.

PKI uses both asymmetric and symmetric keys. Asymmetric keys are used to encrypt and decrypt the data, a method which uses the public key to encrypt the data and the corresponding private key to carry the decryption. If faster communication is required symmetric keys are often used, these are generally thought of as less secure, but there are instances where they are preferable.

<b>Conclusion</b>

PKI is a vital tool for organisations like NMIT to protect data and communications including:

- SSL/TLS certificates to provide security for web browsing and communications
- Protect access to Wi-Fi based on login credentials 
- Encrypt emails and data 
- Authenticating and securing Internet of Things (IoT) devices

A lot of the information students and tutors access require secure connections, Moodle, NMIT email accounts, MyNMIT as mentioned, TALOS, Office365, Microsoft Azure, GitHub and more - to meet expectations of user groups and to comply with regulatory requirements, PKI offers a solution to both authentication and encryption needs.

<i>Reference:</i> What is PKI and How Does it Work?, [https://info.keyfactor.com/what-is-pki#how_does_pki_work](https://info.keyfactor.com/what-is-pki#how_does_pki_work)