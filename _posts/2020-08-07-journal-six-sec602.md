---
layout: post
title:  "Journal #Six [SEC602]"
author: d-stephenson
categories: [ SEC602, Journal, Systems Security ]
image: assets/images/SEC601-J6.jpeg
featured: true
hidden: true
---
<i>Encryption and Hashing</i>

JOURNAL #SIX [SEC602]

<h2>Encryption and Hashing</h2>

In the first class session this week we performed a really useful practical enactment of how key exchanges work. I personally find these visual displays really useful when clarifying my understanding of a subject matter.

Discussion then focussed on public key infrastructure and how this is trusted, I wasn't fully aware of how this worked in practice before the class and it has cleared up a lot of gaps in my knowledge.

So, moving on to Lab 6 and looking at to how we can check MD5 and SHA1 hashes, and where they can be used:

<h3>Q1 - Discuss the use of MD5 hashes.</h3> 

MD5 <i>(message-digest algorithm 5)</i> was created as a cryptographic hash function. For context, MD5 has a hash value of 128-bit and has been a commonly used hash function since it was invented in 1991 by Ronald Rivest.

The purpose of the algorithm is to take random text or binary data, which can be any length, and use it to generate a hash value with a fixed 32 digit hex length.

The following is an example of how an MD5 hash function would convert the string input into a fixed length hash:




Each time an MD5 hash is used it is unique, this is the case for every file. The result is that the MD5 hash can uniquely identify one specific file from another, even if they are the same file type and size.

<i>Reference:</i> [What is MD5 Hash and How to Use it, https://www.gohacking.com/what-is-md5-hash/](https://www.gohacking.com/what-is-md5-hash/)

MD5 is a widely used algorithm but not in the way it was originally intended. It was discovered that the algorithm suffered from extensive vulnerabilities. The inherent vulnerabilities were famously exploited in 2012 by the Flame malware attack, where it was used in collision attacks where it generated identical hashes. This was the first such instance of an MD5 attack being used maliciously in a real-world scenario. 

<i>Reference:</i> [Crypto breakthrough shows Flame was designed by world-class scientists,  https://arstechnica.com/information-technology/2012/06/flame-crypto-breakthrough/](https://arstechnica.com/information-technology/2012/06/flame-crypto-breakthrough/)

Despite these problems it still has practical uses. The algorithm is used as a checksum in order to verify the integrity of data against unintentional corruption, or for other non-cryptographic purposes such as:

- check the integrity of data for problems resulting from packet loss leading to corruption, this can happen when files are downloaded from the internet
- check on files that may have been corrupted as a result of other non-malicious actions to the files prior to any attempted download
- check on files to determine if they have been  maliciously tampered with in order to attack a system or network 
- check to determine if files have be removed and replaced with new files which can also be used to attack the target system 

These checks are useful because they provide assurances that files transferred are intact, this is done through the use of the checksum as a comparison tool. Both unix-based operating systems and Windows include sum utilities, for example in Windows these can be run through Powershell.

Earlier uses of MD5 included the storing of one-way hash passwords and unique document identification. However, as a result of the Flame attack these uses are no longer recommended. The best advice is to use more secure hash functions such as Secure Hash Algorithm (SHA1) which has a length of 160-bits.

<i>Reference:</i> [MD5, https://en.wikipedia.org/wiki/MD5](https://en.wikipedia.org/wiki/MD5)

<b>Conclusion</b>

MD5 is now considered a weak security algorithm and not best placed to be used for security purposes. Despite this other uses for the algorithm have been found that still makes it relevant, even if it is no longer serving its intended purpose.  