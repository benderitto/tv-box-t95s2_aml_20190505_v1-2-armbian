# tv-box-t95s2_aml_20190505_v1-2-armbian
Armbian image for amlogic s905w (t95s2_aml_20190505_v1 2 tv-box board)
# 🖥️ Armbian S905W TV-Box Image

**Armbian (Debian 13 server)** image for TV boxes based on **Amlogic S905W** processor.  

**📝 Used DTB:** `meson-gxl-s905w-tx3-mini.dtb`  

Turn your Android TV box into a **stable Debian server** with root access, eMMC boot, and all the flexibility of Linux.

---

## ⚡ Requirements

- TV box with Amlogic S905W (e.g., T95S2)  
- SD card ≥8GB  
- SD card reader or USB adapter  
- USB keyboard & HDMI display (for first boot)  

---

## 💾 Creating a Bootable SD Card

1. **Download** the Armbian S905W image.  
2. **Insert SD card** into your PC and identify it:

```bash
lsblk
```
⚠ Warning: Make sure you know your SD device (/dev/sdX on Linux). This will erase all data.

Flash the image using dd:

```bash
sudo dd if=Armbian_S905W.img of=/dev/sdX bs=4M status=progress
sync
```
Insert the SD card into the TV box and boot from SD.

🚀 Installing Armbian to eMMC
Boot the box from SD → you’ll see the Armbian login prompt.

Log in as root.

⚠⚠⚠DO NOT SETUP ANY USER! GET root PASSWORD ONLY AND SKIP CREATIN USER!!!⚠⚠⚠

Run the installation script:

```bash
sudo bash /root/install-aml.sh
```
Wait for Copy USR and bootloader setup to finish.

Once complete, power off, remove SD, and power on → Armbian will boot from eMMC.

✅ Post-Installation Tips
Update system:

```bash
sudo apt update && sudo apt upgrade -y
```
Set up networking, Wi-Fi, and install additional packages.

Optionally, backup eMMC to prevent future issues.

⚠ Notes & Tips
Use meson-gxl-s905w-tx3-mini.dtb for stable boot & HDMI output.

Avoid Android files on SD — permissions can break installation.

Troubleshoot via serial console or dmesg logs.

eMMC backup recommended before experimenting.
Armbian (Debian 13 server) image for TV boxes based on **Amlogic S905W** processor.  

**Used DTB:** `meson-gxl-s905w-tx3-mini.dtb`  

This image provides a clean Debian 13 server environment, replacing the stock Android firmware, with proper root access and stable operation on eMMC.

---

## ⚡ Requirements

- TV box with Amlogic S905W (e.g., T95S2)  
- SD card (≥8GB) for flashing Armbian  
- SD card reader or USB adapter  
- USB keyboard and HDMI display (for initial setup)  

---

## 🛠 Creating a Bootable SD Card

1. Download the Armbian image for S905W.  
2. Insert your SD card into your PC. Identify the device (e.g., `/dev/sdX` on Linux).  
3. Flash the image to the SD card using `dd` (Linux/macOS):

```bash
sudo dd if=Armbian_S905W.img of=/dev/sdX bs=4M status=progress
sync
```
