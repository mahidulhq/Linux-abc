
# Fedora Linux Command Line Cheatsheet

A complete, professional reference for Fedora Linux commands, from beginner to advanced.

---

## Filesystem and Directory Management

```bash
pwd                       # Show current working directory
ls                        # List directory contents
ls -la                    # Long listing including hidden files
cd /path/to/dir           # Change directory
mkdir newdir              # Create a new directory
rmdir dir                 # Remove empty directory
rm -r dir                 # Remove directory and contents
touch file.txt            # Create an empty file
cp file1 file2            # Copy file1 to file2
cp -r dir1 dir2           # Copy directories recursively
mv file newname           # Rename or move file
rm file.txt               # Delete file
```

---

## File Permissions and Ownership

```bash
chmod 755 file            # Set permissions (owner=rwx, group=rx, others=rx)
chmod -R 755 dir/         # Apply permissions recursively
chown user:group file     # Change file owner and group
ls -l                     # List files with permissions
umask                     # Show default permission mask
```

---

## Process Management

```bash
ps aux                    # List all running processes
top                       # Dynamic real-time process view
htop                      # Interactive process monitor (install: dnf install htop)
kill PID                  # Terminate process by PID
killall name              # Terminate all processes by name
nice -n 10 command        # Run command with specific priority
renice -n -5 PID          # Change running process priority
```

---

## User and Group Management

```bash
adduser username          # Add new user
passwd username           # Set password for user
usermod -aG wheel user    # Add user to 'wheel' (sudo) group
deluser username          # Delete user
groupadd groupname        # Create new group
gpasswd -a user group     # Add user to group
id user                   # Show user ID and groups
```

---

## Disk and Memory Usage

```bash
df -h                     # Disk usage of mounted filesystems
du -sh dir/               # Disk usage of a directory
free -m                   # Memory usage
swapon -s                 # Show swap usage
lsblk                     # List block devices
mount /dev/sdX /mnt       # Mount device
umount /mnt               # Unmount device
```

---

## Networking Commands

```bash
ip a                      # Show IP addresses
ip r                      # Show routing table
ping example.com          # Check network connectivity
dig example.com           # DNS lookup
nslookup example.com      # DNS resolver tool
traceroute example.com    # Trace route to host
wget http://url           # Download file
curl http://url           # Fetch web resource
nmcli                     # NetworkManager command-line tool
```

---

## System Monitoring and Logs

```bash
uptime                   # Show system uptime
dmesg                    # Kernel messages
journalctl               # Systemd log viewer
journalctl -xe           # Show recent critical logs
systemctl status service # Show status of a service
```

---

## System Services (systemd)

```bash
systemctl status sshd           # Check service status
systemctl start sshd            # Start a service
systemctl stop sshd             # Stop a service
systemctl restart sshd          # Restart a service
systemctl enable sshd           # Enable service at boot
systemctl disable sshd          # Disable autostart
systemctl list-units --type=service  # List all services
```

---

## Package Management Comparison (APT vs DNF vs Pacman)

| Task | APT (Debian/Ubuntu) | DNF (Fedora) | Pacman (Arch) |
|------|----------------------|--------------|----------------|
| Update package index | `sudo apt update` | `sudo dnf check-update` | `sudo pacman -Sy` |
| Upgrade packages | `sudo apt upgrade` | `sudo dnf upgrade` | `sudo pacman -Su` |
| Install package | `sudo apt install pkg` | `sudo dnf install pkg` | `sudo pacman -S pkg` |
| Remove package | `sudo apt remove pkg` | `sudo dnf remove pkg` | `sudo pacman -R pkg` |
| Clean cache | `sudo apt clean` | `sudo dnf clean all` | `sudo pacman -Sc` |

---

## Archiving and Compression

```bash
tar -cvf archive.tar dir/      # Create tar archive
tar -xvf archive.tar           # Extract tar
zip file.zip file1 file2       # Create zip
unzip file.zip                 # Extract zip
gzip file                      # Compress file
gunzip file.gz                 # Decompress file
```

---

## Search and Filters

```bash
grep 'text' file               # Search text in file
find / -name "file.txt"        # Find file by name
locate file.txt                # Fast file location (needs updatedb)
awk '{print $1}' file.txt      # Print first column
sed 's/old/new/g' file.txt     # Replace text in file
```

---

## Scripting and Shell Utilities

```bash
bash script.sh                # Run shell script
chmod +x script.sh            # Make script executable
echo "text"                   # Print text
read var                      # Read input into variable
sleep 5                       # Pause script
date                          # Show current date and time
```

---

## Crontab and Scheduling

```bash
crontab -e                    # Edit crontab
crontab -l                    # List scheduled jobs
@reboot command               # Run command at boot
0 2 * * * command             # Schedule: 2:00 AM daily
```

---

## Boot Process and GRUB

```bash
grub2-mkconfig -o /boot/grub2/grub.cfg  # Regenerate GRUB config
grub2-install /dev/sdX                  # Install GRUB bootloader
systemctl reboot                        # Reboot system
systemctl poweroff                      # Shutdown system
```

---

## Security Tools

```bash
sudo dnf install ufw                   # Install Uncomplicated Firewall
sudo ufw enable                        # Enable firewall
sudo ufw allow ssh                     # Allow SSH
sudo ufw status                        # Show status
sudo dnf install fail2ban              # Install Fail2Ban
sudo systemctl enable fail2ban --now   # Start Fail2Ban
```

---
**Sources**: Fedora Docs, Arch Wiki, Debian Manual.

