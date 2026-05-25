# Install Ubuntu in Oracle VirtualBox on macOS

## 1. Install Oracle VirtualBox
1. Visit the official download page: https://www.virtualbox.org/wiki/Downloads
2. Download the **OS X hosts** DMG.
3. Open the DMG and run the installer. macOS may warn about system extensions – allow them in **System Settings → Security & Privacy** and reboot if prompted.

## 2. Create a New Ubuntu VM
1. Launch **VirtualBox** → **New**.
2. Name: `Ubuntu 22.04`.
3. Type: **Linux**, Version: **Ubuntu (64-bit)**.
4. Allocate Memory: **4096 MB** (or more if you have RAM).
5. Create a Virtual Hard Disk → **VDI**, dynamically allocated, size **25 GB** (or larger).

## 3. Attach the Ubuntu ISO
1. Select the new VM → **Settings** → **Storage**.
2. Under **Controller: SATA**, click the empty optical drive, then the CD icon → **Choose a disk file**.
3. Browse to the Ubuntu ISO you downloaded (e.g., `~/Downloads/ubuntu-22.04-desktop-amd64.iso`).

## 4. Adjust System Settings (Optional)
- **System > Motherboard**: Enable **EFI** if the ISO is EFI‑based.
- **Processor**: Allocate 2‑4 CPU cores.
- **Display > Screen**: Increase **Video Memory** to 128 MB and enable **HiDPI** for retina displays.

## 5. Start the VM and Install Ubuntu
1. Click **Start**. The VM boots from the ISO.
2. Choose **Install Ubuntu** (or **Try Ubuntu** first).
3. Follow the standard Ubuntu installer steps (keyboard, updates, installation type → **Erase disk and install Ubuntu** – this only erases the virtual disk).
4. When the installer asks to remove the installation medium, go back to **Settings → Storage** and detach the ISO, then reboot the VM.

## 6. Post‑Installation Tweaks
- **Install Guest Additions** for better mouse/clipboard integration:
  ```bash
  sudo apt update && sudo apt install -y build-essential dkms linux-headers-$(uname -r)
  sudo apt install -y virtualbox-guest-utils
  ```
- **Shared Folders**: In VirtualBox settings → **Shared Folders** → **Add** a folder from macOS, then mount inside Ubuntu:
  ```bash
  sudo mkdir /mnt/shared
  sudo mount -t vboxsf SharedFolderName /mnt/shared
  ```
- Adjust display resolution via **View → Auto-resize Guest Display**.

---
> **Tip**: Take a **snapshot** after a fresh install; you can revert to it if you want to try a different configuration.
