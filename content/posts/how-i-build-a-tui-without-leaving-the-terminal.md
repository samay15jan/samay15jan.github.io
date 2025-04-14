---
title: How I Built a TUI Without Leaving the Terminal
summary: Sparklines TUI project showcasing the power of terminals.
date: 2025-04-14
author: Samay Kumar
draft: false
showToc: true
TocOpen: true
---
### What does TUI even mean?

Terminals are an overly complexified yet quick way to interact with the system and any task without leaving the terminal... ever. TUI stands for Terminal User Interface. Basically, it's a way to use some software features directly from the terminal with a user-intrusive interface, and use the keyboard to control everything.

I know you might not understand it at first, because terminals are complex in their own way. So, it’s a step forward.

> **PS**: In this article, don’t expect much of a learning experience, it's more about me showcasing a project I built for the terminal. And it’s definitely not gonna help you in your career ever. haha. So proceed wisely.

---

[![project-screenshot](https://raw.githubusercontent.com/samay15jan/Sparklines/main/TUI/demo.png)](https://asciinema.org/a/696484)

---

### Why TUI matters

We live in a world where everything is graphical, flashy, and requires 12GB of RAM to open a note-taking app (_~~Definitely not targeting Notion~~_). But sometimes, being raw is power. Terminals give you that rawness.

It’s not just about nostalgia or being geeky for fun. TUI tools are:

- Blazing fast (like seriously instant)
    
- Keyboard-driven, so your hands never leave the keys and forget the mouse even exists
    
- Often more scriptable and composable
    
- Lightweight and can run on toasters (or potatoes, if u prefer them)

For devs, sysadmins, hobbyists, and even minimalists, TUI is not just a UI – it's a philosophy.  
And if you can make your own (even if it’s not fully polished)? Damn right it's still worth flexing.

### What did I do?

A long time ago, somewhere in February of 2024, I got an idea to build myself a music streaming platform, 'caz at that time I was good with frontend web development. But I wanted to expand more, and what's the best way to learn than hands-on experience? That’s how I started learning backend. Fast forward 6–7 months, my web application was ready. I’ll explain the entire workflow in some other blog someday. For now, u can refer to GitHub [here](https://github.com/samay15jan/sparklines).

So, from here I got an idea—why not use the custom backend (which I built on top of an open-source project [here](https://github.com/sumitkolhe/jiosaavn-api)—I can’t remember if it was v2 or v3. idk) and build a terminal user interface to control music directly from the terminal? (Because other open-source projects were related to Spotify TUI and required a paid account with Spotify open in the background). But I needed something based on my use case, which I could run in the background while I was lost in coding sessions _**and didn’t eat up 60% of my RAM**_. I needed something like a command to run, and I could play any song I want directly from the terminal itself. After all, it’s going to be the coolest way to stream your music from the terminal!

> **NOTE**: Just to be honest — it doesn’t "stream" like you think. My custom backend (built on top of JioSaavn) grabs the full song URL. Then I just pass that URL to `mpv`, a media player. Simple and effective, yet works like a charm.

For quite some time, this project was just sitting idle in my TO-DO list while I did my research on finding the perfect way I could do that. And that’s when I found [Ink](https://github.com/vadimdemedes/ink). It's a way I can use React for interactive command-line apps. Yeah, it's old but it’s a well-maintained and documented open-source project. I found it to be a perfect fit for my use case, ‘caz I did know JS/TS well and had hands-on experience in React itself. So, I believed it was going to be fun to build. Also, I couldn't find anyone who took this approach to build a highly intrusive TUI with React and Ink specifically, so either I’m making history or I’m one step closer to becoming that mad guy. _Win-Win situation haha._

So, I went all in. Can’t truly recall how long it took me to build—somewhere around a month.  
Oh shit... been talking all this time and didn’t tell u what I named it: [**Sparklines-TUI**](https://github.com/samay15jan/Sparklines/tree/main/TUI). hehe

---

### Tech Stack

**Languages & Tools:**

- NodeJS + TypeScript
    
- [Ink](https://github.com/vadimdemedes/ink) and [Ink-UI](https://github.com/vadimdemedes/ink-ui)
    
- mpv (for music playback)
    
- Custom backend (on top of JioSaavn)
    
- Socket & fs handling in Node for communication with mpv
    
- Works in Termux (Android) (unstable)
    
- Vim/Google IDX (now Firebase Studio)
    

> Some features are not yet implemented, but the basic functionality has been achieved, though there might be unknown bugs. You can report [here](https://github.com/samay15jan/Sparklines/issues), and chances are I might never fix them. hehe, so try doing some work yourself, and contributions are welcome.

---

### Building the UI

Definitely, React + Ink streamlined the approach to build the tool, because I was able to use previous web development knowledge and not much of a learning curve either. It was definitely something worth it. I know people will say it's not good, design/system architecture sucks, should’ve used Rust or ncurses or something similar, and so on. Definitely agree with some things, but the reason I built it was to solve a problem I couldn’t find a solution for anywhere. So I created it for myself, and it serves the purpose and works as expected. Also, Rust or ncurses introduces a steep learning curve.

#### My work environment

I used Vim mostly while I was building this. I cloned the Ink repo to read docs side by side. Definitely worth it. Vim itself is a skill, though it’s not that good for actual coding, and messing around with nvim felt like a burden. So I switched gears to a cloud IDE (Google IDX) for development, and it did increase my coding speed a lot, especially with Nix package management.

#### Challenges in the journey

The biggest challenge I faced was getting some sort of way to play music. So I picked the easiest route—I directly implemented it with [mpv](https://mpv.io/) and I channeled logs of mpv (which had timestamps, which I needed) to a log file under the `.sparklines` folder, and managed it with a socket (a two-way communication endpoint to handle the custom commands). With the power of NodeJS, I made it work out and somehow it turned out a lot better than expected. Also, configuration files can be accessed at `.sparklines/config`.

For sure, **Ink** was something ahead of its time. It has everything one needs to build something like this. At least for fun. I faced challenges when I was working with the UI itself, though it took me some time to perfectionate it and make it modular and work with custom shortcuts. Packaging was a very simple and quick task.

> BTW, u can get it directly using `npm i sparklines-tui -g`.

#### Some Features

- Control music directly from the terminal
    
- Login/Register functionality
    
- API key-based interaction with [Sparklines Backend](https://github.com/samay15jan/sparklines-backend)
    
- Continuous playback (still buggy) and clean playback bar
    
- Custom shortcuts & help menu (Alt+h)
    
- Search songs, albums, and artists
    
- Music language selector
    
- Recommendations & infinite play (work in progress) [TODO]
    
- Loop, shuffle, queue, and lyrics support (coming soon) [TODO]
    
- NPM packaged and works on Termux (to some extent)
    

> For installation, refer to [docs](https://github.com/samay15jan/Sparklines/tree/main/TUI).

#### Help Menu

Some useful commands (can be accessed through Alt + h):

```
Tab                 → Navigate between sections  
Spacebar            → Toggle between play and pause  
Enter               → Select the selected item  
Ctrl + m            → Mute/unmute the audio  
Ctrl + x            → Hide other section  
Ctrl + z            → Toggle search  
Ctrl + a/s/d/f      → Focus on menu/playlists/simulation/other section  
Ctrl + k/l/;        → Toggle between search/lyrics/queue section  
↑ and ↓             → Navigate up and down between items  
] or [              → Increase/decrease volume by 5  
Ctrl + ➡ / Ctrl + ⬅ → Seek forward/backward by 5 seconds  
Ctrl + ➡ / Ctrl + ⬅ → Increase/decrease speed by 0.2x  
Alt + h             → Display/close this help menu  
Esc                 → Quit the app
```

---

[![TUI Demo](https://asciinema.org/a/696484.svg)](https://asciinema.org/a/696484)

---

### Final Thoughts
I don’t expect anyone to care (but u should care). Honestly, this was more for me. To learn, to experiment, to see if I could push the limits of terminal UI in JS. And it did that.   
And that’s what matters the most. If you're building something and it excites you, then even if no one else claps, you've still won.  

Until next time. stay in terminal. peace
