---
layout: post
title: Memetest86+, and the demise of memetest.org
comments: true
---
# Background
Back in 2015, when [Twitch Plays Pokémon](https://en.wikipedia.org/wiki/Twitch_Plays_Pok%C3%A9mon) was coming off its popularity (well, I guess that was 2014), and numerous spin-offs were created allowing Twitch to play a variety of stuff. One such spin-off was [Twitch Installs Arch Linux](https://www.twitchinstalls.com/), where Twitch chat tries to install Arch Linux in a virtual machine. 

Of course, one of the most fun parts of Twitch Plays Pokémon was the fact that Pokémon could be played in total anarchy, with commands from twitch chat being performed in the order they happened to come in. The events that happened as a result of this anarchy spawned a [whole series of lore](https://www.reddit.com/r/twitchplayspokemon/wiki/lore_red) that's worth checking out, if only for nostalgia's sake.

Of course, this total anarchy meant that actions requiring a specific sequence of button presses were almost impossible to perform, as an errant button press (for example, the infamous Viridian City Gym ledge or the Route 22 ledge) could send Red into a place where he would have to start all over. Of course, this prompted the Twitch Plays Pokémon devs to add a Democracy mode (which was often DoSed by people spamming start9 to freeze Red in place). Since there are a lot more possible inputs when installing Arch Linux, Twitch Installs Arch Linux exclusively used a form of Democracy to decide its next action.

# Memetest86+
Of course, even with users voting on the next command, chaos was bound to reign. 

On the Arch Linux live CD (when booted in BIOS mode), the bootloader offers a memory test, as is standard on many Linux live CDs. However, in the chaos of voting (as well as trolling by some voting blocs or botnets), often this option would get selected instead of one of the boot options. Since this happened quite frequently in the early days (when botnets weren't trying to [install Gentoo instead](https://linux.slashdot.org/story/15/11/02/0125246/botnet-takes-over-twitch-install-and-partially-installs-gentoo)), people started typing "memtest" over and over again, some even corrupting it to memetest. I think one of the main inspirations for me to create Memetest was a tweet (since deleted) that went something along the lines of, "Memtest, more like memetest."

Thus, I forked Memtest86+ (not to be confused with the closed-source [Memtest86 by Passmark](https://memtest86.com)) and created a [simple website](https://memetest86.org/index_old.html) (yes, it's an eyesore). I also got one of my friends, [Zhuowei](https://twitter.com/zhuowei) on board, and we set out to integrate as many memes as we could into Memtest86+. 

I'll be honest, Zhuowei did most of the work, adding Pepe the Frog to the background, and porting over a PC speaker player routine into Memtest86+'s initial startup and having it play Darude Sandstorm (Note: the reason why we can't have Darude Sandstorm while memtest is running is because the play routine required interrupts, which obviously would mess with memtest). He even did the more modern site redesign (including many, many memes, since he definitely follows them a lot better than I do--I honestly only understood all of the memes on the site several years later...), which is probably the version of the page you saw, if at all. My contributions were mostly text-related changes (for example, changing "Cache" to "Ca$h", where the most difficult challenge was to fix the text padding). 

Once this was finished, the community reboot of Twitch installs Arch Linux, [Twitch in the Shell](https://web.archive.org/web/20200611231223/http://twitchintheshell.com/), added a goal to boot Memetest86+ on the VM, which was actually [achieved on November 3, 2015!](https://www.youtube.com/watch?v=7tUGtroVWSM)

# The demise of memetest.org
After booting memetest was achieved, we didn't have any further plans for Memetest. Both Zhuowei and I went on to do other things. We both finished up uni, and are well into our careers building other, cooler things. I kept paying for the domain, and I honestly intended to keep it for a long time. I found the name amusing.

However, in November 2021, I missed every renewal email, and didn't have autorenew set up on my domains. I only noticed far later, in August 2022, that some of my domains had expired, including memetest.org. Thus for the first time in 7 years, Memetest86+'s website went dark. This is purely on me, and I should have been monitoring my domains more closely. Ironically, it seems like Twitch in the Shell's domain has suffered the same fate after 2020.

## A revival: memetest86.org (purely for archival purposes)
I've migrated the website from my DigitalOcean droplet to GitHub Pages, since it was honestly a static site, and hosting it on a VPS backed by CloudFlare was definitely overkill ([among other reasons](https://twitter.com/keffals/status/1560389687566630913)). I've also registered another domain, since someone seems to have snapped memetest.org up when I let it expire. If you're interested, you can visit [https://memetest86.org/](https://memetest86.org/) to relive 2015, though honestly some of the memes probably wouldn't be in good taste in 2022. It's purely up for historical/nostalgic reasons, a reminder of simpler times. 

# Epilogue
If the new owner of memetest.org is reading this, I'd appreciate if you instead pointed it back at [https://memtest.org/](https://memtest.org/). Memetest was just a one-off joke, and helping people who made typos trying to find memtest86+ is probably more important anyways.
