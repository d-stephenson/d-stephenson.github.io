---
layout: post
title:  "Journal #Sixteen [SEC602] - Introduction to Digital Forensics"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J16.jpeg
featured: true
hidden: true
---
<i>Introduction to Digital Forensics</i>

JOURNAL #SIXTEEN [SEC602]

<h2>Introduction to Digital Forensics</h2>

Digital Forensics is the scientific application of the various processes that make up this capacity. The forensics process is used in scenarios that warrant investigation including:

- <b>Quick Internal Investigations:</b> IT Administrators are instructed to review documents in a corporate environment
- <b>Civil Investigations:</b> Third party data is acquired using a subpoena for presentation in a court of law
- <b>Slow Criminal Investigations:</b> Law enforcement uncovers illegal possession of digital material

Common causes that lead to the forensics process include identifying malicious code, uncovering unauthorised access or misuse of resources, DOS attacks, espionage or hoaxes.

The steps involved in the digital forensics process are as follows:

<h3>1 - Identification</h3> 

Prior to conducting a digital forensic investigation an action plan must be created that determines who will be investigated, and where the best sources of digital information is likely to be obtained.

Understanding the scope allows an organisation to:

- Mitigate the risk that sources are overlooked
- Gain an estimation of the costs involved to meet the objectives
- Limit cost increases later as a result of newly identified sources

The identification process should include:

- Interview key people to identify devices of interest 
- Understand who has what authority 
- List all the potential locations of digital information
- Identify devices that have remote capabilities
- Document the findings, network structure and file types
- Agree the scope prior to proceeding 

<h3>2 - Preservation</h3> 

It is critical that the original evidence is preserved in order for an analysis to be conducted, time is an important factor when dealing with preservation. There are several important steps that should be observed: 

1. Retain the state of the device, if running leave it running and if powered down leave it powered down
2. If possible move the device to a secured area, or ensure it is monitored then document those people that have had access
3. Ensure that external media such as USB drives or memory cards are not connected to the device
4. It is important that changes are not made to the slack space memory, so nothing should be copied to or from the device
5. Take photographic evidence of the device from all angles to ensure no further tampering can take place
6. Ensure the login credentials are secure and can be passed to the forensic investigation team
7. Only trust certified forensics investigator with the device to limit the chance of human error 
8. Volatile memory may contain crucial information, if required send the device into hibernation mode but keep it powered on

<h3>3 - Collection</h3> 

The collection of devices has changed over the years, the onset of cloud servers and the advancement in technologies means that it is no longer the case of simply removing a device from a organisation to be analysed later.

Whilst the gathering of devices still serves a purpose, often the same results can be achieved by duplicating the electronically stored information (ESI). The benefit of this method is that the original evidence is preserved, in some instances this can actually mitigate potential loss caused by removal, resulting from powering the machine down

Alternatively, a device can be imaged after being powered down, known as a dead box forensic collection. A live collection can also be performed prior to the device being powered down, this can be extremely useful for encrypted devices where the credentials are not known and the encryption key not retained, if an employee has left an organisation for example.

Other instances where removal might not be possible is with servers that are providing critical operational functions to a business and its customers. Either the data will need to be collected on the live machine, or outside working hours in order to ensure operations are not adversely affected. If infrastructure has been moved to the cloud then data can be collected remotely which can reduce costs.

<h3>4 - Examination</h3>

The examination process involves the extraction and recovery of digital evidence from the device using acceptable methods, these methods can vary depending on the media type. There are two types of extraction described separately:

1. Physical Extraction

This technique involves extracting data at the physical level, no consideration is made to file systems on the drive. The technique may include the methods such as:

- <b>Keyword searching:</b> Useful to extract data not accounted for by the OS or file system 
- <b>File carving:</b> Assist the recovery of usable files and data not accounted for by the OS or file system 
- <b>Extraction of the partition table and unused space:</b> To determine if the physical hard drive size is accounted for, may also identify present file systems

2. Logical Extraction

This technique aims to extract data based on the present file systems on the drive, including active and deleted files, file slack, and unallocated space. The technique may include methods such as:

- Revealing the directory structure and file attributes such as file size, names, location and date/time stamps
- Identify and eliminate known files through the comparison of calculated hash values to authenticated hash values
- Extract files pertinent to the investigation, can be based around file extensions and names, headers or content, or its location on the drive
- To recovery any files that had been deleted
- Extract encrypted or compressed data
- Extract file slack
- Extract any unallocated space

<h3>5 - Analysis</h3>

No matter how meticulous the extraction of data, its analysis is time consuming and costly when attempting to determine its significance. Performing an analysis review includes looking at:

- <b>Timeframe:</b> Determine when events occured by studying the date/time stamps and system and application logs, in addition to security, installation, error and connection logs, whilst lso considering differences in dates reported in the BIOS

- <b>Data Hiding:</b> Detecting data that has been concealed can assist in determining knowledge of an event, ownership, or intent. Hiding can be identified by correlating file headers with extensions, accessing encrypted data, steganography, and accessing a host-protected area (HPA)

- <b>Applications & Files:</b> Identify problems and files that may contain relevant information by studying file names for patterns and relevance, detailed examination of content, the numbers and types of OS, correlating files and applications, consideration of file relationships and default storage locations, examining configuration settings and finally performing a metadata analyses 

- <b>Ownership & Possession:</b> Instances occur that require an identification of users that created, accessed and modified a file to determine ownership and knowledge. This can be achieved by placing a subject at the device at a particular data and time, discovering files of interest stored in unexpected locations, deliberately hidden data, recovered passwords to access files that indicate possession and ownership, reviewing contents of a file can achieve the same outcome

<h3>6 - Presentation</h3>

Once the data has been analysed a report is produced either by the application used to provide a digital analysis, or as is common, in conjunction with a written report.

The report is produced for the relevant stakeholders, which can include corporate executives, law enforcement agencies, the courts or government bodies. Due to the intended audience the information in the report must be clear, concise and sufficient in detail for the defence process.

The report should include:

- High level Executive Summary using non-technical language 
- The findings encompassing technical analysis including any diagrams and charts
- Technical reports providing highly detailed information and evidence 
- Conclusion produced in a subjective manner including concise and direct expert opinions 

<i>References</i> 

Digital Evidence Preservation—Digital Forensics. (2020, May 31). GeeksforGeeks. [https://www.geeksforgeeks.org/digital-evidence-preservation-digital-forensics/](https://www.geeksforgeeks.org/digital-evidence-preservation-digital-forensics/)

Digital Forensics Process—Identification. (2017, May 4). DriveSavers Data Recovery Services. [https://drivesaversdatarecovery.com/blog/digital-forensics-process-identification/](https://drivesaversdatarecovery.com/blog/digital-forensics-process-identification/)

Digital Forensic Process—Presentation. (2018, April 4). DriveSavers Data Recovery Services. [https://drivesaversdatarecovery.com/blog/digital-forensic-process-presentation/](https://drivesaversdatarecovery.com/blog/digital-forensic-process-presentation/)

Introduction to Digital Forensics - Cipsec. (n.d.). Retrieved September 17, 2020, from [https://www.cipsec.eu/content/introduction-digital-forensics](https://www.cipsec.eu/content/introduction-digital-forensics)

US Department of Justice; Office of Justice Programs; National Institute of Justice. (2004). Forensic Examination of Digital Evidence: A Guide for Law Enforcement: (378092004-001) [Data set]. American Psychological Association. [https://doi.org/10.1037/e378092004-001](https://doi.org/10.1037/e378092004-001)