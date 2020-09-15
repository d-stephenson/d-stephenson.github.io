---
layout: post
title:  "Journal #Fourteen [SEC602]"
author: Dale Stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J14.jpeg
featured: true
hidden: true
---
<i>Data Encryption</i>

JOURNAL #FOURTEEN [SEC602]

<h2>Data Encryption</h2>

<h3>1 - Summary of the functions of BitLocker</h3> 

BitLocker Drive Encryption offers disk encryption for entire volumes, it protects data against direct theft and/or loss and extends to hard drives where procedures have not been correctly followed in relation to proper decommissioning.

BitLocker is a built-in integration within the Windows operating system, however the greatest level of protection is provided when used with a Trusted Platform Module (TPM) v.1.2 or greater. BitLocker is included on Microsoft Windows 10 Professional and Enterprise, 8, 7, Vista and Server 2008 and higher, it allows administrators to encrypt and decrypt the disks either with the assigned credentials or via the system generated recovery key. 

Online backup solutions such as MEGA use a similar process to encrypt your data that they store, an account is created and users can select which files and folders they want to backup and sync. Access to this information is either locally on the PC or through a web browser by entering the assigned credentials, if a user loses their password they lose their data.

However, a recovery key is produced by MEGA that the user must securely store, this is the only access method should a user forget their login information. MEGA recommends this recovery key be printed, stored in a password manager or on a USB key.

<h3>2 - Discussion of the protection BitLocker provides the user</h3> 

BitLocker uses the AES encryption algorithm with a 128-bit key by default, a higher level 256-bit key can also be used to protect data from threats actors. Access to data or changes to data is only possible via the user credentials or the recovery key. 

There are several authentication and multi-authentication methods available, including:

- TPM only: Weaker if the threat actor has access to the full computer
- TPM + PIN: Encryption key released only after entering the PIN
- TPM + USB Key: Requires both TPM and USB for system boot
- TPM + PIN + USB Key: Requires all three methods, but the security benefits are not sufficiently greater than TPM + USB Key
- Password only: Can allow for brute-force attacks as there is no enforceable limit 

As mentioned, to get the best results from BitLocker, TPM should be utilised in combination. A computer would need to have a TMP chip that enables the support of advanced security features, BitLocker can however, be used without a TPM chip through a software based encryption, this method will require further authentication. A suitably strong password should be used, especially when deploying BitLocker without TPM. 

According to Microsoft BitLocker has no back doors, however it is a closed-source program so there are no guarantees that it maintains complete privacy. Users have no way of knowing if vulnerabilities exists or if back door access is provided to government agencies.

BitLocker is considered an effective solution for protecting data on hard drives, being both secure and convenient. However, if a threat actor has access to the entire computer the drive will be unencrypted if Secure Boot conditions are met, leading to several vectors of attack including RAM imaging via a Thunderbolt attack, extracting windows passwords or online accounts, or obtaining the recovery key from a Microsoft account. 

<h3>3 - How should the Recovery Key be securely stored</h3> 

Most of us can admit to being guilty of storing password or keys on word documents, text editors and even sticky notes on our monitors, some of use may still be guilty of this, but a recovery key needs significantly more security consideration.

There are numerous reasons to keep a recovery key. Instances occur where a password might be lost or forgotten and without the recovery key the encrypted data could not be accessed, additionally an employee may leave a company taking the password with them - these scenarios make the recovery key a vital tool.

The safest place to secure a recovery up key would be in a hardware encrypted storage device such as separate drive not on the network, or secure USB. Other solutions include traditional pen and paper secured in a locked safe, or on a modern password manager. In an organisation strict policies would need to be in place to ensure access restrictions and location storage information. 

<i>References</i> 

Dailies—The Secure Transport Use Case | SecureDrive.com. (n.d.). SecureDrive. Retrieved September 15, 2020, from [https://www.securedrive.com/solutions/bitlocker](https://www.securedrive.com/solutions/bitlocker)

Dansimp. (n.d.). BitLocker (Windows 10)—Microsoft 365 Security. Retrieved September 15, 2020, from [https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-overview](https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-overview)

Introduction to BitLocker: Protecting Your System Disk. (2020, January 20). ElcomSoft Blog. [https://blog.elcomsoft.com/2020/01/introduction-to-bitlocker-protecting-your-system-disk/](https://blog.elcomsoft.com/2020/01/introduction-to-bitlocker-protecting-your-system-disk/)

Paul, I., Contributor, Aug 1, Pcw. |, & hassles, 2016 2:27 pm PDT About | Smart fixes for your PC. (2016, August 1). A beginner’s guide to BitLocker, Windows’ built-in encryption tool. PCWorld. [https://www.pcworld.com/article/2308725/a-beginners-guide-to-bitlocker-windows-built-in-encryption-tool.html](https://www.pcworld.com/article/2308725/a-beginners-guide-to-bitlocker-windows-built-in-encryption-tool.html)

Randall Vu. (2018, November 6). Microsoft BitLocker function in Windows 10/8/7. Windows Bulletin Tutorials. [http://windowsbulletin.com/bitlocker-function-in-windows/](http://windowsbulletin.com/bitlocker-function-in-windows/)

Setting up BitLocker Drive Encryption on Windows 10. (2016, July 5). Windows Central. [https://www.windowscentral.com/how-use-bitlocker-encryption-windows-10](https://www.windowscentral.com/how-use-bitlocker-encryption-windows-10)
