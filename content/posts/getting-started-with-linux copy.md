---
title : 'Breaking Into Apple’s Walled Garden (Almost)'
summary : "I didn’t set out to fight the system, but here we are."
date : '2025-08-18T23:59:15+05:30'
author: "Samay Kumar"
draft: false
showToc: true
TocOpen: true
---
### Introduction
All I wanted was simple solution to a bigger problem:  
**Develop and run my own app on my own iPhone without paying Apple a dime.**

If you’ve ever tried developing for [iOS](https://developer.apple.com/ios/), you know how locked down the ecosystem is. Unlike Android, where you can just download and install an APK, iOS has always been about control. Apple decides what goes in, and unless you pay $100/year, own a Mac, to test and follow their endless rules—you’re stuck.

That’s fine if you’re a big company. But for students, indie devs, or hobbyists on Windows/Linux, it feels impossible.

And yet, I found a way.  
Not a perfect way. Not a sustainable way. But it just works.

---
### The Early Days of Sideloading
My journey started with something very non-serious and personal: **removing ads from YouTube on iOS.**

On Android, we have _coughs_...[_ReVanced_](https://revanced.app/) and other mods. On iOS? Things weren’t so easy. I stumbled upon sideloading and thought it meant jailbreaking at first. Turns out—it didn’t.

I grabbed some cracked `.ipa` files (basically iOS’s version of `.apk`) but had no idea how to install them. That’s when I entered the chaotic world of sideloading tools: [**Sidestore**](https://sidestore.io/) (which didn’t work), [**Sideloadly**](https://sideloadly.io/) (with no Linux support), [**Sideloader**](https://github.com/SideStore/sideloader) (almost worked) and finally [**AltStore**](https://altstore.io/) + [**AltServer-Linux**](https://github.com/NyaMisty/AltServer-Linux) which brought some magic with more problems along the way.

AltStore was a revelation but only when you understand its working. But then came Apple’s infamous **3-app limit.** I tried hacking around it: running multiple Docker containers, different Apple IDs, even modding AltStore into “AltStoreX”, just to bypass the limit.

Still after days of `.plist` editing which itself was pain, especially when binaries get messed up, I got two different AltStore instances working independently on one device… only to realize the 3-app limit is tied to the **device itself**, not the Apple ID. Brutal.

Eventually, I discovered [**TrollStore**](https://github.com/opa334/TrollStore), which exploited a vulnerability (like [**macdirtycow**](https://github.com/dora2-iOS/macdirtycow-exploit)) to bypass refresh limits entirely. No 7-day expiry. No re-signing. It was glorious.

_(Caveat: TrollStore only works on specific iOS versions/devices.)_

---
### The Real Problem
Sideloading mods was fun, but the real problem hit me when I started working on my own app:  
[Sparklines Mobile](https://github.com/samay15jan/sparklines-mobile), a music streaming app built with **React Native + [Expo](https://expo.dev/)** (unfinished and might never be anyways).

On Android, Expo’s [**EAS build system**](https://docs.expo.dev/eas/) worked flawlessly. I could build an `.apk` and install it in minutes.  
On iOS? Different story.

- Simulator builds only, not real `.ipa`s
    
- Need a paid [Apple Developer Account](https://developer.apple.com/programs/)
    
- Need [macOS](https://www.apple.com/macos/) + [Xcode](https://developer.apple.com/xcode/) for building, and a specific iOS device to test it
    
- and distribution is impossible too
    

As someone on Linux, that was a dead end. But then I had a thought:  
**What if I could just get an unsigned `.ipa` and sideload it manually?**

Apple wants that to happen only on macOS. Challenge accepted.

---
### The Breakthrough
While digging around, I noticed projects like [**uYouPlus**](https://github.com/qnblackcat/uYouPlus) and [**EeveeSpotify**](https://github.com/whoeevee/EeveeSpotify) were building `.ipa` files using **[GitHub Actions](https://docs.github.com/en/actions)** on macOS runners.

That’s when it clicked:  
**Why not do the same for Expo apps?**

I spent hours fighting with YAML configs, debugging failed builds, and experimenting with different workflows. Eventually, I managed to get GitHub’s macOS runners worked the way I wanted and generate an unsigned `.ipa` and sideloaded with AltStore/TrollStore.

Guess what ? It worked.  
I had my own React Native app running on my iPhone—no Mac, no paid Apple account, nothing.

Sure, crashes were ugly (probably because I hadn’t set up error boundaries properly within my application codebase), but native modules worked fine. It felt surreal.

---
### The Tool That Could Have Been
At this point, I considered turning the whole process into a tool. Maybe:

- A **CLI** to auto-generate the GitHub Actions workflow
    
- Or a **web app** frontend where you could link your GitHub account and upload code, and it spits out an `.ipa`. Something like [**Vercel**](https://vercel.com/) for mobile apps.

> PS: There are things like [webmuxd](https://github.com/hack-different/webmuxd) which could be a game changer. 

Basically, a free alternative to Expo’s paid EAS service—but for people who just want to test and learn without Apple’s gatekeeping, legally and ethically, and for personal use only.

I had some ideas and minimal executional logic… but never turned into something real. And maybe i didn’t even need to anymore. I was already moving away from iOS.

Still, I pushed what I had to GitHub: [**Altux**](https://github.com/samay15jan/Altux)  
You could refer to GitHub Action template and README file in the repository for some nitty gritty, behind the scenes working.  
If anyone wants to build on top of it, go ahead.

---
### Conclusion
This whole thing started because I just wanted to test an iOS app without paying Apple. And in the process, I learned a lot about sideloading, CI, and Apple’s walls.

I’m not maintaining this project, and I’m not sticking with iOS either. But maybe this little experiment will help students, indie devs, or tinkerers who just want to learn without paying $100/year for the privilege.

Apple may have a walled garden, but sometimes a crack in the wall is all you need to learn, build, and experiment. Altux was mine. Waiting for yours...