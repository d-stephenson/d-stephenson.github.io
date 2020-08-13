---
layout: post
title:  "Journal #Seven [SEC602]"
author: d-stephenson
categories: [ SEC602 Systems Security ]
image: assets/images/SEC601-J7.jpeg
featured: true
hidden: true
---
<i>Password Cracking Tools</i>

JOURNAL #SEVEN [SEC602]

<h2>Password Cracking Tools</h2>

Today's class session looked at password authentication and several protocols that can help keep systems and networks secure. Specifically we reviewed:

- Lan Manager (LANMAN)
- NT Lan Manager (NTLM)
- Kerberos
- Password Authentication Protocol (PAP)
- Challenge-Handshake Authentication Protocol (CHAP)
- Extensible Authentication Protocol (EAP)

I am still surprised by how much system security relies on the steps taken by the users. Simple actions such as using longer more complex passwords, different passwords for different accounts, secure password managers and dual factor authentication are just some of the steps that can prevent you being a victim of a password hack.

The Lab looked at the other side of this discussion, how attackers make use of specialist tools to attempt to crack user passwords:

<h3>Q1 - Discuss how to use Cain & Abel to initiate a brute force attack.</h3> 

Cain and Abel is a tool who's purpose, amongst other features, is to hack software. Specifically it is used for password cracking, network sniffing and to hack websites. Hackers are able to utilise the package to exploit flaws in order to reveal passwords and gain access to systems and networks. 

There are several ways to crack a password including:

- Dictionary attacks
- Cryptanalysis attacks
- Brute force attacks

Because passwords are the most common authentication method used, a password crack is the most convenient tool with the intention of accessing a system or network. 

It is surprising simple to initiate a brute force attack using Cain and Abel. The user interface has a logical layout and for the most part is simple to navigate.

<i>Reference:</i> [Cain and Abel Software Download, https://softfay.com/windows-browser/cain-and-abel-software/](https://softfay.com/windows-browser/cain-and-abel-software/)

The brute force attack is performed from the 'Cracker' tab. The first step is to display the users of the system that will be the victims of the attack. This is done by importing hashes from a local system, alternatively hashes can be imported from a text file or SAM database. For the purpose of this Lab the exercises utilised the two former methods. 

For this example we are going to look at the process based on importing hashes from a local system.

Once the import is complete the system will display the various users on the network, along with other data including but not limited to the following:

- User Name
- LM Password
- NT Password
- LM Hash
- NT Hash

The results for each account return either '* empty *', which tells use there is no LM, or NT password - or it will return a blank field which indicates there is a password on the account.

The hacker will now select which account they want to hack, to do this you simply right click on the account and select 'Brute Force Attack', followed by NTLM Hashes (in this particular Lab scenario).

A new dialogue box opens which allows the attackers to select the 'Predefined' value and adjust the min and max password length. For the purpose of this Lab we used a password string that included upper and lower case letter in addition to numbers, followed by a password min equal to one and a max equal to eight.

The hacker then starts the attack. In this instance the attack was estimated to take several days to rotate through all the possible character combinations in order to determine the correct password used on the account. 

Obviously we didn’t have 3 days to run the attack scenario, but for a determined hacker, three days might be worth the wait. Depending on the reason for the attack the reward might far out way the wait. 

<h3>Q1 - Discuss the problems with using the brute force attack and compare and contrast with another password attack.</h3> 

In the case of the Lab as discussed, the password crack was estimated to take several days, if a password uses lower case characters and no digits or special characters it can take as little as a few minutes. However, the problem comes when attempting to crack a more complex password, in which case it can take many years, even a decade or more. 

This is obviously not practical, during such a long period of time it is highly probable that the password would be changed, the user might be removed from the system, or the network may not even exist any longer.

Additionally, the length of time a crack might take will also depend on the speed of the computer processor. The stronger the password the hacker is attempting to crack, the more processing power is required, and still the crack might take such a long amount of time as to make it unlikely to be attempted in the first place.

It is relatively simple to protect yourself from a brute force attack, use the following in any password to help you stay secure:

- Upper and lower case letters
- Digits 
- Special characters
- At least 8-10 characters long, the longer the better  

<i>Reference:</i> [Learn about Brute Force attack, https://tipsmake.com/learn-about-brute-force-attack](https://tipsmake.com/learn-about-brute-force-attack)

An alternative password attack would be a dictionary attack. A dictionary attack operates in a similar way to a brute force attack in that attempts to defeat a password by taking a systematic approach to crack. Instead of characters though, it uses dictionary words. The idea behind the attack is that many users deploy ordinary words as passwords, words that are ordinarily found in a dictionary. 

These types of attacks come with a separate set of problems, namely if multiple words are used in the password the crack will be ineffective. The same is true if the password contains a random use of lowercase and uppercase characters as well as digits. The drawbacks of a dictionary attack can be overcome by using the brute force attack. 

<i>Reference:</i> [Dictionary Attack, https://www.techopedia.com/definition/1774/dictionary-attack](https://www.techopedia.com/definition/1774/dictionary-attack)

Attackers will often create word lists when deploying a dictionary attack, for example they might look at:

- Variations of the users name or names of relatives or pets
- Other user details such as an address which can be obtained through social engineering
- Variation of the words, such as replacing 'o' with '0'
- Deploying common word pairs
- Words extracted from multiple databases which might include names, locations, films etc.

<i>Reference:</i> [What is dictionary attack and how to Prevent It?, https://www.zerosuniverse.com/dictionary-attack/](https://www.zerosuniverse.com/dictionary-attack/)

<b>Conclusion</b>

These types of cracks are surprisingly easy to implement, and it is clear why hackers might use them in order to carry out attacks. They aren't however foolproof - if system users follow readily available password security protocols like the ones discussed in today's class session, they are far less likely to succumb to this kind of attack.  