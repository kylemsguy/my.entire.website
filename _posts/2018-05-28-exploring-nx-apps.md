---
layout: post
title:  "Exploring Splatoon 2's RomFS"
date:   2018-05-17 02:30:00 +0900
categories: switch hacking splatoon
tags: dedf1sh romfs dumping nintendo octo-expansion
published: false
---
After I saw [SplatoonJP's tweet](https://twitter.com/SplatoonJP/status/998488945695440896) about the new character dedf1sh their music, I remembered OatmealDome's tweet about Splatoon 2 Octo Expansion's Mission clear theme ([Click here for the tweet](https://twitter.com/OatmealDome/status/992620498721935361) Note: light spoilers). I wondered if this new music was already included in the Splatoon 2 update files (as of this writing, ver. 3.0.2). Instead of messaging one of the Splatoon 2 modders/dataminers, I decided (with some encouragement from my friend [Zhuowei](https://twitter.com/zhuowei) to begin exploring how one dumps and modifies Nintendo Switch games.

Just a note before we continue: everything I'm about to talk about is derived from publically-released information, and this information is provided for entertainment and educational purposes only. I do not condone hacking for online multiplayer, or for the purposes of piracy. What you choose to do with this information is your responsibility. I will not be providing any keys or any dumps, and any requests for these will be ignored.

Now that we have gotten that out of the way, on to the... adventure. This particular post is probably going to be more of a commentary on the current state of Switch hacking, since Fusée Gelée (aka shofel2; the exploit that works on all current systems) is quite new, and can be difficult to exploit. I will be detailing my entire process of exploiting the system, dumping the NAND, decrypting the NAND, finding the titles, decrypting the titles... yeah this is going to be complicated. And keep in mind, tutorials for doing this kind of thing are few and far between, so this post might also end up being a tutorial on how to dump titles, especially Splatoon 2. We'll see. (Stick around to the end.)

The first thing we need to talk about is how to obtain the title data. After a discussion with [Zhuowei](https://twitter.com/zhuowei), we agreed that the simplest way would probably be to make a NAND dump of the system, and decrypt/dump data from that, since tools seemed to exist to do that sort of thing. The tools in question are, Hekate-ipl (Bootloader and CFW), biskeydump (key dumper), HacDiskMount, and hactool. Let's go over these tools.

## Tools used
- **Hekate-ipl**: Allows us to dump the Switch's eMMC memory and bootloader. Also lets us boot custom firmware that supports the Homebrew Launcher, which lets us run code to grab the path to titles on 5.0+ (will become important later)
- **biskeydump**: Allows us to dump the encryption keys used to encrypt the various partitions on the Switch's NAND.
- **HacDiskMount**: Allows us to decrypt and mount the Switch's partitions as FAT32 partitions, or alternatively, to dump the entire partitions to a file.
- **hactool**: Allows us to decrypt the .nro files we extract from the NAND backup.

## Earlier attempts
