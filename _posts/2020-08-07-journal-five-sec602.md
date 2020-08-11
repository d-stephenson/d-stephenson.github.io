---
layout: post
title:  "Journal #Five [SEC602]"
author: d-stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J5.jpeg
featured: true
hidden: true
---
<i>Scanning and Remediating Vulnerabilities</i>

JOURNAL #FIVE [SEC602]

<h2>Scanning and Remediating Vulnerabilities with OpenVAS</h2>

The second class session looked at assessing system security, defining scope and discussing possible rules of engagement. I have worked in business consultancy previously, and part of position objective was to carry out strategic business reviews with the aim to effect turnaround. This involved an assessment of every profit making area of the organisation. Some of what I did was somewhat familiar to this exercise and there may be areas where I could utilise some transferrable skills, albeit the subject matter is very, very different. 

Moving away from the class work and diving into the fresh learning subject matter of Lab 5:

<h3>Q1 - Investigate and discuss one of the more severe vulnerabilities found as a result of the OpenVAS scan. Depending on the vulnerability the Common Vulnerabilities and Exposures (CVE) database may be of use.</h3> 

I started this investigation with the intent to look at the vulnerability results for DCE/RPC and MSRPC Services Enumeration Reporting. However I was unable to locate a reference from the CVE database. I have instead chosen to look at results for SSL/TLS: Report Weak Cipher Suites - vulnerability CVE-2013-2566.

The results identified by the scan are that the service will accept weak SSL/TLS cipher suites. Cipher suites are a set of mathematical algorithms. Ciphers suites are used for encryption, decryption, digital signatures or hashing.

<i>Reference:</i> [Cipher Suites in TLS/SSL (Schannel SSP), https://docs.microsoft.com/en-us/windows/win32/secauthn/cipher-suites-in-schannel](https://docs.microsoft.com/en-us/windows/win32/secauthn/cipher-suites-in-schannel)

The scanning tool is a useful resource. Not only does it perform the scan function but, once vulnerabilities are identified, offers a solution, provides further details regarding the vulnerability detected in addition to references which allowed me to pull up the information on the CVE database. 

The insight provided by the report surrounded the cryptographic strength of the ciphers. Specifically identifying ciphers that are 64-bit or less which are considered weak. This is because these ciphers are more susceptible to brute force attacks meaning they could be decrypted, and the information contained used to initiate further attacks on the parties involved in the communication.

The CVE reports list the vulnerability as an RC4 stream cipher which is known to contain many single-byte biases. RC4 was initially a trade secret until a description of the algorithm was made public in September 1994. The effect is such that it is easy to attack remotely through plain-text recovery.

<i>Reference:</i> [RC4, https://en.wikipedia.org/wiki/RC4](https://en.wikipedia.org/wiki/RC4)

The following link is to an interesting article regarding the RC4 encryption algorithm and its vulnerability to brute force using plain-text attacks: [https://threatpost.com/new-rc4-attack-dramatically-reduces-plaintext-recovery-time/113808/](https://threatpost.com/new-rc4-attack-dramatically-reduces-plaintext-recovery-time/113808/) 

The CVE reports scores the vulnerability as follows:

- There is a risk to the confidentiality of the information stored, with a considerable chance it would be accessed by the attackers
- The is no requirement for authentication in order to exploit the vulnerability 
- There is some degree of complexity to gain access, but if pre-conditions can be satisfied the cipher can be exploited 

This type of vulnerability does not impact the availability or integrity of the system, which can mean that the scope of the attack is limited. However, all the popular web browsers from Safari, to Firefox and Google Chrome are affected by this vulnerability type.

For context there are other ciphers which, as a result of their design are more secure as followed:

- if over the preceding 10 year period the cipher remains secure then they are identified as offering 'medium' security protection
- if the cipher offers longer protection then they are considered to be offering 'strong' security protection

As a result the scanning tool recommends mitigating the problem by configuring the services so that they no longer accept any types of cipher suites that are categorised as weak. 

The following url will link to the CVE report as discussed in this journal: [https://www.cvedetails.com/cve/CVE-2013-2566/](https://www.cvedetails.com/cve/CVE-2013-2566/)

<h3>Q2 - Investigate and discuss vulnerability assessment of services on Cloud Infrastructure such as Amazon Web Services.</h3>

Switching to cloud services for applications, file storage and even network management is becoming more commonplace. Most of us use services such as Google Drive to store or back-up our documents and photos, or Firefox cloud services to sync our bookmarks and tabs across devices and even network servers which we discussed in NET603 last semester. 

These types of cloud services offer convenience, cost savings and reduced set up time. The downside of these services is the exposure to various risks as follows:

- Commercial 
- Financial
- Technical
- Legal
- Compliance 

It is important for users of these services to understand that the threats involved in switching to the cloud are constantly evolving. Remaining vigilant and informed is an important step for the providers of these services, and you as the end user.

Cloud services share a lot of the same risks, threats and vulnerabilities that 'traditional' environments suffer. A lot of the applications a user will normally run are also utilised in cloud services, the software applications are the same and so are equally as exploitable by attackers. From the users perspective what this also means is that security responsibility is now shared between you and the provider. 

For personal users this is likely to increase the security level, on larger corporate networks this may be trickier to determine - for example where does the service providers offering or liability end, and yours take over? If a risk assessment unsuccessfully defines the point of concern in this type of scenario, it could lead to breaches that might have otherwise been avoided. 

This brings us to the threats and vulnerabilities that are unique to cloud based solutions:

<h4>1. The level of control and visibility the user has over the cloud service</h4>

This is a significant threat to consider when moving to the cloud. Where does security concerns end for the user and start for the provider, is it clear and what steps can be taken to ensure the dual responsibility meets in the middle so that the system maintains full protection?

On a network level a technician would have to assess the service offered fully, and be constantly aware that terms and conditions are subject to change and as a result service levels can change. If this occurs a review would need to take place to determine what steps should happen to meet any challenges these changes create. This can also be problematic when considering how much trust to place in the provider to meet the ever-evolving treats that can pose a risk to the network. Ultimately it may be decided that the benefits of a cloud service are not worth the potential of increased risk.

<h4>2. The ability of network users to add services without I.T. authorisation</h4>

Providers of cloud services make it very easy for users to add applications and features without the knowledge of the team that manage the network system. This type of activity is referred to as shadow I.T. and makes the network more difficult to protect from specific threats. 

The additional service offered may not be considered as a secure package, and in ordinary circumstances may be rejected by the I.T. team and an alternative recommended. Not only is this an undesired scenario but it also reduces the visibility of the network by the people who's job it is to secure it. 

<h4>3. The need to delete data and be confident that the data is 'deleted'</h4> 

The simple fact is that the user has no idea where their data is physically stored, including the data of their customers and employees which limits their ability to verify that the data has been completely deleted. Often the data will be stored across multiple storage devices within the cloud providers network infrastructure, most likely for legitimate reasons such as back up and recovery.

Each cloud provider will have different procedures for handling deleted data, and if these procedures fail then any data you believed was securely deleted, may still be available to potential attackers.

<h4>4. Exposure of application programming interfaces (API) to the internet</h4> 

A lot of cloud services provide a web-based interface that allows user to access and interact with the applications they use. The APIs are a risk to the same type of attacks as those on operating systems accessed through an on-site network. However, the added risk comes from the fact that cloud APIs are accessed online which increases the reach and as a consequence the vulnerability.

These make cloud APIs a potentially easier target for attackers to discover vulnerabilities in order to compromise the cloud assets. More worrying is that if an attack is successful, further attacks could be carried out in the system, gaining access to increased data or more sensitive data.

It should be noted that these vulnerabilities are over and above those that exist both on cloud solutions and on-site solutions which include:

- Potential for stolen authentication information such as usernames and passwords
- Any increase in the complexity of a network increases the responsibilities of the I.T. team which can increase the likelihood that concerns are missed
- Threat actors can include employees of the organisation and procedures and policies should help to mitigate this risk
- Loss of data stored in the system due to accidental deletion or malicious attack 
- Reliance on a supply chain resulting from outsourcing infrastructure, maintenance or operations
- A lack of due diligence or understanding of the scope of the system 

<i>Reference:</i> [12 Risks, Threats, & Vulnerabilities in Moving to the Cloud, https://insights.sei.cmu.edu/sei_blog/2018/03/12-risks-threats-vulnerabilities-in-moving-to-the-cloud.html](https://insights.sei.cmu.edu/sei_blog/2018/03/12-risks-threats-vulnerabilities-in-moving-to-the-cloud.html)

<b>Conclusion</b>

Cloud services are impossible to ignore, there are many benefits for users and organisations, and as long as we remain security conscious these services should be considered as viable alternatives. The challenge comes when assessing the risk and understanding where responsibility lies, as well as staying up to date with the changing security landscape and how that makes cloud services vulnerable when compared with on-site solutions.

If you as the user, or an organisation decides collectively that the benefits out-way the risks then there is no reason not to proceed. I have used Google Drive for many years to back up my documents and found it to be invaluable, however more recently my concerns over how Google uses that data forced me to leave the service. The downside to this decision? I wasn't ready to give up the benefits of this kind of cloud backup and cross devices syncing. I have found an alternative provider 'Sync' - the data encryption and privacy policy meet my requirements and I have been using them for around a year. I recognised the downsides of the Google product adapted and sought out a different solution that worked better for me.  