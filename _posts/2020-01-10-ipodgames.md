---
layout: post
title:  "Attempting to preserve iPod Games"
date:   2020-01-10 00:16:00 -0800
categories: general
published: false
---
Disclaimer: I have no idea what I'm doing, but I do have some understanding of assembly. And the NSA gave us Ghidra. Let's put those to use.

iPod Click wheel games seem to be the long-forgotten part of iDevice history. When I received my iPod nano

I managed to track down a torrent of the hacked 5/5.5g firmware (along with iPodWizard and the released cracked games), so I decided to look into what exactly was patched. After some digging around on archive.org versions of the iPodLinux website, I managed to find the source of make_fw, and extracted the retailos files from the iPod 5/5.5g ipsws.

I loaded these files into Ghidra (thank NSA) and started diffing the 5g 1.2.1 firmware with the hacked one (the 5.5g 1.2.1 hacked firmware has the iPodLinux bootloader in it, so I wasn't sure what was actually related to the patch, and what was related to the crack xP), and I found some interesting differences in it. 

1. at the beginning of the firmware (offset 0x24, probably some exception vector or something), a multiple register load instruction (that I have been unable to find the definition of on Google) has been replaced with a software interrupt instruction. No idea what this means since I'm not familiar with ARM assembly.
2. Much farther down in what looks like a function, there's a bunch of bne (branch if not equal to) instructions that have been patched to be `mov param1, param1`, which seems like a no-op. I wonder if that function serves to do some verification of iPod games?

Otherwise, I cannot see any other significant differences between the two firmware files. I wonder if I patch these instructions into the 1.3 firmware, I'll be able to 

http://www.ipodlinux.org/Firmware.html#Firmware_Partition_format