# Essential Ubuntu Linux Commands

## System Information
- `uname -a` – display kernel and OS info
- `lsb_release -a` – Ubuntu version details
- `hostnamectl` – show hostname and hardware info

## Filesystem Navigation
- `ls -la` – list all files with permissions
- `cd /path/to/dir` – change directory
- `pwd` – print working directory
- `tree` – directory tree (install with `sudo apt install tree`)

## File Operations
- `cp source dest` – copy files
- `mv source dest` – move/rename files
- `rm file` – delete file (use `-r` for directories)
- `chmod 755 file` – change permissions
- `chown user:group file` – change ownership

## Package Management (APT)
- `sudo apt update` – refresh package lists
- `sudo apt upgrade` – upgrade installed packages
- `sudo apt install package_name` – install a package
- `sudo apt remove package_name` – remove a package
- `apt search keyword` – search for packages

## System Monitoring
- `top` / `htop` – view running processes
- `df -h` – disk space usage
- `free -h` – memory usage
- `systemctl status service` – check service status

## Networking
- `ip a` – show network interfaces
- `ping hostname` – test connectivity
- `netstat -tulpn` – list listening ports
- `sudo apt install net-tools` – provides `netstat`

## User Management
- `adduser username` – create new user
- `deluser username` – delete user
- `usermod -aG sudo username` – add to sudo group

## Service Management (systemd)
- `sudo systemctl start service`
- `sudo systemctl stop service`
- `sudo systemctl enable service`
- `sudo systemctl disable service`

## Miscellaneous
- `cat file` – display file contents
- `grep 'pattern' file` – search within files
- `sudo shutdown -h now` – immediate shutdown
- `sudo reboot` – reboot system

> **Tip**: Most commands have `--help` for usage details, and you can use the man pages (`man <command>`).
