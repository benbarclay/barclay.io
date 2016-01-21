+++
date = "2016-01-21T19:28:47+11:00"
draft = false
title = "Desktop Config 2016"

+++

For the past two or so years, I have been running my desktop computer dual booting Windows and Arch Linux. This has been a good solution for me, being able to use Windows for media consumption and the occasional game and also having a proper Linux operating system as a development environment. It's occasionally frustrating having to reboot between systems, especially on weekends where I might swap between working and leisure multiple times.

Over December my desktop pulled down a new Windows 10 update. I have Windows set to automatically update and wasn't particularly worries about it applying updates.

However, this particular update decided it needed to re-partition my computer. I had a pre-existing Windows 8 recovery partition and a Windows 10 partition. Deciding that the Windows 8 recovery partition was too small to convert into a Windows 10 recovery partition, the updater decided to split the Windows 10 partition and create a new recovery partition at the end.

So far so good, this didn't touch my Linux partitions at all.

The trouble started the next time I tried to boot into Arch.

Initially I couldn't boot at all as the EFI bootloader was pointing at the wrong partition. Easy fix, just temporarily overwrite the setting on a single boot and then permanently fix it once booted into the system.

After getting the system bootable again, I found the network was down. Not really sure why the network wouldn't come up, and didn't really have the time to debug it before I had to head off to visit family.

Not particularly happy that Arch was broken, and slightly bothered that Windows now had more partitions than it needed, I decided to start afresh.

My data was all stored on some spinning disk HDD's and the two operating systems on a faster SSD.

I wiped the SSD and installed Windows 10 from scratch, letting it create partitions as necessary.

At this point I stopped and thought about whether I wanted to install Arch on another partition again or if I could use a virtual machine to get the best of both worlds.

I have used VirtualBox many times in the past, and whilst it's perfectly functional, it's not what I had in mind here. I ended up giving Windows built in Hyper-V a try. I had last used it when Windows 8 first came out and I heard that it had a build in hypervisor. At that point I found myself unable to use it as I needed access to a GUI for some of the things I was working with and Hyper-V had (and still does) abysmal video performance.

What I had missed at that point was that it was deeply integrated into the lifecycle of the machine and very performant.

So I created a new Virtual Machine in Hyper-V and got ready to install Linux.

I decided to install Debian instead of Arch this time, as it's closer to the Ubuntu servers that I use at work, but still provides a systemd environment that I was comfortable with from Arch.

This setup has been running for a few weeks now, and I have been very happy with it. Hyper-V is aware of the Windows lifecycle and will start when Windows starts and will cleanly shutdown guest OS's when the host is shutting down.

In addition it seems to be very memory efficient, with dynamic memory allocation. I have assigned my VM 4GB of memory, but Hyper-V is currently only assigned 768MB of memory. Given that it's running a server edition with very few utilities, this seems generous but sensible.

The biggest problem in this whole setup has been finding a good way to connect. From my work OS X laptop, I can connect over SSH with no problems. On windows the build in Virtual Machine Connection utility provides a functional, but sub-optimal way to connect to the VM. Ultimately I settled on using the Secure Shell extension to Google Chrome to access my desktop.

Unlike when I provisioned my Arch box last time, this machine is fully configured with Ansible. If I need to go through this process again in another six months, it should be a fairly trivial process.
