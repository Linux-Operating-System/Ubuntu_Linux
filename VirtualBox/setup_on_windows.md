# Install Ubuntu in Oracle VirtualBox on Windows

## 1. Install Oracle VirtualBox
1. Download the latest Windows installer from the official site: https://www.virtualbox.org/wiki/Downloads
2. Run the installer and follow the wizard (default options are fine). Reboot if prompted.

## 2. Create a New Ubuntu VM
1. Open **VirtualBox** → **New**.
2. Name: `Ubuntu 22.04` (or any name you like).
3. Type: **Linux**, Version: **Ubuntu (64-bit)**.
4. Allocate Memory: **4096 MB** (or more if available).
5. Create a Virtual Hard Disk → **VDI**, dynamically allocated, size **25 GB** (or larger).

## 3. Attach the Ubuntu ISO
1. Select the newly created VM → **Settings** → **Storage**.
2. Under **Controller: IDE**, click the empty optical drive and then the small CD icon → **Choose a disk file**.
3. Browse to the Ubuntu ISO you downloaded (e.g., `C:\Downloads\ubuntu-22.04-desktop-amd64.iso`).

## 4. Adjust System Settings (Optional but recommended)
- **System > Motherboard**: Enable **EFI** (only for UEFI‑based ISOs).
- **Processor**: Allocate 2‑4 CPU cores.
- **Display > Screen**: Increase **Video Memory** to 128 MB.

## 5. Start the VM and Install Ubuntu
1. Click **Start**.
2. The VM will boot from the ISO – choose **Install Ubuntu**.
3. Follow the regular Ubuntu installer steps (keyboard, updates, installation type → **Erase disk and install Ubuntu** – this only erases the virtual disk, not your host).
4. When installation finishes, the VM will reboot. You may be prompted to remove the ISO – go back to **Storage** and detach it, then start the VM again.

## 6. Post‑Installation Tweaks
- Install **Guest Additions** for better mouse/clipboard integration:
  ```bash
  sudo apt update && sudo apt install -y build-essential dkms linux-headers-$(uname -r)
  sudo apt install -y virtualbox-guest-utils
  ```
- Set up **Shared Folders** in VirtualBox settings → **Shared Folders** → **Add** → folder path on Windows and mount it inside Ubuntu:
  ```bash
  sudo mkdir /mnt/shared
  sudo mount -t vboxsf SharedFolderName /mnt/shared
  ```
- Adjust display resolution via **View > Auto-resize Guest Display**.

---
> **Tip**: Snapshots – take a snapshot after a fresh install so you can revert easily.
