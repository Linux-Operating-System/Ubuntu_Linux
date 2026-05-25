# Ubuntu Command Reference

## Package Management (APT)
- Update package lists:
  ```bash
  sudo apt update
  ```
- Upgrade installed packages:
  ```bash
  sudo apt upgrade -y
  ```
- Full distribution upgrade:
  ```bash
  sudo apt full-upgrade -y
  ```
- Install a package:
  ```bash
  sudo apt install <package-name>
  ```
- Remove a package:
  ```bash
  sudo apt remove <package-name>
  ```
- Search for a package:
  ```bash
  apt search <keyword>
  ```

## System Information
- Show OS release info:
  ```bash
  lsb_release -a
  ```
- Kernel version:
  ```bash
  uname -r
  ```
- CPU info:
  ```bash
  lscpu
  ```
- Memory usage:
  ```bash
  free -h
  ```

## Disk Management
- List block devices:
  ```bash
  lsblk
  ```
- Check disk usage:
  ```bash
  df -h
  ```
- Partition tool (cfdisk):
  ```bash
  sudo cfdisk /dev/sda
  ```

## Service Management (systemd)
- List running services:
  ```bash
  systemctl list-units --type=service --state=running
  ```
- Start a service:
  ```bash
  sudo systemctl start <service>
  ```
- Enable service at boot:
  ```bash
  sudo systemctl enable <service>
  ```
- Check service status:
  ```bash
  systemctl status <service>
  ```

## Networking
- Show IP addresses:
  ```bash
  ip addr show
  ```
- Test connectivity:
  ```bash
  ping -c 4 8.8.8.8
  ```
- Modify `/etc/hosts`:
  ```bash
  sudo nano /etc/hosts
  ```

## User Management
- Add a new user:
  ```bash
  sudo adduser <username>
  ```
- Add user to sudo group:
  ```bash
  sudo usermod -aG sudo <username>
  ```
- Delete a user:
  ```bash
  sudo deluser <username>
  ```

## Miscellaneous
- Search file contents:
  ```bash
  grep -r "search_term" /path/to/search
  ```
- Find files by name:
  ```bash
  find / -name "*.conf" 2>/dev/null
  ```
- Archive/Extract tarballs:
  ```bash
  tar -czvf archive.tar.gz /path/to/dir   # create
  tar -xzvf archive.tar.gz                # extract
  ```

> **Tip**: Use `apt-get` and `apt` interchangeably, but `apt` provides a more user‑friendly output.
