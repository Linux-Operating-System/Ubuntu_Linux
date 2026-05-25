# Download Ubuntu on Windows

## 1. Get the ISO Image
1. Open your web browser and navigate to the **Official Ubuntu Download Sources** page (see `official_sources.md`).
2. Click the link for the desired release (e.g., **Ubuntu Desktop 22.04 LTS**).
3. Save the `.iso` file to a known location (e.g., `C:\Downloads\ubuntu-22.04-desktop-amd64.iso`).
4. **Verify checksum**:
   ```powershell
   $hash = Get-FileHash -Path "C:\Downloads\ubuntu-22.04-desktop-amd64.iso" -Algorithm SHA256
   Write-Host $hash.Hash
   ```
   Compare the output with the SHA256 value from `SHA256SUMS`.

## 2. Create a Bootable USB Drive
You can use **Rufus** (free utility).
1. Download Rufus from https://rufus.ie.
2. Insert a USB stick (≥8 GB) and launch Rufus.
3. Select the USB device, choose **Disk or ISO image (Please select)**, then browse to the downloaded Ubuntu ISO.
4. Keep the default **Partition scheme: MBR** for BIOS/UEFI compatibility.
5. Click **START** → **Write in ISO Image mode** → **OK**.

## 3. Install Ubuntu as Primary OS
1. Restart the computer and press the boot‑menu key (often **F12**, **Esc**, or **Del**) to select the USB drive.
2. Choose **Try Ubuntu** or **Install Ubuntu**.
3. Follow the installer prompts:
   - **Keyboard layout** → **Continue**
   - **Updates and other software** → select "Normal installation" and check "Download updates while installing" if you have internet.
   - **Installation type** → choose **Erase disk and install Ubuntu** (be aware this wipes Windows).
   - Set your **time zone**, **username**, and **password**.
4. After installation, the system will reboot into Ubuntu.

## 4. Post‑Installation Tweaks (Optional)
- Enable **Proprietary drivers**: `Software & Updates → Additional Drivers`.
- Update the system:
  ```powershell
  wsl -d Ubuntu -e bash -c "sudo apt update && sudo apt upgrade -y"
  ```
- Install **OpenSSH Server** for remote access:
  ```bash
  sudo apt install openssh-server
  ```

---
> **Tip**: Keep the ISO and checksum file for future reinstallations.
