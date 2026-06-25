<div align="center">

# 🐧 Antigravity IDE Installer

![License](https://img.shields.io/badge/License-GPLv3-blue?style=for-the-badge&logo=gnu)
![Platform](https://img.shields.io/badge/Platform-Linux-orange?style=for-the-badge&logo=linux)
![Arch](https://img.shields.io/badge/Arch-x86__64%20%7C%20aarch64-green?style=for-the-badge)
![Shell](https://img.shields.io/badge/Shell-Bash-89e051?style=for-the-badge&logo=gnubash)

A lightweight Bash script to install and update **Antigravity IDE** on Linux.  
Tested on **Fedora** and RHEL-based distros.

</div>

---

## 📦 Requirements

```bash
sudo dnf install -y curl tar python3
```

---

## ⬇️ Install the Script

```bash
sudo curl -fsSL \
  https://raw.githubusercontent.com/mostafa447/linux-ide-installer/main/install-antigravity-ide \
  -o /usr/local/bin/install-antigravity-ide

sudo chmod +x /usr/local/bin/install-antigravity-ide
```

---

## 🚀 Run

```bash
sudo install-antigravity-ide
```

### What happens:

| Step | Action |
|------|--------|
| 🔍 | Detects system architecture (`x86_64` or `aarch64`) |
| 🌐 | Fetches the latest version from Antigravity's download page |
| 📥 | Downloads and extracts the archive |
| 📁 | Installs to `/opt/antigravity-ide/` |
| 🔗 | Creates symlink at `/usr/bin/antigravity-ide` |
| 🖥️ | Registers `.desktop` entry and icon for app launchers |
| 🔒 | Applies SELinux labels automatically (Fedora/RHEL) |
| ⚡ | Skips download if already on the latest version |

---

## 🔄 Update

Re-run the same command — it skips if already up to date:

```bash
sudo install-antigravity-ide
```

---

## 🗑️ Uninstall

```bash
sudo rm -rf /opt/antigravity-ide
sudo rm -f /usr/bin/antigravity-ide /usr/local/bin/install-antigravity-ide
sudo rm -f /usr/share/applications/antigravity-ide.desktop
sudo rm -f /usr/share/icons/hicolor/512x512/apps/antigravity-ide.png
sudo gtk-update-icon-cache -q /usr/share/icons/hicolor
sudo update-desktop-database /usr/share/applications
```

---

## 🖥️ Supported Architectures

| Architecture | Target |
|---|---|
| `x86_64` / `amd64` | `linux-x64` |
| `aarch64` / `arm64` | `linux-arm` |

---

## 📂 Install Paths

| Item | Path |
|---|---|
| 📁 Application | `/opt/antigravity-ide/` |
| 🔗 Binary | `/usr/bin/antigravity-ide` |
| 🖥️ Desktop Entry | `/usr/share/applications/antigravity-ide.desktop` |
| 🎨 Icon | `/usr/share/icons/hicolor/512x512/apps/antigravity-ide.png` |

---

## 📄 License

This project is licensed under the **GNU General Public License v3.0**.  
See [LICENSE](LICENSE) for details.
