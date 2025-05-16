


<img src="https://github.com/user-attachments/assets/2375bc8c-c908-47f5-9f1a-c08bc028b7b7" width="50%">

# KVM Auto-Load Config

Welcome to the KVM Auto-Load Config documentation.

This package automatically loads essential KVM kernel modules at boot to enable hardware virtualization support for Intel and AMD processors on Arch Linux systems.

---

## 📜 Overview

KVM (Kernel-based Virtual Machine) is a native Linux kernel module that enables full virtualization using your system's hardware acceleration features such as Intel VT-x or AMD-V.

By auto-loading the necessary modules at boot, this package helps users:

- Run virtual machines with near-native performance.
- Avoid manual configuration of kernel modules.
- Maintain compatibility with both Intel and AMD CPUs.

---

## 🔧 Features

- Auto-loads KVM modules: kvm, kvm-intel, and kvm-amd via systemd on boot.
- CPU compatibility: Supports Intel and AMD processors.
- Optimized for Arch Linux Zen kernel as well as standard kernels.
- Lightweight & non-intrusive: Does not interfere with system performance when unused.
- Graceful failure: If the CPU does not support KVM, no modules are loaded.

---

## 🛠 Installation
```
sudo pacman -S zenora-qemu-kvm
```
---

## 🔧 Installing Virtual Machine Drivers in KVM

When setting up virtual machines with KVM, it's essential to install and configure appropriate drivers within the guest operating system to ensure optimal performance and functionality. Here's how to set up the most common drivers:

### 1. QEMU Guest Agent 

The QEMU Guest Agent provides an interface for the host system to communicate with the guest virtual machine (VM) and is crucial for advanced features like shutting down or pausing VMs from the host. To install the QEMU Guest Agent inside your VM:

For Ubuntu/Debian-based systems:
```
sudo apt-get install qemu-guest-agent
```
For zenora Linux:
```
sudo pacman -S qemu-guest-agent
```
Once installed, enable and start the service:
```
sudo systemctl enable qemu-guest-agent
sudo systemctl start qemu-guest-agent
```
This allows the host to interact with the VM and provides additional features like file transfer, clipboard sharing, and automatic shutdown.

### 2. VirtIO Drivers (For Better Performance)

VirtIO provides efficient, high-performance I/O for virtual machines. This driver is necessary for devices like network interfaces, disk drives, and memory ballooning. Here's how to install it:

#### Install VirtIO drivers in the guest OS:

For Windows VMs:
- Download the VirtIO ISO image from [Fedora's repository](https://fedoraproject.org/wiki/Windows_Virtio_Drivers).
- Attach the ISO to the VM's virtual CD/DVD drive.
- Inside the guest OS, open the VirtIO CD and install the necessary drivers for network, disk, and other devices.

For Linux-based VMs (zenora Linux example):
sudo pacman -S virtio
The virtio module should already be part of the Linux kernel, but installing the virtio package ensures that all tools and utilities for managing VirtIO devices are installed.

### 3. SPICE and QXL (For Enhanced Graphics Performance)

For better graphical performance and enhanced display capabilities (especially if running a graphical desktop environment inside the VM), you can install the SPICE server and QXL video drivers:

For Linux-based guests:
```
sudo pacman -S xf86-video-qxl spice-vdagent
```
For Windows-based guests, you need to install the SPICE Guest Tools from the VirtIO ISO.

### 4. Enable Clipboard Sharing (For Linux Guests)

To enable clipboard sharing (copy/paste functionality) between the host and guest, make sure the spice-vdagent is installed and running inside the guest:
```
sudo systemctl enable spice-vdagentd
sudo systemctl start spice-vdagentd

```
This will allow you to copy text and files between the host and the guest using the clipboard.

---

## 🔍 How It Works
Upon installation, the package creates a systemd modules-load configuration file at:
```
/etc/modules-load.d/kvm.conf
```
This file includes the following lines:
```
kvm
kvm_intel
kvm_amd
```
Systemd will load these modules during boot, and the kernel automatically ignores incompatible modules.

---

## 🏁 Verifying Module Status

To check if the KVM modules are loaded:
```
lsmod | grep kvm
```
Check CPU virtualization support:
```
lscpu | grep Virtualization
```

Inspect system logs for KVM-related messages:
```
dmesg | grep kvm
```
---

## ⚙️ BIOS/UEFI Requirement

Ensure that hardware virtualization is enabled in your BIOS/UEFI firmware:

- Intel CPUs: Enable VT-x
- AMD CPUs: Enable AMD-V

---

## ❗ Troubleshooting

- KVM not working? Double-check that virtualization is enabled in BIOS.
- Modules not loading? Make sure /etc/modules-load.d/kvm.conf is correctly created and contains the module names.
- Log Errors: Use dmesg to identify kernel errors related to KVM.

---

## 📚 Additional Resources

If you are looking for more detailed documentation and guides, here are some helpful resources:

- KVM Documentation - Official Kernel Docs:  
  [https://www.kernel.org/doc/html/latest/virtualization/kvm.html](https://www.kernel.org/doc/html/latest/virtualization/kvm.html)

- QEMU Documentation:  
  [https://www.qemu.org/docs/master/](https://www.qemu.org/docs/master/)

- Arch Wiki - KVM:  
  [https://wiki.archlinux.org/title/KVM](https://wiki.archlinux.org/title/KVM)

- VirtIO Drivers for Windows:  
  [https://fedoraproject.org/wiki/Windows_Virtio_Drivers](https://fedoraproject.org/wiki/Windows_Virtio_Drivers)

- SPICE Documentation for Virtual Machines:  
  [https://www.spice-space.org/](https://www.spice-space.org/)

---

## 📝 License

This project is licensed under the MIT License.  
You are free to use, modify, and redistribute the package with appropriate credit.

---

## 🚀 Contributing

Contributions are welcome! Feel free to open an issue or pull request for improvements, bug fixes, or new features.

---

## 🙏 Thank You

Thank you for using KVM Auto-Load Config — making virtualization setup seamless and easy on Arch Linux!
