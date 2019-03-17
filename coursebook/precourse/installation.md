# Ubuntu Installation - Instructions and Troubleshooting :grimacing: :sweat:

Helping the students to dual-boot ubuntu with Windows can be a bit of a pain for the mentors (especially for those with no experience of Windows).
This document is meant to provide a step by step guide with the help of links to tutorials I've followed and which proved to be successful.
In the troubleshooting section, I provide some answers to frequent (and not so frequent...) problems I've encountered while helping the Lotus-1 cohort with their installation.

For the sake of clarity, I would just like to specify that students in Lotus-1 were all using **Windows 10** and we installed **Ubuntu 18.04**.

## Installation - Step by Step Instructions

First, create bootable USB drives using [Rufus](https://rufus.ie/).
It's important to create USB drives that can boot **both in UEFI and Legacy BIOS mode**.

### UEFI or Legacy BIOS Install :question:

Next, identify which type of install the system will need. It's important to install Ubuntu in the same mode as Windows.

To identify whether Windows is in UEFI or BIOS mode, press the :mag: and look for **System Information** (there are various ways to access System Information but this is the one I used). In the *System Summary* tab, you should see an entry **BIOS mode**.
[example screenshot](https://www.tenforums.com/attachments/tutorials/136343d1495570285-check-if-windows-10-using-uefi-legacy-bios-legacy_bios_msinfo32.jpg)

### UEFI Install

UEFI install is usually pretty straight forward :pray:
Follow [this tutorial](https://itsfoss.com/install-ubuntu-1404-dual-boot-mode-windows-8-81-uefi/).

**Note**: You should do all the steps, **even the ones marked as optional**.

The only thing that is not completely accurate in this tutorial is the **Note:** at the end.
It's true that if the machine boots directly into Windows after the install, it means you need to change the
boot order. The way I successfully did this was to access the computer BIOS and change the boot order there(more on this in the Troubleshoot section). The terminal command listed in the tutorial did not work on the machines I had this problem with.

### Legacy BIOS Install

Legacy BIOS installs can be slightly more complex but if you understand what you are doing (which should be the case once you are done reading this document and the attached resources :smirk:) then everything should work just fine :sunglasses:.

Here are the steps that I followed:
- Create space for Ubuntu by following **step 3** of [this tutorial](https://itsfoss.com/install-ubuntu-1404-dual-boot-mode-windows-8-81-uefi/)
- Plug in the USB drive and then do a normal shutdown of the computer.
- Turn on the computer and press the appropriate key to access the boot menu. Different manufacturers and computer models have different keys for accessing the boot menu. Here is a comprehensive [list of computer manufacturers and models](https://kb.wisc.edu/page.php?id=58779) with their keys listed.
- Choose to boot the system from the USB drive.
- Once this is done, at some point you should see the options "Try Ubuntu" and "Install Ubuntu". Click on **Install Ubuntu**.
- Follow the installation instructions until you are prompt for the Installation Type.
- Once you are on the **Installation Type** screen, click on **Something else**.
- Create the partitions as shown in **step 6** of the previously mentioned tutorial except that instead of choosing *Primary* for the type of partition (as shown in the screenshots) you should choose *Logical* (this is the option that should be selected by default if you are installing in Legacy BIOS mode).
- Once you are done creating the partitions, click **Install**.

---
**IMPORTANT** :boom:

If the system throws an error after you clicked *Install*, **DO NOT PROCEED WITH THE INSTALLATION!** Click on **Go Back** and quit the installation until you figure out what the problem is (hopefully the next section should help).

---

## Troubleshooting :scream_cat:

### The installation worked but Wifi is not working in Ubuntu

This means that you are missing the drivers for your Wifi adapter. It's fairly simple to fix with some linux-fu and googling. :muscle:

- Connect your phone to your computer with USB cable and [enable USB tethering](https://www.youtube.com/watch?v=LvMZW_ztf14). This will allow you to have internet on the computer to be able to download the necessary tools and drivers.
- Open Terminal and start by doing update and upgrade of the system:
```
sudo apt-get update && apt-get upgrade
```
- install full linux headers and build packages, as well as git (most of the solutions are be hosted on Github).
```
sudo apt-get install linux-headers-$(uname -r) build-essential git
```
- Now you need to find out which wireless adapter is installed on the machine so that you can google it and find the appropriate driver:
```
lspci |grep Wireless
```
You should get an output that looks something like this, except that the name and model will be probably different:
```
Network controller: Intel Corporation PRO/Wireless 3945ABG [Golan] Network Connection
```
- Once you know which wireless adapter you have, google: *Wifi adapter not recognized Ubuntu <the name and model you got from previous step>*

Hopefully, from that point on Google will provide you to some answers and you should find links that point you to the right direction. I encountered this problem with student on HP laptops (HP 15-da0xxx). Here is the solution I followed and it worked:
```
sudo apt-get install --reinstall git dkms build-essential linux-headers-$(uname -r)
git clone https://github.com/tomaspinho/rtl8821ce
cd rtl8821ce
chmod +x dkms-install.sh
chmod +x dkms-remove.sh
sudo ./dkms-install.sh
```
[Taken from an answer on Stack Overflow](https://askubuntu.com/questions/990378/wi-fi-not-working-on-lenovo-thinkpad-e570-realtek-rtl8821ce)

### Free space shown as *unusable* when creating the partitions in Ubuntu

If this happens, you are probably doing a Legacy BIOS install. This means that your partition scheme is in MBR (Master Boot Record). MBR partition schemes can only support up to 4 primary partitions (in contrast to GPT scheme which can support up to 128 primary partitions).
You can read more on this [here](https://www.howtogeek.com/193669/whats-the-difference-between-gpt-and-mbr-when-partitioning-a-drive/).

To fix this issue:
- Quit the installation and shutdown the machine.
- Reboot inside Windows and go back to where you partitioned your drive to create free space for Ubuntu (Control Panel - Search for "disk" - Click on "Create and format hard disk partitions").
- Undo the partitioning which you previously did by extending the drive you parted. For example, if you parted the C: drive, right click on it and choose **Extend Volume**. The unallocated space you created should go back to be part of the C: drive. See *Method 1* of [this tutorial](https://www.intowindows.com/how-to-extend-system-partition-in-windows-8-1/).
- Now you will need to find a partition which your system doesn't need and delete it in order to use this space for Ubuntu. The easiest is when a computer contains more than one drive (for example a D: drive). If this is the case, backup all the data on that drive before proceeding to the next step. Otherwise, try to see if there is another partition which doesn't seem to be useful (DO NOT DELETE the **Recovery** partitions).
- Once you found a partition you can delete, click on it and choose **Delete Volume**. The space should show as **Unallocated**. See method 1 of [this tutorial](https://www.thewindowsclub.com/delete-volume-drive-partition-windows-10).
- Shutdown the computer and retry the installation as explained in the previous section.

### The system doesn't detect the Windows partition

This means that you are probably trying to install Ubuntu in a different BIOS mode then the Windows OS.
- Quit the install and shutdown the computer normally.
- Reboot inside Windows and check System Information. Make sure you follow the instructions for the appropriate BIOS mode.
- If you are sure that you are choosing the correct installation method but you are still having this problem, you might be dealing with this next issue so keep on reading...

### System Information says that I'm in Legacy BIOS mode but when I try to install I get the error "No EFI partition found" even if I boot in the USB from bios

This is a bit of a strange problem which happened once in the Lotus-1 cohort and not much documentation is written on it... But it's a surprisingly simple fix, the only thing is that you need to sacrifice one of the bootable USB drives in the process (the USB will still work for Legacy BIOS install but not UEFI).
- Quit the installation and shutdown the computer normally.
- Remove the USB drive.
- Turn on the computer to enter Windows normally.
- Plugin the USB and make sure the system recognizes it.
- Go to the disk management tool which you used to partition your disk (Control Panel - Search for "disk" - Click on "Create and format hard disk partitions").
- Right-click on the drive that says *Ubuntu* and choose **Explore**. This will give you a listing of all the internal files and folders that make the bootable Ubuntu drive.
- Now the important step, find the folder labeled as **EFI** and **DELETE IT**.
- Shutdown the computer normally.
- Reboot into BIOS, select to boot from the USB drive and proceed with the installation as explained in the previous section.
- After creating the partitions in Ubuntu and clicking **Install**, the error should be gone.

I found this solution by [reading this thread](https://askubuntu.com/questions/1122650/no-efi-system-partition-was-found-but-i-dont-have-a-uefi-and-the-installer-is-i).

---

Hope this guide is useful to future students/mentors dealing with the installation process! Any comments, suggestions or additions are welcome :sparkles:
