---
layout: post
title:  "Journal #One [NET603]"
author: d-stephenson
categories: [ NET603, Journal, Practical Network Development ]
image: assets/images/sub-net.jpeg
featured: true
hidden: true
---
<i>Sub-netting</i>

<h2>JOURNAL #ONE [NET603]</h2>

Learning Summary<br>

<h3>WHAT</h3>

Learning outcomes relate to converting decimal into binary, specifically with regards to sub-netting.

A Subnet Mask allows us to determine where within the IP address the network ends and the host, or client begins. The IP address is a set of decimal numbers that represent a conversion of a 32 bit binary number.

The 32 bit binary number is split into 4 octets each containing 8 of the 24 bits. Each bit represents either a 0 or 1, or to put it another way 'On' or 'Off'. 

<h3>WHY</h3>

We normally interact between networks using IP addresses which are represented as 4 octets, for example 192.168.1.1. An IP address however is not a real interpretation of what the computer understands, it is merely a representation that allows us to quickly and efficiently work with network systems.

In order to understand what is happening in real terms, that the computer understands, we have to convert the IP address into binary.

<h3>HOW</h3>

We need to covert each octet into binary, so in the above example we have 192.168.1.1. The decimal numbers to allow conversion always start on the right and begin with a 1, then double all the way up to 128:

<img src="/assets/images/sub-net1.png" alt="Sub-netting"><br>

So if we take the 192 we ask ourselves, does 128 fit into 192? The answer is yes so that is represented by a 1 in binary. Then we move onto the next number in the sequence and ask ourselves, does 64 fit into 192 after the 128 has been allocated to it? The answer is yes so that gets a 1 also. Those two numbers make the total 192 so the rest of the 6 digits are represented by a 0 leaving us with the 8 bit sequence of 0s and 1s.

So now how do we determine the Subnet Mask?

If we take an example network range of 192.168.1.0 > 192.168.1.255 where the first three octets represent the network and the last one represents the hos,t we have a total of 256 IP address, with 254 reserved for hosts machines. The reason there are 256 addresses is because we have a range between 0 and 255, so 255 + 0 = 256. The reason we have 254 hosts is because the first IP address, 192.168.1.0 is reserved for the network address, and the last 192.168.255.255 is reserved for the broadcast address.

So in the above example IP range we have a subnet mask of 255.255.255.0.

<img src="/assets/images/sub-net2.png" alt="Sub-netting"><br>

So because the decimals, when added together equal 255, means that converting the decimal to binary in this instance is simple, but how do we know where the network ends and the host begins?

This 'point' that distinguishes the network and the host is between the last 1, and the first 0. So the binary shows us that 255.255.255 represents the network, and the .0 represents the host or client machine/printer etc..

The subnet mask can be anywhere along the 32 bits, it operates in a sliding scale. So we can take a subnet mask of 255.255.240.0 which in binary is 11111111.11111111.11110000.00000000. This shows the network ending 4 bits into the third octet, or 20 bits into the binary in total.

This can be represented in the IP address by adding the '1' bit numbers representing the network to the end of the IP address as /20, because there are 20 '1s' in the bit sequence, for example 125.238.219.173 /20.
