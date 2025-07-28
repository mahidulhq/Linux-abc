
### 📦 Linux Package Management: APT vs DNF vs Pacman

Linux package management across **Debian-based**, **Fedora-based**, and **Arch-based** distributions.
---

#### 📊 Task-Based Command Comparison

| Task | Debian/Ubuntu (`apt`) | Fedora/RHEL (`dnf`) | Arch Linux (`pacman`) |
|------|------------------------|----------------------|------------------------|
| **Update package list** | `sudo apt update` | `sudo dnf check-update` | `sudo pacman -Sy` |
| **Upgrade packages** | `sudo apt upgrade` | `sudo dnf upgrade` | `sudo pacman -Su` |
| **Install package** | `sudo apt install package` | `sudo dnf install package` | `sudo pacman -S package` |
| **Remove package** | `sudo apt remove package` | `sudo dnf remove package` | `sudo pacman -R package` |
| **Remove + config files** | `sudo apt purge package` | `sudo dnf remove package` | `sudo pacman -Rns package` |
| **List installed packages** | `dpkg -l` | `dnf list installed` | `pacman -Q` |
| **Search for package** | `apt search keyword` | `dnf search keyword` | `pacman -Ss keyword` |
| **Show package info** | `apt show package` | `dnf info package` | `pacman -Si package` |
| **Clean package cache** | `sudo apt clean` | `sudo dnf clean all` | `sudo pacman -Sc` |
| **Show upgradeable packages** | `apt list --upgradable` | `dnf check-update` | `pacman -Qu` |
| **Reinstall package** | `sudo apt install --reinstall package` | `sudo dnf reinstall package` | `sudo pacman -S package` |
| **Show dependencies** | `apt depends package` | `dnf repoquery --requires package`<br>(`dnf-plugins-core`) | `pactree package`<br>(from `pkgtools`) |

---

#### ⚙️ System & Config File Differences

| Feature | APT (Debian/Ubuntu) | DNF (Fedora/RHEL) | Pacman (Arch) |
|--------|----------------------|--------------------|----------------|
| Main Config | `/etc/apt/` | `/etc/dnf/` | `/etc/pacman.conf` |
| Source List | `/etc/apt/sources.list` | `/etc/yum.repos.d/` | `/etc/pacman.d/mirrorlist` |
| Rollback Support | ❌ Not supported | ✅ Via `dnf history` | ❌ Manual only |
| GUI Frontend | Synaptic | dnfdragora | Pamac (optional) |

---
