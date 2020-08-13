---
layout: post
title:  "Journal #One [SEC602]"
author: d-stephenson
categories: [ SEC602 Systems Security ]
image: assets/images/SEC601-J1.jpeg
featured: true
hidden: true
---
<i>Social Engineering Reconnaissance</i>

JOURNAL #ONE [SEC602]

<h2>Social Engineering Reconnaissance</h2> 

Class sessions covered topics relating to the security and the protection of business systems. Specially the topics covered areas such as mitigating risk, protecting assets and compliance, which are areas I am familiar with from my career relating to legal and regulatory compliance in local government and financial risk in the commercial sector. 

Risk is an important mitigating factor for any organisation, particularly relating to assets and infrastructure. It is not just the obvious financial risk associated with exposure, but reputational issues that can result from data leaks that have plagued large organisations such as Sony, LinkedIn, Adobe, Marritot International, Yahoo and Equifax amongst others.

<i>Reference:</i>  The 15 biggest data breaches of the 21st century, [https://www.csoonline.com/article/2130877/the-biggest-data-breaches-of-the-21st-century.html](https://www.csoonline.com/article/2130877/the-biggest-data-breaches-of-the-21st-century.html)

Breaches in security are however not always at the technical level but can stem from a calculated practice of gathering information about a person from often quite open profiles such as social media accounts, job platforms and even personal web pages. 

It is important that internet users consider the information that is readily available about them, and while this is not always under their direct control, steps should be made to control how much and what information they publish online. 

This leads us to the first Lab, a fictitious online MyBook profile:

<h3>Q1 - Summarise the key information gathered from MyBook?</h3> 

Personally I have always been conscious about what information I choose to publish online, and found that limiting information to a 'needs must' approach far more palatable. 

A prime example would be allowing other users to contact me, where possible I only allow contact through an online form, negating the need to display either my email address or my phone number. However in the case of the fictious MyBook profile the user is quite open about displaying quite sensitive material including:

- A profile image of the user
- The full name of the user, the user may have a middle name however the first and last name would be sufficient 
- A preferred name the user is more familiar with 
- Occupation or field of work, this fluctuates across the profile
- Marital status and length of marriage as mentioned in the blog timeline
- Full name of the users wife
- Potentially expecting a child 
- Very recent vehicle breakdown, unlikely resolved 
- Place of work at Google
- Interests including playing the guitar, others as determined by the imagery and has a dog 
- Date of Birth 
- Telephone Number 
- Degree history and place of attendance
- Work experience history including employee names and time periods
- General address location 
- Spoken languages 
- Full names for friends and/or associates including job titles, they may reveal more information about the user that provides a more complete picture 
- User is active and has a large number of followers 

<h3>Q2 - Consider how the information gathered can be leveraged to attack an organisation?</h3>

The most obvious social engineering attack would be the practice of phishing. Phishing is commonly used to steal the data of internet users, using this information to increase the likelihood that they could get a user to open a malicious email, for example. 

This type of attack could lead to installing malicious software onto the users system in order to gain more sensitive data such as banking information, passwords to cloud storage accounts, online shopping accounts and even credit or debit card details. Alternatively malware could be installed leading to a system freeze and consequently a ransomware attack. 

These acts would be extremely harmful in themselves on an individual level, however should these be targeted to the individual at their place of work, the consequences and potential risk are far greater. There is potential that such an attack could lead to an instance such as an advanced persistent treat (APT), which can have consequences such as those discussed earlier in this journal. 

Common phishing attacks include fake emails ranging from mass distribution to password expiration instructions, which can either link to a fake web page or worse, the real intended web page but unknown to the user, a malicious script is running that gives access.

<i>Reference:</i> What is a phishing attack, [https://www.imperva.com/learn/application-security/phishing-attack-scam/](https://www.imperva.com/learn/application-security/phishing-attack-scam/)

In the case of the user in the Lab the following could be a result from gathering of the information readily available:

- A phishing attack could be generated from the car garage that is performing repairs, an email could be sent asking to rate the value of the customer service. The threat actor could achieve this by simply searching likely garages in the local area as derived from the blog, to find which garage is performing the work. Moreover the garage may freely give information if the threat actor impersonates the user. 
- The treat actor could look to impersonate one of the users friends specifically those in a position of significance at a company, such as a CEO under the pretense of asking for a copy of his CV, suggesting there may be a job opening and they would like to put the user forward. Commonly CVs include additional information such as an address or other contact information. With an address the threat actor may consider other attacks such as dumpster diving or as a way to build up trust by 'friending' the user on social media and relating common interests and local knowledge for the purpose of extracting further information. 
- The information gathered could be used in an attempt to reset passwords to online accounts such as cloud storage or emails, both of which could be a rich resource of further information gathering.
- The user has a dog, it stands to reason that the pet would have been micro-chipped or may have had cause to attend a local RSPCA or veterinary clinic. If this were the case it would be possible for the threat actor to use this information again to send an attack via email to the user. As the clinic would be entirely trustworthy it stands to reason the user would have no objection to trusting the source. 
- There may be potential attack vectors available through taking advantage of the users interests. By way of example vouchers or links to known local events could be used, the clever use of actual events would lead to the user trusting the attack but will also be instantly recognisable to the user.

<h3>Q3 - What prevention methods could be used to mitigate the risks of an attack?</h3>

In order for the user to mitigate the risk of being exposed to attacks as discussed there are several steps that can be taken:

1. Remain vigilant, any fake email of message will often contain subtle mistakes that can be easily identified if you know what to look for, these include domain name changes or domains that don't appear as expected. Spelling mistakes can also be a clue as often professional organisations will try their best to limit such errors. If you suspect foul play take another look or ask someone else for their opinion. 
2. Never click on links either by email or social media until you are confident that the source can be trusted, be particularly vigilant if the sender is asking for confidential information.
3. Enable two-factor authentication (2FA) wherever possible. If a threat actor does succeed in discovering login information, 2FA is proven to be incredibly effective at preventing unwanted access to sensitive online accounts. 
4. Limit the amount of personal information available through your global online presence. This extends to removing contact information of any kind, use forms instead, remove location maps giving away your general location and consider applying a 'needs must' approach to everything you reveal about yourself. 
5. Keep your social media timeline restricted to trusted friends, colleagues and family, consider, does the world need to see this information? Apply this principle to all online activity including images, your location, your work history and friends list. 
6. Use secure website when it is possible to do so, these are identified with the URL precursor HTTPs. This is particularly important when using a unsecured internet connection and when accessing personal information in the cloud, banking or shopping website which might require you to input credit card information should also be accessed securely.

<i>Reference:</i> 5 simple ways you can protect yourself from phishing attacks, [https://www.welivesecurity.com/2016/09/22/5-simple-ways-can-protect-phishing-attacks/](https://www.welivesecurity.com/2016/09/22/5-simple-ways-can-protect-phishing-attacks/)

<b>Conclusion</b>

I have personally not experienced an attack in a manner as described however, I have not had cause or a desire to actively use social media platforms and attempt to limit the information I  submit online to a needs must, particularly when using LinkedIn, being the only social media platform that does retain my information and which is currently set to private.

Should I make the account more open in the future I do intend to review the information and will perhaps take steps to change some of the more personal content if deemed necessary. 

Additionally, I consistently take steps to limit the amount of 'junk email' I receive by removing myself from email lists, this has the added benefit of making me question why I'm receiving such emails in the first instance, more often then not deleting them without having ever opened the email to review the contents. 

Despite this the exercise has led me to consider my sometimes flippant nature  when opening emails I believe I can trust without questioning it first and I am feeling compelled to review my LinkedIn to test whether or not I am practicing what I preach…
