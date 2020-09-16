---
layout: post
title:  "Journal #Fifteen [SEC602]"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J15.jpeg
featured: true
hidden: true
---
<i>Backup and Recovery</i>

JOURNAL #FIFTEEN [SEC602]

<h2>Backup and Recovery</h2>

<h3>1 - Summarise the backup and restore functions of Windows Server Backup</h3> 

Windows Server Backup and Recovery is the process of copying data and archiving it to a separate hard drive or external storage device. The benefit of this function is, should the operating data drive become corrupted or data be maliciously or accidently deleted, it can easily be recovered. Data backup is a vitally important part of an organisations disaster recovery plan, and an essential practice as part of the daily management of a network. 

Backing up data includes the data held on the system, meaning that settings and system data may not form part of the process, such as active directory servers and computer clusters. 

Windows Server Backup feature is installed through the 'Add Roles and Features Wizard', once installed backups can be performed manually, or scheduled to be carried out automatically. During the setup process the destination location must be specified for the backup files.

Windows Server 2012 introduced additional features that allowed Hyper-V virtual machines to be individually backed up and restored in the same way an application would be, the backup can also be performed as part of the full server backup.

There are multiple ways that users can now protect the data held on their system, including cloud solutions such as OneDrive, Google Drive, Sync and MEGA. The benefits of this type of backup is that they happen in real time and are fully automated. 

Apple machines have 'Time Machine' as a built in app, this allows users to perform full and incremental backups of their computers. The real benefit of this app is that it not only restores the data but the applications, settings and operating system. 

<h3>2 - Discussion of the protection Windows Server Backup provides</h3> 

Servers often store vast quantities of data that businesses and organisations rely on to maintain their daily operations. Server Backup is capable of backing up data files, libraries, and desktops. Additionally it can be used to create a system image to restore the server in the event of failure.

Duplicating important information in a remote location helps protect against:

- Computer crashes which can lead to data loss
- Virus infections designed to corrupt files of disable computers
- Hard drive failures due to end of life
- Physical damage, more likely to occur with laptops
- Theft which can lead to data loss if the machine is not recovered

If events like those described occur then it is important for organisations to regain operational effectiveness as soon as possible to prevent disruption to services that prevent fulfillment of their obligations. Backups reduce the consequences resulting from human error and improve the ability to implement disaster recovery.

Best protection is offered when backups are automated and occur on a regular basis, this can be as often as every day on a network, or weekly or monthly on a personal PC depending on the circumstance of use. The greater the passage of time the larger the amount of data loss that can occur. Multiple copies should be created to provide additional insurance, a further benefit of multiple copies, particularly when in different forms, is the added flexibility in recovery options. 

Data backup offers a company or organisation protection from data loss, this could be in the form of customer or employee information, financial transactions which must be retained in a regulatory capacity, and operational reports or strategic projections. 

I have experienced significant data loss in business and it has taught me the value of data back ups. In my first job posting in claims handling the database suffered a catastrophic failure which caused a loss off all the data for thousands of client cases. There was no backup procedure, possibly due to the timing being mid-2000, but also because it was a small businesses with limited resources. On this occasion printed reports had been produced that allowed for the manual input of client data back into the system, but the information was not complete. In addition this manual process was incredibly time consuming leading to a significant drain on employee resources.

<i>References</i> 

Backup of Data & Files – Why it is Important? (n.d.). Retrieved September 16, 2020, from [https://www.bullguard.com/bullguard-security-center/pc-security/computer-threats/backup-of-data-files-why-it-is-important.aspx](https://www.bullguard.com/bullguard-security-center/pc-security/computer-threats/backup-of-data-files-why-it-is-important.aspx)

Brandon Lee. (2019, June 27). Windows Server Backup: Installation, Features and Limitations. Vembu.Com. [https://www.vembu.com/blog/windows-server-backup-installation-features-limitations/](https://www.vembu.com/blog/windows-server-backup-installation-features-limitations/)

What Is Backup & Recovery? | Why It’s Important | Concepts | NetApp. (n.d.). Retrieved September 16, 2020, from [https://www.netapp.com/us/info/what-is-backup-and-recovery.aspx](https://www.netapp.com/us/info/what-is-backup-and-recovery.aspx)

What is Backup and Recovery? - Definition from Techopedia. (n.d.). Techopedia.Com. Retrieved September 16, 2020, from [http://www.techopedia.com/definition/24058/backup-and-recovery](http://www.techopedia.com/definition/24058/backup-and-recovery)

Windows Backup vs. Professional Backup Software. (n.d.). Retrieved September 16, 2020, from [https://www.acronis.com/en-us/articles/windows-backup/](https://www.acronis.com/en-us/articles/windows-backup/)
