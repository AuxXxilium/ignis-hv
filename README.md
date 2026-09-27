<div align="center">

<img width="160" alt="Ignis" src="assets/ignis.svg">

### Ignis — Hypervisor for your own hardware

Run virtual machines and containers on your own x86-64 PC or server.<br>
Install it once, then manage everything from your browser.

<a href="https://github.com/AuxXxilium/firevisor/releases/latest"><img alt="Download" src="https://img.shields.io/badge/download-red?style=for-the-badge&label=latest&color=%23FF0000"></a>
<a href="https://discord.auxxxilium.tech"><img alt="Discord" src="https://img.shields.io/badge/discord-5865F2?style=for-the-badge&label=chat&color=%235865F2"></a>

</div>

---

> [!IMPORTANT]
> * Ignis is a **complete system** for the machine it runs on. It is installed to the machine's own disks and does not run alongside another operating system.
> * Ignis is free and will stay free forever.

> [!WARNING]
> Installing Ignis **erases every disk you select** for it. Back up anything on those disks first. The project is released for educational and learning purposes only, and I'm not liable for damage or loss of any kind.

---

## ✨ What Ignis does

Ignis turns a PC or server into a small, dedicated host for virtual machines and containers. You install it from a USB stick, and from then on everything is done in the browser at `https://<your-ignis-address>`. No desktop, no separate management tool.

* **Virtual machines**: create, edit, clone and run machines, with BIOS or UEFI and Secure Boot. Each machine can have its own TPM 2.0, so Windows 11 installs without workarounds
* **Screen in the browser**: open any machine's display in a browser tab, and read its serial output even after it has stopped
* **Snapshots and schedules**: take snapshots and roll back to them, and start, shut down or snapshot machines on a timetable. Old snapshots are cleaned up for you
* **Start at boot**: choose which machines start with the host, and in what order
* **Import and export**: bring in an `.ova` or disks from ESXi, Hyper-V or VirtualBox, which are converted for you. Export a machine to move it elsewhere
* **Containers**: run Docker containers and compose projects next to your machines. You can update them by hand or on a schedule, and give each one a disk priority
* **Passthrough**: give a machine a real graphics card, network card, disk controller, USB device or whole disk. Ignis shows which devices can be handed over safely
* **NVIDIA for containers**: an optional extension adds the NVIDIA driver, so containers can use the GPU
* **Storage**: install to one disk or several with software RAID, and add more disks later as extra volumes (ext4, XFS or btrfs, alone or as RAID)
* **Networking**: private networks with NAT, or bridges that put machines directly on your network. VLANs and bonded network cards are supported
* **Users and roles**: admin, operator and viewer accounts, each limited to the machines and pages you choose
* **Host controls**: live monitoring, CPU speed and power settings, fan curves, time, services, and HTTPS with your own certificate or a free one from Let's Encrypt
* **Extensions**: add services, commands or pages to the appliance, and they survive updates
* **Safe updates**: install a new version from a file or a link. The previous version is kept, so you can go back to it from the boot menu

---

## 🧭 How it works

```
USB stick → Installer → choose disks and RAID → Ignis on the machine's own disks
                                                   └─ web interface at https://<address>
                                                        ├─ virtual machines (KVM/QEMU)
                                                        ├─ containers (Docker)
                                                        └─ host: storage, network, users, updates
```

Ignis keeps two things apart: **the system**, which is small and replaced as a whole by each update, and **your data**: machines, disk images, ISOs, containers and settings. Your data lives on its own volume, so an update never touches it and a failed update can be undone.

---

## 🖥️ The web interface

| Page | What you do there |
| :-- | :-- |
| **Virtual Machines** | Create, start, stop and edit machines, open their display, take snapshots, clone, import and export |
| **Containers** | Run containers and compose projects, pull images, update and clean up |
| **Network** | Private and bridged networks for machines, plus the host's own address, VLANs and bonds |
| **Storage** | Disk images, ISOs, uploads and extra storage volumes |
| **Schedules** | Timed start, shutdown, snapshot and container update tasks |
| **Passthrough** | Graphics cards, PCI devices and USB devices that machines can use |
| **Users** | Accounts, roles, and which machines and pages each user sees |
| **System** | Network, time, services, HTTPS and updates |
| **Monitor** | Live CPU, memory, network and temperature readings, plus CPU and fan control |
| **Extensions** | Install, enable and remove extensions |
| **Info** | What this host supports, and a report to copy into a bug report |

Every page has a **?** button with help written for that page, including what common error messages mean.

The interface has a light and a dark mode and several accent colours to choose from.

---

## 📋 What you need

* An x86-64 machine you own, with virtualisation (Intel VT-x or AMD-V) turned on in the bios
* For passthrough: an IOMMU (Intel VT-d or AMD-Vi), also turned on in the bios
* A USB stick for the installer
* One or more disks for Ignis. 64 GB or more is a good start, and your machines need room on top of that
* Two or more disks if you want RAID
* A wired network

The **Info** page shows what your host supports once Ignis is running, and says what is missing if something is.

---

## 💿 Installing

1. Download the latest ISO from the [releases](https://github.com/AuxXxilium/firevisor/releases/latest) and write it to a USB stick
2. Boot the machine from the stick and choose **Install**
3. Pick the disks to install to. **Everything on them is erased**
4. Choose how the disks work together, for the system and for your data separately: a single disk, a mirror, or another RAID level. Only the levels your disk count allows are offered
5. Set a root password
6. Remove the stick and reboot. The screen shows the address to open in your browser. Sign in as `root`

With several disks, Ignis puts a boot loader on every one of them, so the machine still boots if one disk fails.

---

## ⬆️ Updates

Updates are done under **System → Update**. Give it an update file, or a link to one from the [releases](https://github.com/AuxXxilium/firevisor/releases/latest). Ignis prepares the new version next to the running one, and your machines keep running while it does. When you click **Apply**, it restarts into the new version.

Your settings, passwords and certificates are carried across. Machines, disk images, containers, networks and users are never touched by an update.

The previous version is kept for one update cycle. If something is wrong, choose it from the boot menu to go back.

---

## 🔒 Security

* Every action in the interface checks who is signed in and what they are allowed to do. Hiding a page in the interface is not what protects it
* Failed sign-ins are rate-limited, and repeated guessing at the login page or SSH gets the address blocked for a while
* A machine's display is only reachable through the signed-in web interface, never directly over the network
* HTTPS is available with a self-signed certificate, one you upload, or a free one from Let's Encrypt
* Extensions and containers run with a lot of access to the host, so install only what you trust. Only admins can manage them

---

## 🧰 More from the Arc Project

| Project | Description |
| :-- | :-- |
| [Arc Loader](https://github.com/AuxXxilium/arc) | Redpill loader for DSM 7.x |
| [arx](https://github.com/AuxXxilium/arx) | The evolution of Arc: set up entirely from your browser |
| [Arc Control](https://github.com/AuxXxilium/arc-control) | DSM app for loader settings, monitoring and hardware tuning |
| [AuxXxilium](https://github.com/AuxXxilium) | Everything else from the Arc Project |

---

### Developer

- <a href="https://github.com/AuxXxilium">AuxXxilium</a>
- <a href="https://github.com/FulcrumCode">Fulcrum</a>

### License

GPL-3.0. The included third-party drivers keep their own licenses.

<div align="center">

[![Stars](https://img.shields.io/github/stars/AuxXxilium/firevisor?style=for-the-badge&logo=github)](https://github.com/AuxXxilium/firevisor)
[![Discord](https://img.shields.io/discord/639072565155069962?style=for-the-badge&logo=discord&label=Discord)](https://discord.auxxxilium.tech)

</div>
