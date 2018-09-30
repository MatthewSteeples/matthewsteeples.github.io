---
layout: post
title: Fishing for Errors - 0x80073b01
tag: 
---

I'm posting this in the hope that it helps anyone (or at least myself in the future when I've forgotten that I've had this problem previously).

There's an error in Windows (one in particular) with the rather fetching name of 0x80073b01. It's not a common error, and the majority of people seem to have experienced this when dealing with Windows Defender. I encountered it today not when dealing with Defender, but instead with BITS (Background Intelligent Transfer Service). For those of you unfamiliar with this service (which is going to be most of you) it happily sits in the background (as the name suggests) and downloads files. Windows Update uses it to fetch all of the updates every month. The idea is that it takes a look at how much bandwidth you have to the internet and backs off to make sure it doesn't use all of it.

I use it through Powershell (Start-BitsTransfer) when downloading large files as it automatically resumes the download a certain number of times so it's like having a build in download manager in Windows.

Today I tried downloading a file and was given that error. I'm not sure if this is the correct resolution for it, but when I specified explicitly that the command shouldn't use a proxy server (-ProxyUsage NoProxy) it happily downloaded the file.