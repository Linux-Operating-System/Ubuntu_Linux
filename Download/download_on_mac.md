# Download Ubuntu on macOS

## 1. Get the ISO Image
1. Open Safari (or your preferred browser) and go to the **Official Ubuntu Download Sources** (`official_sources.md`).
2. Click the link for the desired release, e.g., **Ubuntu Desktop 22.04 LTS**.
3. Save the `.iso` file to a folder such as `~/Downloads/ubuntu-22.04-desktop-amd64.iso`.
4. **Verify checksum**:
   ```bash
   shasum -a 256 ~/Downloads/ubuntu-22.04-desktop-amd64.iso
   ```
   Compare the printed hash with the SHA256 value from `SHA256SUMS`.

## 2. Create a Bootable USB Drive (Optional)
You can use **BalenaEtcher** (free, cross‑platform).
1. Download BalenaEtcher from https://www.balena.io/etcher/ and install it.
2. Insert a USB stick (≥8 GB).
3. Open Etcher → **Select image** → choose the Ubuntu ISO.
4. **Select target** → your USB device.
5. Click **Flash!** and wait for completion.

## 3. Install Ubuntu as Primary OS
1. Reboot the Mac and hold the **Option (⌥)** key to bring up the startup manager.
2. Choose the USB drive (or the ISO if you use the built‑in Apple Boot Picker with `rEFInd`).
3. Select **Try Ubuntu** or **Install Ubuntu**.
4. Follow the installer prompts (similar to Windows guide):
   - Keyboard layout → Continue
   - Updates and other software → Normal installation, optional download updates
   - Installation type → **Erase disk and install Ubuntu** (will delete macOS) or **Something else** for custom partitions.
   - Set time‑zone, user name, password.
5. After installation, the Mac will boot directly into Ubuntu.

## 4. Post‑Installation (Optional)
- Install **Mac hardware drivers** (most work out‑of‑the‑box, but you can install `mac‑fan‑control` if needed).
- Update the system:
  ```bash
  sudo apt update && sudo apt upgrade -y
  ```
- Enable SSH server if you need remote access:
  ```bash
  sudo apt install openssh-server
  ```

---
> **Tip**: Keep the ISO file and checksum for future reinstallations.
