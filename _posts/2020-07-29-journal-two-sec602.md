---
layout: post
title:  "Journal #Two [SEC602]"
author: d-stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J2.jpeg
featured: true
hidden: true
---
<i>Application Data - Establish Host Security</i>

JOURNAL #Two [SEC602]

<h2>Application Data - Establish Host Security</h2> 

Class sessions covered previous security topics in more detail. Specifically, we covered areas of malware such as:
 
- Adware and Spyware
- Viruses and Worms
- Ransomware and Crypto-currencies 
- Trojan and Remote Access Trojans (RAT)
- Bootkit
- Keylogger 
- Bots and botnets
- Logic Bombs
- Backdoor<br>
 
After considering the threat vectors we looked at the common vulnerabilities and what preventative steps can be taken including:<br>
 
- Host Security 
- User Security 
- Monitoring 
 
Taking a personal perspective, I have been surprised how much of a role is played in user security. Coming from a business background I held an assumption that the security of the technology systems primarily sat with the I.T. Team. In my career there has been little requirement for personal consideration for the security of the technology systems I have relied upon daily. 
 
In hindsight this has been in error, personal security measures can often be the first step in preventing data leaks and in mitigating other risks. I am reminded of an incident that occurred in the UK where an MI5 employee left their government issued laptop on a train - obviously, a huge security risk. In this case I believe the data was encrypted and the laptop recovered, but the consequences could have been severe if it made its way into the wrong hands. 
 
Moving onto the Lab, the tasks included looking at Exclusion features on Windows Defender and how they are implemented:

<h3>Q1 - Discuss when you may need to use the Windows Defender Exclusions feature from the lab.  What the security considerations or actions would you recommend or implement if you were asked to exclude a folder from Windows Defender.</h3> 

Windows Defender is a built-in antivirus package, initially as part of Windows 8 and continuing to Windows 10. The package was known in Windows 7 as Microsoft Security Essentials which was not built-in at the time, but instead offered as a separate download. 
 
<i>Reference:</i> What's the best Antivirus for Windows 10?, https://www.howtogeek.com/225385/what%E2%80%99s-the-best-antivirus-for-windows-10-is-windows-defender-good-enough/<br>
 
Studies have shown that Windows Defender is comparable to the paid solutions offered by competitors. 

In the past it was commonplace for organisations to pay for antivirus and anti-malware solutions simply due to the lack of quality free alternatives in addition to Microsoft not offering a service that provided sufficient protection.

Windows Defender and its competition have been tested by two separate testing houses, AV-comparatives, and AV-test. The outcome from both tests was extremely positive for Defender, coming out amongst the top products.<br>

<i>Reference:</i> Why you can stop paying for antivirus software, https://www.pcworld.com/article/3434097/why-you-can-stop-paying-for-antivirus-software.html<br>
 
Windows Defender takes a proactive approach to protecting a Windows 10 machine by running in the background, offering real-time protection. The operation of Defender means there are reasons a user may want to make exclusions to the scanning process including:
 
- Excluding files from being scanned to improve overall performance for tasks such as virtual machines or compiling code
- Assist with false positives, this can prevent Defender identifying legitimate files as malware<br>
 
It is important that users recognise that any excluded files will not be scanned by Defender. Consideration should be made to any potential risk before making any exclusions. 
 
<i>Reference:</i> How to Add Exclusions in Windows Defender on Windows 10, https://www.howtogeek.com/671233/how-to-add-exclusions-in-windows-defender-on-windows-10/<br>
 
There are alternative actions that can be implemented on a machine that can continue to offer protection to these files or folders after they have been excluded by Defender, including:
 
- Set Defender to run on a schedule that suits the needs of the user through Task Scheduler. This may negate the need to set up exclusions and therefore continue to offer full protection for the machine, 
- Running a free alternative to Defender, scheduled to specifically scan Defender excluded files and folders when the machine is not in use. This provides the user full protection and bypasses any performance issues. One of the benefits of Defender is that it will operate alongside other antivirus programs. 
- Use Defender to run an on-demand scan by defining the location for the scan and setting it to run manually. This would require the user to be proactive in running the scan on the excluded files or folders.
	 
<i>Reference:</i> How To Set Your Own Scan Schedule For Windows Defender Antivirus, https://helpdeskgeek.com/windows-10/how-to-set-your-own-scan-schedule-for-windows-defender-antivirus/ 

<h3>Q2 - Discuss a scenario when you may need to use the Microsoft Safety Scanner rather than Windows Defender.</h3>

Microsoft Safety Scanner might be used in a situation where a machine has already become infected with malware. Safety Scanner completely removes all the malware that it detects. It is useful when another anti-virus software has not worked, or the user is unable to download and install another anti-virus option.
 
<i>Reference:</i> Windows Defender compared with MS Safety Scanner Compared with Windows Malicious Software Removal Tool, https://answers.microsoft.com/en-us/protect/forum/protect_other-protect_scanning-windows_10/windows-defender-compared-with-ms-safety-scanner/e813d86b-5886-4ed2-b025-392a7d561559
 
Once Safety Scanner performs a scan it provides the user with a report which lists all instances of potentially harmful or malicious programs. Safety scanner allows the user to choose which antivirus program they use to remove the discovered malware. 
 
Defender is an incredibly capable alternative to Safety Scanner on machines running Windows 7 or higher. This means that Saftey Scanner should be used on all other applications of Windows to ensure these older operating systems maintain full protection. 
 
<i>Reference:</i> Microsoft Safety Scanner is a legitimate scanning software developed for the security of your computer, https://www.2-spyware.com/review-microsoft-safety-scanner.html

<h3>Q3 -Select a feature Internet Explorer Browser Security from the lab and discuss the vulnerability it is protecting, is this required just for Internet Explorer?</h3>

Let's discuss Pop-Blockers, not just because they protect us from harmful pop-ups, but because they reduce the amount of advertising material we are bombarded with on a daily basis, and as a result limit annoying distraction.
 
The real damage can occur from those pop-ups that contain material that is deliberately deceptive by appealing to the user in a targeted way, the ones that catch the eye despite your best efforts. These are successful precisely because they are targeted in a way that makes it difficult not to click and link to whatever is being offered. Something I think we can all admit to being guilty of at one time or another.
 
These pop-ups are problematic because the links contained within them can be malicious, and often it is difficult to determine whether they are genuine or harmful. Thankfully, most browsers including Internet Explorer, use filters which will detect and block pops-up without you having to turn on any settings or take any direct action.
 
There may however be instances where a user chooses to allow pop-ups from certain sites that are trusted and have been validated. In these instances, a user can allow pop-ups from these sites in order to continue using all the features and functionality offered.
 
<i>Reference:</i> How to block web page pop-ups, https://computing.which.co.uk/hc/en-gb/articles/207058655-How-to-block-web-page-pop-ups

<b>Conclusion</b>

The primary browser I use is Firefox for a range of reasons including its ability to block both pop-ups and pop-unders (those that appear underneath the browser instead of on top of the browser). 
 
Pop-up blocking in Firefox can be administered and controlled similarly to that in Internet Explorer. Firefox has been my preferred option due to a several security concerns specifically privacy, an area which I believe is becoming increasing important in an age where users hand over their data to large corporations with little or no consideration as to how that data is used or who may make legally questionable requests for that information, including but not limited to government agents. 
