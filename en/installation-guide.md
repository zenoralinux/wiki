# Installing Zenora Linux as a Dual Boot alongside Windows

Welcome to the **Zenora Linux Dual Boot Installation** guide. This document will help you easily install Zenora Linux alongside Windows and configure your system to choose between the two operating systems at startup.

---

## 📜 Overview

Dual booting allows you to have two operating systems on one computer and choose which one to run during boot. Zenora Linux is a lightweight and beautiful Arch-based distribution that offers a smooth and fast experience. This guide walks you through preparing the installation USB, creating a suitable partition, and installing Zenora with bootloader configuration step-by-step.

---

## 🔧 Features

- Easy creation of a bootable USB flash drive using Rufus  
- Safely create space on Windows for Linux installation  
- Boot directly from USB to start the installation  
- Live Linux environment for testing before installation  
- Full installation of Zenora Linux on a separate partition  
- Boot menu (GRUB) setup to select between Windows and Linux  
- Simple, illustrated instructions  

---

## 🛠️ Installation Steps

### 1. Download and Extract Zenora Linux ISO

First, download all parts of the Zenora Linux ISO. Then, use WinRAR to right-click on the first part and choose Extract to create the full ISO file.

### 2. Create a Bootable USB with Rufus

- Launch Rufus software.  
- Insert your USB flash drive.  
- Select your USB device under Device.  
- Click Select and choose the extracted Zenora ISO file.  
- Default settings usually work (Partition scheme: GPT, Target system: UEFI).  
- Click Start to create the bootable USB.

### 3. Create Free Space on Windows for Linux

- In Windows, right-click on This PC and select Manage.  
- Go to Disk Management.  
- Right-click on a partition with free space and select Shrink Volume.  
- Enter the amount of space to allocate (at least 30 GB) and confirm.

### 4. Boot from USB Flash Drive

- Restart your computer.  
- Press F12, F2, Delete, or the appropriate key to enter the boot menu during startup.  
- Select the created USB flash drive as the boot device.

### 5. Enter Zenora Linux Live Environment

- After booting, the live environment login screen appears.  
- Username: `zenora`  
- Password: `zenora`  
- Login to access the Zenora desktop.

### 6. Install Zenora Linux

- In the live environment, click the Zenora installer icon.  
- Choose your language and time zone, then click Next.  
- At the partition step, select the free space you created in Windows for installation.  
- Enter your desired username, password, and hostname.  
- Begin the installation. After completion, reboot the system.

### 7. Select Operating System at Boot (GRUB)

- After rebooting, the GRUB boot menu will appear.  
- Choose between Zenora Linux and Windows to boot your preferred OS.

---

## ⚠️ Important Notes

- Ensure you do NOT delete or format the Windows partition during installation.  
- If USB boot is not recognized, check BIOS settings and disable Secure Boot.  
- Use official Zenora Linux releases and download all parts completely.  
- If issues occur, recreate the bootable USB.

---

## 📚 Resources

- [Download Zenora Linux from the official site](https://zenoralinux.ir/en?page=download)  
- [Rufus for creating bootable USB drives](https://rufus.ie)  
- [WinRAR for extracting files](https://www.win-rar.com)

---

## 🙏 Thank You

Thank you for choosing Zenora Linux. We hope this guide helps you achieve an easy installation and a better user experience.

