

<img src="https://github.com/user-attachments/assets/0894c7b6-6469-4858-a273-5f9d72efcd02">

# OpenRGB Installation & Configuration

Welcome to the **OpenRGB Installation & Configuration** documentation. This guide will help you to install **OpenRGB**, automatically set up necessary dependencies, and configure required **udev** rules for controlling RGB devices on your Arch Linux system.

---

## 📜 Overview

**OpenRGB** is a cross-platform RGB lighting control software that allows you to manage and synchronize RGB lighting effects on multiple devices. This package provides an automated installation process, configuring **OpenRGB** along with essential dependencies and rules for device access.

The main features of **OpenRGB** are:

- Unified RGB control for various devices.
- Customizable lighting profiles and effects.
- Open-source and supports a variety of devices (motherboards, GPUs, peripherals, etc.).

This package ensures that all **OpenRGB** dependencies are correctly installed and configured to run seamlessly on your system.

---

## 🔧 Features

- **Automatic installation** of OpenRGB with required dependencies.
- **Kernel module setup** for RGB device access.
- **Automatic udev rule addition** to provide required permissions.
- **Supports a wide range of devices** including motherboards, memory, GPUs, and peripherals like keyboards, mice, and more.
- **Easy-to-use interface** for managing and customizing RGB lighting.
- **Service setup** to run OpenRGB at startup.

---

## 🛠️ Installation

```bash
sudo pacman -Syu zenora-openrgb
```

This will install **OpenRGB**, **i2c-tools**, and **libusb**, which are essential for device communication and control.

---

## ⚙️ udev Rules Configuration

**udev** rules are required to provide the necessary permissions for **OpenRGB** to access your RGB devices. These rules are automatically added during installation.

Here is a list of the rules that will be added to `/etc/udev/rules.d/60-openrgb.rules`:

```bash
# Open Access to All USB Devices
SUBSYSTEM=="usb", MODE="0666"

# Open Access to All HID Devices
KERNEL=="hidraw*", MODE="0666"

# Open Access to All I2C Devices
KERNEL=="i2c-[0-9]*", MODE="0666"
SUBSYSTEM=="i2c-dev", MODE="0666"

# Open Access to NVMe Devices (for RGB SSDs like XPG S40G)
KERNEL=="nvme*", MODE="0666"

# Extra: Open Access to SMBus
SUBSYSTEM=="i2c", ATTR{name}=="SMBus", MODE="0666"
```

### Step 4: Reload udev Rules

Once the rules are added, reload **udev** to apply them:

```bash
sudo udevadm control --reload
sudo udevadm trigger
```

This will apply the newly created rules and ensure that **OpenRGB** has the necessary access to all supported devices.

---

## 📋 Usage

After installation and configuration, you can launch **OpenRGB** either from the application menu or via the terminal:

```bash
openrgb
```

### Customization and Profiles

Once **OpenRGB** is running, you can customize the RGB effects, create lighting profiles, and synchronize devices directly from the graphical interface. You can save profiles for later use, allowing you to apply your lighting preferences quickly.

---

## 🛠️ Troubleshooting

If you encounter any issues, follow these steps:

### 1. **Permissions Issue**
If **OpenRGB** is unable to access devices, check that the udev rules are correctly applied:

```bash
ls -l /dev/i2c-*
ls -l /dev/hidraw*
```

Ensure that the devices have the correct permissions (`0666`).

### 2. **Device Not Detected**
If **OpenRGB** does not detect your RGB device:

- Verify that your device is supported by **OpenRGB** (check the [official OpenRGB device compatibility list](https://github.com/CalcProgrammer1/OpenRGB/wiki/Supported-Devices)).
- Ensure that your system recognizes the device correctly (check with `lsusb` for USB devices and `lspci` for PCIe devices).
- Check the **system logs** for any error messages related to device access.

---

## 📝 Contributing

Contributions to **OpenRGB** and this repository are welcome. If you have improvements, bug fixes, or new features, please fork the repository and create a pull request. For reporting bugs or requesting features, open an issue on GitHub.

---

## 📚 Additional Resources

- **Official OpenRGB GitHub Repository:**  
  [https://github.com/CalcProgrammer1/OpenRGB](https://github.com/CalcProgrammer1/OpenRGB)

- **OpenRGB Device Compatibility:**  
  [https://github.com/CalcProgrammer1/OpenRGB/wiki/Supported-Devices](https://github.com/CalcProgrammer1/OpenRGB/wiki/Supported-Devices)

- **Arch Wiki - OpenRGB:**  
  [https://wiki.archlinux.org/title/OpenRGB](https://wiki.archlinux.org/title/OpenRGB)

---

## 🚀 License

This project is licensed under the **MIT License**.  
Feel free to use, modify, and redistribute this package with proper attribution.

---

## 🙏 Thanks

Thank you for using **OpenRGB**! We hope this guide helps you set up a seamless RGB experience on your Arch Linux system.
