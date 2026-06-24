# Linux IDE Installer

A lightweight Bash script to install and update **Antigravity IDE** on Linux systems (Fedora / RHEL-based recommended).

---

## Requirements

```bash
sudo dnf install -y curl tar python3
```

## Install the Script

```bash
sudo curl -fsSL \
  https://raw.githubusercontent.com/mostafa447/linux-ide-installer/main/install-antigravity-ide \
  -o /usr/local/bin/install-antigravity-ide

sudo chmod +x /usr/local/bin/install-antigravity-ide
```

## Run

```bash
sudo install-antigravity-ide
```

The script will:
- Detect your architecture (`x86_64` or `aarch64`)
- Download the latest Antigravity IDE release
- Install to `/opt/antigravity-ide/`
- Create a symlink at `/usr/local/bin/antigravity-ide`
- Register a `.desktop` entry and icon
- Apply SELinux labels automatically (Fedora)

## Update

Re-run the same command — it skips download if already on the latest version:

```bash
sudo install-antigravity-ide
```

## Uninstall

```bash
sudo rm -rf /opt/antigravity-ide
sudo rm -f /usr/local/bin/antigravity-ide /usr/local/bin/install-antigravity-ide
sudo rm -f /usr/share/applications/antigravity-ide.desktop
sudo rm -f /usr/share/icons/hicolor/512x512/apps/antigravity-ide.png
sudo gtk-update-icon-cache -q /usr/share/icons/hicolor
sudo update-desktop-database /usr/share/applications
```

## Supported Architectures

| Architecture | Target |
|---|---|
| x86_64 / amd64 | `linux-x64` |
| aarch64 / arm64 | `linux-arm` |

## Install Paths

| Item | Path |
|---|---|
| Application | `/opt/antigravity-ide/` |
| Binary | `/usr/local/bin/antigravity-ide` |
| Desktop Entry | `/usr/share/applications/antigravity-ide.desktop` |
| Icon | `/usr/share/icons/hicolor/512x512/apps/antigravity-ide.png` |

---

## License

MIT
