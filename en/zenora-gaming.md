

# Zenora Gaming - Installation & Configuration for Heroic + Wine + proton-ge

Welcome to the official documentation for **Zenora Gaming**. This package provides an optimized environment for running Windows games on Linux. With a single command, you’ll install **Heroic Games Launcher** and a pre-configured **Wine-GE** runtime, ready to play.

---

## 📜 Overview

**Zenora Gaming** is a streamlined Arch Linux package designed to deliver a smooth and effortless experience for playing Windows games on Linux.

This package includes:

- Automatic installation of Heroic Games Launcher
- Pre-configured Wine GE (Gaming Edition)
- Predefined environment variables and runtime libraries
- Full compatibility with Proton, DXVK, and modern gaming tools

---

## 🔧 Features

- ⚙️ Installs Heroic Launcher, Wine GE, and all required dependencies
- 🧰 Includes DXVK, VKD3D, and other graphics compatibility layers
- 🎮 Play Epic & GOG games out-of-the-box with Heroic
- 🧪 Compatible with Lutris, Steam Proton, and other gaming tools
- 🔁 Automatic Wine GE updates from Zenora sources
- 🌙 Designed for both Wayland and X11 environments

---

## 🛠️ Installation

To install Zenora Gaming, run:

```bash
sudo pacman -Syu zenora-gaming
````

This will automatically install:

* `heroic-games-launcher-bin`
* `wine-zenora-ge`
* `zenora-gaming-config`

Custom configuration scripts are also executed to prepare directories and caches for optimal gaming performance.

---

## ⚙️ Initial Configuration

After installation, the following directories will be set up:

```bash
~/.wine-zenora/
~/.config/heroic/
~/.cache/zenora-gaming/
```

To ensure the best performance, it’s recommended to add the following environment variables to your `~/.bashrc` or `~/.zshrc`:

```bash
export WINEPREFIX="$HOME/.wine-zenora"
export DXVK_STATE_CACHE_PATH="$HOME/.cache/zenora-gaming/dxvk"
export PROTON_LOG=1
```

---

## 🎮 Launching Heroic

To launch Heroic Games Launcher, run:

```bash
heroic
```

Log in with your Epic or GOG account and begin installing games. Heroic will automatically use the bundled **Wine GE** runtime provided by this package.

---

## 🧪 Using Wine GE Manually

To test Wine configuration manually:

```bash
WINEPREFIX=~/.wine-zenora winecfg
```

To run an `.exe` file manually:

```bash
WINEPREFIX=~/.wine-zenora wine Setup.exe
```

---

## 🛠️ Troubleshooting

### 1. Game Doesn’t Launch

* Ensure the selected Wine version in Heroic is **wine-zenora-ge**
* Try enabling **Proton Compatibility Mode** in Heroic
* Check the logs at `~/.cache/zenora-gaming/logs/` for errors

### 2. Low FPS or Graphic Issues

* Verify that `vulkan-icd-loader`, `lib32-vulkan-*`, and `nvidia-utils` or `mesa` are installed
* Enable **Esync** and **FSync** in Heroic’s settings

### 3. Font or Language Issues (e.g., missing Persian/Arabic fonts)

Install fonts:

```bash
sudo pacman -S ttf-vazir noto-fonts ttf-liberation
```

---

## 📝 Contributing

We welcome contributions to the **zenora-gaming** package. Feel free to open issues, submit pull requests, or suggest new features on GitHub.

---

## 📚 Additional Resources

* **Heroic Games Launcher GitHub:**
  [https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher)

* **Wine GE Releases (Glorious Eggroll):**
  [https://github.com/GloriousEggroll/wine-ge-custom](https://github.com/GloriousEggroll/wine-ge-custom)

* **DXVK:**
  [https://github.com/doitsujin/dxvk](https://github.com/doitsujin/dxvk)

* **Arch Wiki - Wine:**
  [https://wiki.archlinux.org/title/Wine](https://wiki.archlinux.org/title/Wine)

---

## 🚀 License

This project is licensed under the **MIT License**.
Feel free to use, modify, and redistribute this package with proper credit.

---

## 🙏 Thanks

Thank you for using **Zenora Gaming**! Our goal is to make Windows gaming on Linux accessible and smooth. Enjoy your games and stay tuned for updates.

