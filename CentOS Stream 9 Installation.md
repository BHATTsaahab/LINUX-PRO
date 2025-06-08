# Step-by-Step Guide to Installing CentOS Stream 9

## Prerequisites

### Minimum System Requirements
- **RAM**: 2 GB (4 GB Recommended)
- **Disk Space**: 20 GB (40 GB Recommended)

### Tools Needed
- **USB Drive**: 8 GB or more
- **ISO File**: Download from [centos.org](https://www.centos.org/download/)
- **Partition Plan**: Prepare ahead (see below)

## Step 1: Download CentOS Stream 9 ISO
**URL**: [https://www.centos.org/download/cr](https://www.centos.org/download/cr)

- Select **CentOS Stream 9 DVD ISO**
- Click **Download** and save it on your system

## Step 2: Create Bootable USB

### Tools to Use
- **Windows**: Rufus
- **Linux/macOS**: `dd` or **Etcher**

### Linux Example using `dd`
```bash
sudo d# CentOS Stream 9 Installation Guide (Steps 3–5)

## Step 3: Boot & Start Installation
1. **Reboot your system with USB plugged in**
2. **Enter Boot Menu**: Press **F12**, **ESC**, or **F2**
3. **Select USB Drive as boot option**
4. **Choose "Install CentOS Stream 9"**

## Step 4: Installation Options
1. **Language**: Select your preferred language
2. **Installation Destination**: Select your target disk
3. **Partitioning**: Choose **Custom Partitioning** and configure:
   - `/boot` – 1 GB (ext4)
   - `swap` – Equal to RAM (e.g., 2–4 GB)
   - `/` (root) – Rest of space (xfs recommended)

## Step 5: Post-Installation Setup

### First Login & Update System
```bash
dnf update -yd if=CentOS-Stream-9-*.iso of=/dev/sdX bs=4M status=progress && sync
dnf install epel-release -ydnf install -y wget curl vim git net-tools
This Markdown code can be copied into a `.md` file (e.g., `centos-stream-9-installation-steps-3-5.md`) and uploaded to a GitHub repository, where it will render cleanly with headings, lists, and code blocks. If you’d like to include the earlier steps (e.g., Steps 1 and 2 or prerequisites), combine this with previous content (e.g., Windows/Linux directory structures, bug bounties, or Linux distributions), or generate this in a different format like a **PDF** or **graphics-based note**, please let me know, and I’ll provide the adjusted content or artifact!
