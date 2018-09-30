---
layout: post
title: Experimenting with the next version of the internet
tag: 
---

I can't start working with IPv6 without thinking of the beginning of The Hitchhiker's Guide to the Galaxy.

"\[The Address\]space is really big. Really big. You just won't believe how vastly, hugely, mindbogglingly big it is."

I'm too impatient to wait for my ISP to implement IPv6 and I got bored of playing with Teredo so I started dabbling with 6to4 and then 6in4. It's all very confusing, so a bit of background might be useful.

Skimming over the details, IPv6 is an upgrade to one of the main foundations for the internet and networking in general. It allows for approximately 2^128 different devices to be able to communicate with each other, which should be a large enough number to keep us going for a while…! Unfortunately, it's a little tricky to convince everything on the internet to start using the new system as it's not backwards compatible with the old one (IPv4). The closest technology analogy is probably the change in area codes in the UK telephone system. When London was running out of phone numbers, they changed the area code and for a while the old one and the new one would both work. Then after a while only the new one worked and the old one played you a message telling you to use the new one. This upgrade is more like "we've invented a new kind of phone, so until enough people use it you'll have to have two". This is what's referred to as a "dual-stack" setup.

There are services out there though to make the transition easier. Ideally you want the company that provides your internet to support IPv6, as then they will allocate you an address and make sure everything runs smoothly. ISPs don't seem to be in a rush to do that though. IPv6 was finalised as a specification in 1998 (yes, 17 years ago) and currently accounts for at most 6% of internet traffic worldwide. In order to make the transition easier there are 3 widespread "shims" that help you get started on IPv6 before your ISP is ready. They all involve sending IPv6 packets inside IPv4 packets, and they only differ really in where the transition between the two versions happens.

#Teredo

Teredo is built into Windows from XP SP2 onwards, and configures itself automatically. Your computer is responsible for putting the IPv6 packet inside the IPv4 packet and sending it out onto the internet to a relay. This relay will extract the IPv6 packet and sent it natively across the internet to its destination. For the return journey, the IPv6 packet comes back via a relay (not necessarily the same one it went out with) and then the IPv4 packet gets sent back to your computer.

#6to4

6to4 is usually configured at the router level, and works in a similar manor to Teredo but because there are less firewalls in the way it is usually more reliable. Your computer sends IPv6 packets to the router, which puts them inside IPv4 packets and sends them to a relay. The rest of the journey is the same as Teredo and the router unpacks the returned IPv6 packet and sends it back to your computer. In this instance your computer doesn't know that the traffic is being converted to IPv4.

#6in4

6in4 requires some configuration to set up, as it uses specific tunnels rather than general purpose public relays. The transition still happens at the router but rather than being sent off to a random relay on the internet it is sent to one that you've got an account with. When the IPv6 packet is on its way back it gets sent back to the same relay. This means that there is a bit more predictability and better reliability for the connection.

I've spent quite some time playing with Teredo, but recently purchased a router that supports handling the improved IPv6 workarounds and I've now got a "dual-stack" (IPv4 and IPv6) network working. I'm still working out the security, as now every device on my network (including things like my phone) have a publicly routable IP address but the router seems to do a good job of blocking everything by default. The addresses are a lot harder to remember (2001:470:1f09:7fc:2447:28da:c7d3:2e6c instead of 192.168.1.122) but it seems like a small price to pay. It also means that I can connect 18,446,744,073,709,551,616 devices to my network now before I need to apply for another address range!

All I need now is for my ISP to support it properly so I don't need to go through a tunnel!