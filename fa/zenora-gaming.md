# Zenora Gaming - نصب و پیکربندی Heroic + Wine

به مستندات رسمی **Zenora Gaming** خوش آمدید. این بسته به‌منظور فراهم‌سازی محیطی آماده برای اجرای بازی‌های Windows در لینوکس طراحی شده است. با نصب این بسته، شما به‌طور خودکار نرم‌افزار **Heroic Games Launcher** به همراه نسخه بهینه‌شده‌ای از **Wine** را دریافت می‌کنید.

---

## 📜 مروری کلی

**Zenora Gaming** یک بسته‌ی آماده برای Arch Linux و توزیع‌های مشتق‌شده است که هدف آن فراهم‌سازی تجربه‌ای روان و بی‌دردسر برای اجرای بازی‌های ویندوزی بر بستر لینوکس است.

این بسته شامل موارد زیر است:

- نصب خودکار Heroic Games Launcher
- نصب Wine-GE سفارشی (نسخه‌ای ویژه برای بازی‌ها)
- پیکربندی خودکار متغیرهای محیطی و کتابخانه‌های مورد نیاز بازی‌ها
- هماهنگی کامل با Proton و DXVK برای سازگاری بهتر

---

## 🔧 ویژگی‌ها

- ⚙️ نصب خودکار Heroic Launcher، Wine GE و کتابخانه‌های مورد نیاز
- 🧰 پشتیبانی از DXVK، VKD3D و سایر ابزارهای گرافیکی ویندوزی
- 🎮 اجرای بازی‌های Epic و GOG بدون نیاز به نصب دستی
- 🧪 هماهنگی با ابزارهایی مانند **Lutris** و **Steam Proton**
- 🔁 به‌روزرسانی خودکار نسخه Wine GE از منابع Zenora
- 🌙 طراحی‌شده برای عملکرد بهینه در محیط‌های Wayland و X11

---

## 🛠️ نصب بسته

برای نصب، کافی‌ست از دستور زیر استفاده کنید:

```bash
sudo pacman -Syu zenora-gaming
````

این دستور بسته‌های زیر را به‌طور خودکار نصب می‌کند:

* `heroic-games-launcher-bin`
* `wine-zenora-ge`
* `zenora-gaming-config`

همچنین، اسکریپت‌هایی برای آماده‌سازی پوشه‌های بازی و کش‌های گرافیکی اجرا می‌شوند.

---

## ⚙️ تنظیمات اولیه

پس از نصب، تنظیمات اولیه شامل آماده‌سازی پوشه‌های زیر انجام خواهد شد:

```bash
~/.wine-zenora/
~/.config/heroic/
~/.cache/zenora-gaming/
```

برای اجرای بهتر بازی‌ها، پیشنهاد می‌شود تنظیمات زیر به متغیرهای محیطی اضافه شوند (در `~/.bashrc` یا `~/.zshrc`):

```bash
export WINEPREFIX="$HOME/.wine-zenora"
export DXVK_STATE_CACHE_PATH="$HOME/.cache/zenora-gaming/dxvk"
export PROTON_LOG=1
```

---

## 🎮 اجرای Heroic

برای اجرای لانچر Heroic:

```bash
heroic
```

پس از ورود به حساب Epic یا GOG خود، می‌توانید بازی‌ها را نصب و اجرا کنید. Heroic به‌طور خودکار از **Wine GE** پیکربندی‌شده استفاده خواهد کرد.

---

## 🧪 تست Wine GE

برای تست Wine به‌صورت دستی (مفید برای عیب‌یابی):

```bash
WINEPREFIX=~/.wine-zenora winecfg
```

و برای اجرای فایل `.exe` به شکل زیر عمل کنید:

```bash
WINEPREFIX=~/.wine-zenora wine Setup.exe
```

---

## 🛠️ رفع مشکلات رایج

### 1. عدم اجرای بازی

* مطمئن شوید که بازی در Heroic روی Wine GE پیکربندی‌شده اجرا می‌شود.
* در صورت نیاز، از گزینه "Run with Proton" در Heroic استفاده کنید.
* بررسی لاگ اجرای بازی از مسیر `~/.cache/zenora-gaming/logs/`

### 2. مشکل در گرافیک یا FPS پایین

* اطمینان حاصل کنید که `vulkan-icd-loader`, `lib32-vulkan-*`, و `nvidia-utils` یا `mesa` نصب هستند.
* فعال‌سازی حالت **Esync** و **FSync** از داخل Heroic پیشنهاد می‌شود.

### 3. مشکل با زبان فارسی یا قلم‌ها

```bash
sudo pacman -S ttf-vazir noto-fonts ttf-liberation
```

---

## 📝 مشارکت در توسعه

هرگونه مشارکت در توسعه این بسته از طریق GitHub مورد استقبال قرار می‌گیرد. برای گزارش باگ‌ها یا پیشنهاد ویژگی‌های جدید، لطفاً یک Issue جدید باز کنید.

---

## 📚 منابع بیشتر

* **صفحه رسمی Heroic Launcher:**
  [https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher)

* **Wine GE Releases:**
  [https://github.com/GloriousEggroll/wine-ge-custom](https://github.com/GloriousEggroll/wine-ge-custom)

* **DXVK:**
  [https://github.com/doitsujin/dxvk](https://github.com/doitsujin/dxvk)

* **Arch Wiki - Wine:**
  [https://wiki.archlinux.org/title/Wine](https://wiki.archlinux.org/title/Wine)

---

## 🚀 مجوز

این بسته تحت مجوز **MIT** ارائه شده است. شما می‌توانید از آن آزادانه استفاده، ویرایش و بازتوزیع کنید.

---

## 🙏 سپاس

از اینکه از **Zenora Gaming** استفاده می‌کنید سپاسگزاریم. هدف ما فراهم کردن بستری لذت‌بخش برای اجرای بازی‌ها در لینوکس است. با ما همراه باشید!

