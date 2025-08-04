


# Installing BlackArch Security Tools on Zenora Linux

Welcome to the official documentation for using **BlackArch security tools on Zenora Linux**. This guide covers how to install and use a wide range of security tools from BlackArch and other security-focused distributions on Zenora Linux.

---

## 📜 Overview

**BlackArch** is an open-source project that offers over 2800 cybersecurity and penetration testing tools. Zenora Linux includes BlackArch repositories by default, making it easy to install these tools using pacman.

The tools cover various categories including:

- Information gathering
- Network, web, and API testing
- Reverse engineering and malware analysis
- Password cracking and brute-force attacks
- Social engineering and exploits

---

## 🧰 Installing Tools

### Installing the complete BlackArch toolset (recommended for advanced users):

```bash
sudo pacman -S blackarch
````

### Installing specific tool groups (e.g., wireless tools):

```bash
sudo pacman -S blackarch-wireless
```

### Listing available BlackArch groups:

```bash
pacman -Sg | grep blackarch
```

---

## ⚡ Popular Tools Examples

| Tool           | Purpose                                  |
| -------------- | ---------------------------------------- |
| `nmap`         | Network and port scanner                 |
| `wireshark-qt` | Network traffic analyzer                 |
| `aircrack-ng`  | WPA/WEP wireless attacks                 |
| `hydra`        | Brute-force attacks on services          |
| `metasploit`   | Exploit framework and management         |
| `sqlmap`       | SQL Injection detection and exploitation |

To install individual tools:

```bash
sudo pacman -S <tool-name>
```

Example:

```bash
sudo pacman -S nmap hydra sqlmap
```

---

## 🖥️ Running Tools

Run tools directly in the terminal by typing their name. For example:

```bash
nmap -sV 192.168.1.1
```

To display tool help and usage:

```bash
nmap -h
```

---

## 🚨 Security Warning

**Using these tools without permission on systems or networks you do not own is illegal.**

These tools are intended only for educational purposes, authorized security testing, and controlled lab environments.

---

## 🧩 Recommendations for Zenora

* Use multi-language terminals such as wezterm or kitty for better usability.
* Some tools like `wireshark` may require root privileges or special permissions.
* Installing the `zenora-dev-tools` package is recommended to compile tools from source if needed.

---

## 📚 Additional Resources

* [Official BlackArch Website](https://blackarch.org/)
* [BlackArch Tools List](https://blackarch.org/tools.html)
* [Arch Wiki - BlackArch](https://wiki.archlinux.org/title/BlackArch)
* [Metasploit Documentation](https://docs.metasploit.com/)

---

## 🙏 Thanks

Thank you for using Zenora Linux for your security and research needs. For questions or suggestions, feel free to contact us.
