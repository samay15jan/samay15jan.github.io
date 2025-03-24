---
title : 'Part 1: Getting Started With Linux'
summary : "Part 1 of the Ultimate Guide to Mastering Linux: From Beginner to Advanced"
date : '2024-12-10T23:59:15+05:30'
author: "Samay Kumar"
draft: false
showToc: true
TocOpen: true
---
## Introduction to Linux

### What is Linux? Million Dollar Question

Linux is a kernel for computer systems that is used worldwide. *Yeah, even the social media you use on your phone could be backed up by a Linux server.* Some people call it an operating system. However, Linux itself is only the kernel. When combined with other components like software utilities and libraries, it forms a complete OS, often called a "Linux distribution"—*you will get to know about it later in this blog.*

### Why is Linux important?

Firstly, here are some solid stats from [TrueList](https://truelist.co/blog/linux-statistics):

- 96.3% of the top one million web servers are running Linux. (ZDNet)
- Yep, the very same Linux is powering a whopping 85% of smartphones out there. (Linuxblog)
- The world’s top 500 fastest supercomputers all run on Linux. (Blackdown)
- 47% of professional developers (*like me*) use Linux-based operating systems. (Statista)
- Today... *maybe not when you are reading this*, there are over 600 active Linux distros. (Tecmint)

Most importantly, Linux is also one of the biggest open-source projects, which means all its code is publicly accessible. Anyone—*maybe even you after reading this blog*—can modify and distribute its code, and it’s developed collaboratively with our very own Linux community.

Which means it gives freedom and a sense of independence directly into the hands of the user to do whatever they want, without any higher body governing like what we usually get in other OSes, while maintaining the latest updates which don't take hours to install—that too at zero cost.

> **Did you know?**\
> Windows gets shattered,\
> Apples get rotten,\
> but penguins, they don’t drown... wait... do they?\
> Fires up browser..."can penguins dieee?"\
> Waits... waits intensively...\
> Google: "Please verify you are not a robot."\
> Clicks... clicks... submit\
> Google: "Yes, penguins do die like every other living organism, you dumbass. But they do live longer than Windows and Apples."

### The Birth of Linux

The backstory of Linux is straightforward. At the heart of it all is [Linus Torvalds](https://en.wikipedia.org/wiki/Linus_Torvalds), an incredible programmer, who laid the foundation bricks for what we now know as Linux. Over the years, a global community of talented developers has built on that foundation, continually enhancing and evolving the system.

That's all you gotta know. You can anytime fire up Wikipedia and learn about the cheeky little details, but I would recommend—**theory is not something you should focus much on, especially for technical stuff**. For your knowledge, surely go for it.

But for now, that's out of the goals for this blog.

## Understanding the Computer System Architecture

### Layers of a Computer

Let's understand the working of a computer. According to my research, there are basically three main layers of a computer:

- **Layer 1**: This is the **hardware** layer, which consists of the physical components of the computer, such as the CPU, memory, storage devices, or that RTX 4090 Ti graphics card which you asked your mother to buy, stating it is the bare minimum for your studies.
- **Layer 2**: This is the **kernel**, the most crucial layer in the system. It acts as an intermediary between the hardware and the software, managing resources like memory, processing power, and devices. The kernel ensures that software can interact with hardware safely and efficiently.
- **Layer 3**: This is the **user interface** layer, where users interact with the system. It includes the graphical user interface (GUI) and applications. This layer allows users to perform tasks such as browsing the web, creating those boring presentations, and running programs.

Think of the kernel as the manager of all system resources. It ensures that software can talk to the hardware and access resources, but it also ensures that the system runs efficiently and securely by controlling access and managing tasks.

> **NOTE**: If you want to dive deeper into the relationship between the computer and hardware, consider checking out [this](https://www.geeksforgeeks.org/computer-organization-and-architecture-tutorials/).

### The Role of the Kernel in Linux

Here are some of the key roles the kernel plays as an interface between hardware and software:

- **Process Management** - Handles the creation, execution, and termination of processes.
- **Memory Management** - Allocates and deallocates RAM for processes in a sandboxed manner.
- **Device Management** - Controls hardware devices such as keyboards, mice, or any plug-and-play device like USBs via device drivers.
- **File System Management** - Handles file read/write operations, including access control and permissions for files and directories.
- **Networking** - From IP addresses to firewalls, even the communication between processes over networks is handled by the kernel.

## Setting up your playground

Before moving forward, I personally have this ideology that any knowledge learned by hands-on experience will help you grasp concepts more quickly and efficiently. You can skip this part, but it would be good if you give it a shot.

### Installing Linux (Virtual Machine, Bare Metal, WSL, Cloud)

To start using Linux, I personally would recommend going with [Pop!\_OS](https://pop.system76.com/).
You got a few options here: either you can run it on a VM or install it on Bare Metal.
*Don't worry, I got you covered—you can use any one of the following methods:*

#### Virtual Machine (Recommended):

It's like installing an OS inside your running system but virtually, which means you don't have to worry if you mess up something. Your main system will work just fine.
Here are the steps:

- Install either [VirtualBox](https://www.oracle.com/virtualization/technologies/vm/downloads/virtualbox-downloads.html) or [VMWare](https://www.vmware.com/) on your Windows/Mac machine (*for this, your device must support virtualization, which should work in most cases unless you have a very old/potato PC, or you might have to enable it in BIOS. Follow some tutorials for that—it's not a big thing*).
- Download the Linux Pop!\_OS ISO from [here](https://pop.system76.com/). You could try [Ubuntu](https://ubuntu.com/download) too.
- Simply create a new VM, allocate RAM and storage, load the downloaded ISO, and run it.
- Follow the on-screen instructions to install Linux or use the live environment.

> **Note**: There are plenty of guides on the internet—just follow any one.

#### Bare Metal:

This step involves installing Linux directly on your system. It will delete your Windows forever, and you cannot recover it. There are ways like dual booting (*installing two OSes on one device*). But for now, let's focus on a clean installation of Linux on your system:

- Download the Linux Pop!\_OS ISO from [here](https://pop.system76.com/). You could try [Ubuntu](https://ubuntu.com/download) too.
- Download and install [Balena Etcher](https://etcher.balena.io/) or [Rufus](https://rufus.ie/en/) for creating a bootable USB.
- Get at least an 8GB empty USB stick and plug it into your system.
- Run Balena Etcher or Rufus, import the downloaded ISO, and start the process.
- It will take 5-10 minutes to create a bootable USB.
- Now, based on your device brand, find its boot keys—just Google it.
- Reboot your system and say goodbye to Windows.
- Press the boot keys when booting, select your USB stick, and click enter.
- Now, after booting, you will be presented with a live environment. Whatever changes you make here will be gone with a reboot.
- Now, simply follow the on-screen instructions and make a clean install on your storage device.

> **Note**: Unfortunately, this method is not possible on Apple devices. Though there are ways, they are complicated.

> **IMPORTANT**: Installation on Bare Metal is not recommended for beginners because there is a higher chance you could lose all your data, and I don't want you to curse me for that.

#### Windows Subsystem for Linux

It's a method to run Linux directly on your Windows system using the subsystem for Linux. It's a very straightforward method for any Windows user:

- Check if your device supports virtualization.
- Open PowerShell as Administrator.
- Run `wsl --install`.
- That's it; it will install Ubuntu by default.

> **INFO**: Earlier, it was a long process to do, like configuring in the control panel to enable the WSL service, then proceeding with manually installing it from the Microsoft Store, and it wasn't that feature-rich.  

> *Thank God Microsoft streamlined this feature to make it quick and efficient.*

#### Cloud

This process allows us to spin up a virtual machine directly on the cloud. Though they do cost some money, it's a good option if you are already familiar with services like AWS/Azure/GCP. You can also use third-party services like Linode.  

If you just need to get familiar with the command-line interface, Google IDX is a good option, as it provides a terminal window where you can practice commands and also learn the NIX package manager. On the other hand, you can use Google Cloud Shell too, which also uses an APT-like package manager.

> There are infinite possibilities; it just depends on what you are comfortable with. The basic commands on Linux are the same everywhere. Every distro has a layer on top to make some repetitive processes easy. That's it. Nothing else.

## Linux Distributions: What Are They and Why So Many?

Now, you might be thinking, why did I recommend you use Pop! OS or Ubuntu? What are they, and so on? *Good question... Next question?... Joking.*

Look, as I said, Linux is a kernel, which uses a lot of other utilities that make it an OS for performing different tasks. These utilities can be anything (desktop GUI, icons, fonts, tools, drivers, etc.).

Linux has multiple distributions (also known as flavors). As stated earlier, there are about 600+ distros (*short for distributions*), each with its own purpose, use cases, and communities built to maintain them and provide forums for support.

### Some Major Linux Distros:-

- **Ubuntu**: A **Debian**-based Linux distro, famous for its user-friendly nature and interface, which is somewhat similar to Windows. It’s popular for beginners and is also widely used in server environments.
- **Kali Linux**: A specialized Linux distro primarily used by **penetration testers**, ethical hackers, and security researchers. Kali comes preloaded with a wide range of security and forensic tools.
- **Linux Mint and Pop! OS**: Lightweight distros, also based on **Ubuntu** and **Debian**, designed to be easy to use and very similar to the traditional Windows desktop experience.
- **Arch Linux**: A minimalist, DIY distro that follows the **KISS (Keep It Simple, Stupid)** principle. Arch is favored by advanced users who want full control over their system. It’s not beginner-friendly but offers total customization. (*I use Arch, by the way!*)
- **Fedora**: A cutting-edge, community-driven distro with a focus on free and open-source software. It is often used by developers and those who want the latest features in an enterprise-friendly package.
- And more like **Slackware**, **openSUSE**, **Alpine**, etc.

I know it's confusing, and once you go deeper into the rabbit hole, you will explore more and more overly complicated stuff like **Gentoo**, **Linux From Scratch**, and a lot more.

### Concept of Distro Hopping and How to Overcome It

It's common for people who start using Linux to get lost in **distro hopping** (the process where users try out the most popular Linux distros to find a perfect fit for them).

We all have been through that phase, and here are a few tips to avoid it:

- There are only 3-4 main distros on which others depend: Debian, Arch, Fedora & openSUSE.
- Never judge a distro based on its looks; you can replicate any theme, UI, or specific feature of one distro on another using Package Managers (it's like a place where you download software/tools from, just like the Microsoft Store or App Store. More on that later).
- What matters is your use case.

  - **For developers**: Recommend Arch or Fedora due to their rolling releases.
  - **For general users**: Ubuntu or Mint for a user-friendly experience.
  - **For security professionals**: Kali Linux or Parrot Security OS.

- That's it. There are thousands of distros out there, but in reality, they are just some visual enhancements. That's it. I like to call them Niche distros.

> **TIP**: Don't Fall into the Distro Hopping Trap  
> **Pick a distro, stick with it, and get better at it**.  
> There’s no need to constantly jump between distros. If you're a beginner, **Debian** or **Ubuntu** are great choices. For more experienced users, **Arch** is ideal for customization & advanced users, and **Fedora** is the go-to for enterprise use.

> **HINT**:  
> In future articles, we might explore some ways you can create your very own distro too. Stay Tuned.

> **Did you know?**  
> There are even some distros like ***Hannah Montana Linux***, ***Biebian (for Justin Bieber fans)***, ***Red Star OS (North Korea's official Linux distro, you can imagine how great that would be)***, and even ***Linux XP (mimics Windows XP)***.

## The Command Line: The Heart of Linux

The core concept of Linux is getting familiar with the terminal. Yeah, it's that black screen with the blinking cursor—that's the Command Line Interface (CLI). I know it can be overwhelming for many (maybe everyone starting out... I was too). I actually tried avoiding it as much as possible in the initial days of my Linux switch. But eventually, we have to use it, and that's the hard pill to swallow. However, once you actually understand the power of the terminal, you might never leave it again.

**Here are a few solid reasons why it's a must-have skill:**

- Day-to-day tasks like listing, editing, removing, and copying files in folders get easier.
- Understanding package managers (depending on the distro) to install software.
- Unlike Windows, downloading software is different. Linux users prefer commands like **`wget`** and **`curl`** to download something. But don't worry—there are download buttons too, haha.
- Managing and configuring WiFi and the internet becomes easy.
- Configuring user permissions, checking system resources, creating or running scripts, and a lot more... *basically everything you could ever imagine.*

**Now that we know how powerful terminals are, let's quickly address some of the basic commands every Linux user should know:**

1. **`ls`** – List files in a directory
   - Example: `ls` shows all files and folders in the current directory.
2. **`pwd`** – Show the current directory
   - Example: `pwd` will display the full path to your current directory (e.g., `/home/user`).
3. **`cd`** – Change directory
   - Example: `cd Documents` moves into the "Documents" folder.
   - `cd ..` moves up one directory level.
4. **`echo`** – Display text or values
   - Example: `echo "Hello, World!"` prints the text on the screen.
5. **`cp`** – Copy files or directories
   - Example: `cp file1.txt file2.txt` copies the contents of `file1.txt` to `file2.txt`.
6. **`mv`** – Move or rename files or directories
   - Example: `mv oldname.txt newname.txt` renames the file.
7. **`rm`** – Remove files or directories
   - Example: `rm file1.txt` deletes the file `file1.txt`.
   - Use `-rf` to delete a folder directly.
8. **`mkdir`** – Create a new directory
   - Example: `mkdir new_folder` creates a new directory named "new_folder".
9. **`rmdir`** – Remove an empty directory
   - Example: `rmdir empty_folder` removes an empty directory.
0. **`cat`** – Display file contents  
   - Example: `cat file1.txt` shows the content of `file1.txt` on the screen.
1. **`man`** – View the manual for a command
   - Example: `man ls` shows the manual page for the `ls` command, helping you understand how to use it.
2. **`touch`** – Create an empty file
   - Example: `touch newfile.txt` creates an empty file named `newfile.txt`.
3. **`clear`** – Clear the terminal screen
   - Example: `clear` clears all text from the terminal, giving you a clean screen.
4. **`history`** – View your command history
   - Example: `history` shows the list of commands you’ve used in the terminal.
5. **`exit`** – Exit the terminal session
   - Example: `exit` closes your current terminal window.

> **TIP**  
> Linux terminals can be overwhelming at times, especially when we are just starting out. And for this, we have a helper, i.e., `man`. Nice naming, isn't it? _It's like how we ask questions in real life, "Man, what is this?"_ *Silly jokes aside.*  
> We can use this command like **`man <TOOL_NAME>`**, for example, **`man ls`** or **`man lsblk`**. It gives us complete A-Z usage of the tool directly from the terminal. In Linux, it’s more about reading first than implementing.  
> Many tools also have their own help menus, which we can access by **`-h`** or **`--help`**. It gives us a sweet little usage guide using flags.  
> BTW, anything starting with **`-`** or **`--`** in a command like **`--help`** is known as a flag. We can use multiple flags in one command to ease our life.

> **Text Editors**  
> Text editors are basically used to edit files quickly. Vim, Nano, and Emacs are all different types of text editors.
> The difficulty levels for these are: **Nano > Vim > Emacs.**

> **Suggestion**: If you ever accidentally stumble upon **`vim`**, don’t worry—you can exit it with **`esc`** then **`:q!`**. It’s something that will definitely make you mad at first.

## Linux File System Structure
Unlike the Windows file system, Linux has a more structured and hierarchical approach. Everything in Linux is a **file**—whether it's system drivers, memory processes, configuration files, or even hardware-related components. This design makes Linux extremely flexible but also requires a bit of understanding to navigate efficiently.

### Users and Groups in Linux
Before we understand where files are stored and how access is managed, we need to know who controls them—this is where users and groups come in.

**Users in Linux**  
In Linux, the most important user is **root**. Think of it as an admin (or in layman’s terms, we can call it the god of Linux). The **root** user has unrestricted access to the system, similar to the **Administrator** account on Windows, but with even more control. So, the root user has enough access to break the entire system or completely wipe everything (which is something very common if you don't pay attention).

However, as we know, with great responsibility comes great risk, meaning using root directly is dangerous. This brings up another question: How do we use the system?

Basically, in Linux, we can have multiple users, not just one or two—potentially infinite. One device can be used by many people, just like in Windows where we can create users. It’s a similar concept. All users have their own directory where only their data is saved, and no other user can access it.

**Groups in Linux**  
Not all users have the same responsibilities or permissions. We can’t trust everyone fully, so instead of manually assigning permissions to each user (which is a hectic task), Linux allows us to group users together. 

Users can be assigned to a **group**, making management easier. Groups work just like teams in a company—each group has specific permissions, making it easier to manage access control.

**User Management Commands:-**  

I know theory is boring, so let's dive into practicals:-

1. Create a new user:

	- `sudo adduser <USERNAME>` *// here `<USERNAME>` should be replaced by the desired username*
	- Creates a new user and sets home directory (`/home/<USERNAME>`)
	- It will ask you to set a password for the user too

2. Delete a user:

	- `sudo deluser <USERNAME>`
	- This removes the user but doesn’t delete the home directory
	- `sudo deluser --remove-home <USERNAME>` *// deletes home directory too.*

3. Change user password:

	- `sudo passwd <USERNAME>`
	- Prompts you to enter the new password for the user

4. Switch to another user:

	- `su - <USERNAME>`
	- To return to your previous user, type: `exit`

5. Create a new group:

	- `sudo addgroup <GROUPNAME>`

6. Add a user to a group:

	- `sudo usermod -aG <GROUPNAME> <USERNAME>`
	- The `-aG` option adds the user to the group without removing them from other groups

7. Remove a user from a group:

	- `sudo deluser <USERNAME> <GROUPNAME>`

8. List groups for a user:

	- `groups <USERNAME>`

9. Check current user:

	- `whoami`

10. View User ID (UID) and Group ID (GID):

	- `id <USERNAME>`

> **You might not know**  
> Specific commands like `addgroup`, `delgroup`, `adduser`, `deluser` are for Debian-based distros.  
> But, in Arch Linux, it's `groupadd`, `groupdel`, `useradd`, `userdel` commands.  
> The reason it's like this is that, in Debian-based distros, it acts as a wrapper for the same command (visual enhancement only) that Arch Linux uses, as they are true to **UNIX fundamentals**, which suggests that Arch sticks to roots and keeps things minimal.

### Understanding the Linux File System Hierarchy (FHS)

UNIX-based systems are known for their File System Hierarchy Standard (FHS). It's basically the entire file structure of the system. As we know, everything in Linux is a file, so its management is really important.

**Common Directories and Their Functions:-**

| Directory  | Purpose  |
| ---------- | --------------------------------------------------------------------------------------------------- |
| `/` (root) | The top-most directory; everything starts from here. |
| `/bin` | Essential programs (like `ls`, `cp`, `mv`, `rm`). Used by all users. |
| `/boot` | Bootloader configurations for booting (like `EFI`, `Grub`, `ReFind`). |
| `/dev` | Device files (like `/dev/sda` for hard disks, `/dev/null`, `/dev/sdb` for USB devices). |
| `/etc` | System configuration files (e.g., `/etc/passwd`, `/etc/fstab`). |
| `/sbin` | System-related binaries (like `fsck`, `iptables`, `shutdown`). Used mainly by root/admin. |
| `/home` | Home directories for users (`/home/user1`, `/home/user2`). |
| `/root` | Root user’s home directory (not in `/home`). |
| `/var` | Variable data (logs, caches, databases) like `/var/log/syslog`. |
| `/usr` | User-installed software and libraries (`/usr/bin`, `/usr/lib`). `/usr/local/bin` for custom executables. |
| `/tmp` | Temporary files that are deleted on reboot. |
| `/proc` | Virtual directory for process and kernel info (`/proc/cpuinfo`). |
| `/mnt` | Temporary mount point for external drives. |
| `/media` | Auto-mounted external drives (USBs, DVDs). |

### Navigating the File System Using the Terminal

As we have already discovered commands like `ls`, `cd`, `pwd`, now let's go a little deeper to understand things more:-

1. **Absolute Path**: Full path from the root (`/`) directory.
	_Example: `/home/user/Documents/file.txt`_

2. **Relative Path**: Path relative to the current directory.
	_Example: If you're in `/home/user/`, then `cd Documents` is the same as `cd /home/user/Documents`._

**Some Navigation Tips**:-

- `cd ..` → Move up one directory
- `cd -` → Switch to the previous directory
- `cd ~` or just `cd` → Move to your home directory
- `cd ~/home/user/Documents` → Move to a specific folder (if you are familiar with paths, which you will be as you practice.)
- `ls -l` → Long format listing (permissions, ownership, size, etc.)
- `ls -a` → Show hidden files (files starting with `.`)

### Common Linux Filesystems

A **file system** manages how data is stored, retrieved, and structured on a storage device. It includes:

- **Data Structure** → Defines how files, directories, and metadata are stored.
- **Journal & Recovery** → Some file systems support journaling for data protection.
- **Performance & Efficiency** → Affects read/write speeds and storage optimization.
- **Features** → Encryption, snapshots, compression, deduplication, etc.

| Filesystem | Features  |
| ---------- | ------------------------------------ |
| `ext4` | Default, stable, widely used. |
| `XFS` | Great for large files, high performance. |
| `Btrfs` | Supports snapshots, data integrity, and compression. |
| `ZFS` | Best for data integrity, RAID-like features. |
| `exFAT` | Works across Windows, Linux, macOS. |

> **NOTE**:
> For beginners, it's common that you might be on your desktop or VM, so I would recommend going for ext4. It's the most widely used filesystem, very stable, and not hardware-intensive. As you get familiar, you can try the other filesystems as needed. But keep in mind, basic fundamentals stay the same.

### Mounting and Unmounting File Systems

- **Mounting a Device**:
```bash
sudo mount /dev/sdxx /mnt # sdxx can be sda1, sdb, etc.
ls /mnt
```

- **Unmounting**:
```bash
sudo umount /mnt
```

- **Permanent Mounting (fstab)**:
To auto-mount a partition at boot, add to `/etc/fstab`
```bash
UUID=xxxxx /mnt ext4 defaults 0 2
```
> **NOTE**: You can find UUID using `lsblk -f`

### Hard Links vs. Soft Links and Symlinking

- **Hard Links**
	- A hard link is an additional name for the **same file**, no extra storage used.
	- If you delete the original file, the data remains.
	- Best for backups, redundancy, efficiency.
	- Eg: `ln file1 hardlink1`.

- **Soft Links (Symbolic Links)**
	- A symlink points to another file’s **path**, not its data.
	- If you delete the original file, the symlink breaks.
	- Best for shortcuts, cross-partition linking.
	- Eg: `ln -s file1 symlink1`.

## Conclusion

That was a lot to process, but there's even more just around the corner.

In the upcoming blogs, we’ll dive deeper into Linux, covering system administration, security, troubleshooting, and more. Who knows? You might build your custom Linux distro by the end of this series. Stay tuned!

Remember— **Practical > Theoretical**.
