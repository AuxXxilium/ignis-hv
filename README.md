<div align="center">

<img width="160" alt="Ignis" src="assets/ignis.svg">

### Ignis — The all-in-one hypervisor for your own hardware

Run virtual machines, containers and apps on your own x86-64 PC or server.<br>
Install it once, then manage everything from your browser.

<a href="https://github.com/AuxXxilium/ignis-hv/releases/latest"><img alt="Download" src="https://img.shields.io/badge/download-red?style=for-the-badge&label=latest&color=%23FF0000"></a>
<a href="https://discord.auxxxilium.tech"><img alt="Discord" src="https://img.shields.io/badge/discord-5865F2?style=for-the-badge&label=chat&color=%235865F2"></a>

<br><br>

<img alt="Ignis: the Virtual Machines page" src="assets/screenshots/machines.png" width="100%">

</div>

---

> [!IMPORTANT]
> * Ignis is a **complete system** for the machine it runs on. It is installed to the machine's own disks and does not run alongside another operating system.
> * Ignis is free and will stay free forever.

> [!WARNING]
> Installing Ignis **erases every disk you select** for it. Back up anything on those disks first. The project is released for educational and learning purposes only, and I'm not liable for damage or loss of any kind.

---

## ✨ What Ignis does

Ignis turns a PC or server into a small, dedicated host for virtual machines, containers and apps. You install it from a USB stick, and from then on you do everything in your browser at `https://<your-ignis-address>`. You don't need a desktop or any other program.

### 🖥️ Virtual machines

* **Windows and Linux**: create, edit, clone and run Windows, Windows Server and Linux machines. Each machine can have its own TPM 2.0 and Secure Boot with Microsoft's keys, so Windows 11 installs without workarounds
* **Screen in the browser**: open a machine's display in a browser tab. You can change its CD/DVD, and shut it down, reset it or power it off from the same window
* **Snapshots and backups**: save a machine's state and go back to it. Back it up on a timetable, and old snapshots are cleaned up for you
* **Schedules for everything**: plan machine tasks, container updates and the tasks of your apps, such as nightly website and mail backups, in one place
* **Import and export**: bring in machines from ESXi, Hyper-V, VirtualBox or an `.ova` file, and export them as `.ova` for other systems
* **Your choice of CPU**: give a machine the host's own processor, or a fixed generation it keeps when you move it to other hardware
* **Passthrough**: give a machine a real graphics card, network card, disk controller, USB device or a whole disk
* **Start at boot**: choose which machines start with the host, and in what order

### 📦 Containers

* **Docker in the browser**: create and run containers and compose projects, see their logs and live usage, and manage their networks and volumes
* **Easy updates**: update by hand or on a timetable. If an update fails, the old version comes back
* **Linux containers (LXC)**: whole Linux systems that start in seconds, on their own page. Pick Debian, Ubuntu, Alpine and many more from a list of ready images, or bring your own. Each one gets a console in the browser, CPU and memory limits, your machines' networks and the shared folders you choose, with snapshots, backups and clones. They are kept apart from the host by default

### 🗄️ Storage and the host

* **Disks your way**: the system on one disk or a mirror, your data on one disk or software RAID. Add more disks later as extra volumes
* **Storage Health**: see disk errors, run disk tests, check your data for hidden damage once a month, and let idle disks spin down
* **Storage Analyzer**: what uses the space, folder by folder in a map, by kind of file and by age, with the biggest files and folders, duplicates, empty folders, files nobody changed for three years, and how the used space grows. It scans at night, at the lowest priority
* **Monitor and History**: what the host and every machine are doing right now, and over the last hour, day, week or month. Live readings refresh every few seconds, and you can switch that off
* **Several hosts as one**: link your Ignis hosts and run their machines from one interface. A machine can have a standby copy on a second host, ready if the first one fails
* **For your smart home**: a read-only interface for Home Assistant, Prometheus and similar apps

### 🌐 Network

* **Networks for your machines**: private networks, bridges that put machines straight on your network, or a VLAN from your switch for them. Ignis's own VLANs and bonded network cards are set up under Network & Firewall
* **Network & Firewall**: Ignis's own addresses, a firewall that decides who reaches which service, blocklists, countries and port scans, port forwards, and a **router**: one network card to the internet, the others as local networks. Each local network can reach the internet or stay local only, may or may not reach the other local networks, and gets its own DHCP range if you switch it on. A device list shows who is connected, with names of your own and fixed addresses
* **Network boot**: Ignis can start the computers on your network over the network, BIOS and UEFI alike: Ignis Recovery, ISOs from Storage, or netboot.xyz's menu. One switch turns it on
* **HTTPS**: with your own certificate or a free one from Let's Encrypt

### 🔐 Sign-in and security

* **Users and roles**: admin, operator and viewer accounts, each limited to the machines and pages you choose. Every permission says what it allows, and which of your apps it opens
* **Two-factor sign-in**: with an authenticator app, recovery codes for emergencies and codes by email. A browser you trust can skip the code for 30 days
* **Screen lock**: Ignis locks itself after the time you choose, and you unlock it with your password

### 🧩 Apps

Add apps from the **Extensions** tab. Install only the ones you need; each one is updated on its own, apart from Ignis. In the sidebar your apps sit right under the machines, grouped into **Files**, **Media**, **Web & Mail**, **Network**, **Apps** and **Misc**, and each group can be folded away. When an app requires another one, the tab tells you and installs it with a click, and apps you have switched on start by themselves when Ignis starts.

Apps that belong together come as one package: **Web & Mail**, **Drive & Shares**, **Backup & Sync**, the **Graphics Runtime**, and **Docker** with App Station. One switch turns the whole package on or off, updates and removes it, and its page has a tab for each part. If you had one of the parts installed on its own before, it moves into its package with everything it holds.

<sub>Each screenshot shows the app's own page, some with sample data.</sub>

#### 📁 Files

##### Drive & Shares

**Drive** shows your shared folders in the browser: upload, preview and share files with a link, also with people who have no account. The preview opens Office files, OpenDocument, PDF, e-books, Markdown, code and archives. **Network Shares** shares the folders over SMB like a NAS, and over SFTP and FTPS if you want.

<img alt="Drive: the Family share with its folders" src="assets/screenshots/apps/drive.png" width="100%">
<p><img alt="Drive: share links with their limits" src="assets/screenshots/apps/drive-links.png" width="49%"> <img alt="Network Shares: the shares" src="assets/screenshots/apps/shares.png" width="49%"></p>

##### Office Editor

Edits Word, Excel and PowerPoint files (and OpenDocument) right in Drive's preview, with several people in one document at once. It starts when a document is opened and stops again when nobody edits.

<img alt="Office Editor: its state and settings" src="assets/screenshots/apps/office.png" width="100%">

##### Antivirus

Scans your shares for viruses with ClamAV: by hand, on a schedule, and new files as they arrive. Infected files go into a quarantine, and the virus definitions update themselves.

<img alt="Antivirus: definitions, last scan, quarantine and scanner" src="assets/screenshots/apps/antivirus.png" width="100%">

##### Documents

A paperless archive: scans, PDFs and photos of letters become searchable PDFs, filed by correspondent, type and tags. Find any letter again by a word in it.

<img alt="Documents: the archive with its search and filters" src="assets/screenshots/apps/documents.png" width="100%">

##### Backup & Sync

**Backup** makes encrypted, versioned backups of your folders, computers and VMware and Hyper-V machines, to a disk, another Ignis or the cloud. **Ignis Recovery** brings a failed computer back whole. **Cloud Sync** keeps folders in step with Google Drive, OneDrive, Dropbox, S3 and more.

<p><img alt="Backup: tasks, destinations, VM hosts and computers" src="assets/screenshots/apps/backup.png" width="49%"> <img alt="Cloud Sync: tasks and connections" src="assets/screenshots/apps/cloudsync.png" width="49%"></p>

##### Calendar & Contacts

Your calendars, tasks and contacts for every phone and computer (CalDAV and CardDAV), and in the browser with month, week and list views and an address book.

<img alt="Calendar & Contacts: a month view" src="assets/screenshots/apps/calendar.png" width="100%">

##### Ignis Sync

Keeps folders the same on your phones and computers, peer to peer and end-to-end encrypted, with the Syncthing apps.

<img alt="Ignis Sync: folders, devices and this appliance" src="assets/screenshots/apps/sync.png" width="100%">

##### SAN Manager

Offers storage to other computers over iSCSI.

<img alt="SAN Manager: targets, LUNs and sessions" src="assets/screenshots/apps/san.png" width="100%">

##### Download Station

Downloads links, torrents and magnet links into a folder you choose.

<img alt="Download Station: a download queue with progress" src="assets/screenshots/apps/downloads.png" width="100%">

#### 🎬 Media

##### Photos

Your photos as a timeline and in albums, sorted by people, places and things. Edit and share them.

<img alt="Photos: a timeline of pictures grouped by day" src="assets/screenshots/apps/photos.png" width="100%">

##### Video Station

Your movies and TV shows with posters, played in the browser, and on TVs, consoles and Kodi.

<img alt="Video Station: Continue watching and Recently added" src="assets/screenshots/apps/video.png" width="100%">

##### Audio Station

Your music by album, artist, genre and folder, with playlists, lyrics and internet radio. Plays in the browser, in Subsonic apps and on receivers, speakers and TVs.

<img alt="Audio Station: the home view" src="assets/screenshots/apps/audio.png" width="100%">

##### Live TV

Watch TV in the browser from DVB, HDHomeRun and SAT>IP tuners or IPTV playlists, with a programme guide. Records from the guide or by series rules, and passes the channels on to Plex, Jellyfin, Kodi and TVs.

<img alt="Live TV: channels and the player" src="assets/screenshots/apps/tv.png" width="100%">

##### Surveillance

Records your IP cameras, with a live grid that fits your screen, motion events and playback. Recognises people, vehicles, faces and number plates, and alerts you.

<img alt="Surveillance: four cameras live in a grid" src="assets/screenshots/apps/surveillance.png" width="100%">

#### 🌐 Web & Mail

##### Web & Mail

**Web Station** hosts your websites and subdomains with PHP, databases, WordPress and phpMyAdmin, each with its own certificate, and a DNS server for your domains. **Mail Server** is email for your own domain with a spam filter, and **Webmail** reads it in the browser.

<img alt="Web Station: websites with their subdomains, PHP and certificates" src="assets/screenshots/apps/web.png" width="100%">
<p><img alt="Mail Server: today's mail, services and certificates" src="assets/screenshots/apps/mail.png" width="49%"> <img alt="Web Station's DNS server and zones" src="assets/screenshots/apps/dns.png" width="49%"></p>
<img alt="Webmail: addresses and mail servers" src="assets/screenshots/apps/webmail.png" width="100%">

#### 🔒 Network

##### VPN

Reach your home network from anywhere with WireGuard, OpenVPN, IPsec or Tailscale, or send machines and containers through a VPN.

<img alt="VPN: servers, tunnels and who is connected" src="assets/screenshots/apps/vpn.png" width="100%">

##### AdGuard Home

Blocks ads and trackers for your whole network as its DNS server, on the network cards you choose.

<img alt="AdGuard Home: protection and the last 24 hours" src="assets/screenshots/apps/adguard.png" width="100%">

##### Speedtest

Measures your internet connection with Ookla's servers and keeps a history.

<img alt="Speedtest: the latest result and the history" src="assets/screenshots/apps/speedtest.png" width="100%">

##### WiFi

Turns a WiFi card into an access point, or connects Ignis to a WiFi network. It has no page of its own: you set it up under **Network & Firewall**.

#### 🧩 Apps

##### Docker

Runs containers on the **Containers** page. With **App Station**: self-hosted apps such as Jellyfin, Immich, Nextcloud and Home Assistant in one click.

<img alt="Containers: the container list with a compose project" src="assets/screenshots/containers.png" width="100%">

##### Game Servers

Runs servers for Minecraft, Valheim, Factorio and about 145 more games, with a console, mods, backups and timetables. Requires Docker.

<p><img alt="Game Servers: five servers with players and usage" src="assets/screenshots/apps/games.png" width="49%"> <img alt="Game Servers: a Minecraft server's add-ons from Modrinth" src="assets/screenshots/apps/games-addons.png" width="49%"></p>

##### AI

Runs language models on your own GPU, beside online services such as OpenAI, Anthropic and Gemini, all in one chat.

<img alt="AI: engine, models and getting started" src="assets/screenshots/apps/ai.png" width="100%">

##### Web Browser

A browser on Ignis, inside the page, with tabs. Open your router and other devices at home from anywhere, and save downloads straight to a share.

<img alt="Web Browser: the browser page" src="assets/screenshots/apps/browser.png" width="100%">

##### Remote Desktop

Reach the PCs, servers and machines on your network in the browser over RDP, VNC and SSH, with saved connections and wake-on-LAN. Requires the Graphics Runtime.

<img alt="Remote Desktop: the connections" src="assets/screenshots/apps/remote.png" width="100%">

##### Windows Apps

Runs Windows programs in your browser without a Windows licence. Each set of programs has its own Windows, and sees only the folders and networks you allow.

<img alt="Windows Apps: a set with its programs" src="assets/screenshots/apps/winapps.png" width="100%">

##### Android Apps

Runs Android apps in your browser, as a whole Android screen or each app in its own window, with Google's apps or without. Requires the Graphics Runtime.

<img alt="Android Apps: the Android screen" src="assets/screenshots/apps/android.png" width="100%">

##### DSM machines

Sets up Synology DSM machines with the Arx loader and keeps the loader up to date.

<img alt="Arx DSM: machines and a new DSM machine" src="assets/screenshots/apps/dsm.png" width="100%">

#### ⚙️ Misc

##### Graphics Runtime

The screen the Web Browser, Windows Apps, Android Apps and Remote Desktop run on (**Display Runtime**), and GPU video conversion and 3D graphics for Linux machines (**Video Compute Runtime**). Installed by itself with the apps that need it.

<p><img alt="Display Runtime: graphics card, sessions and ports" src="assets/screenshots/apps/display.png" width="49%"> <img alt="Video Compute Runtime: the FFmpeg builds" src="assets/screenshots/apps/vcrt.png" width="49%"></p>

##### UPS

Watches the UPS your box runs on. When the power fails it shuts down your machines, containers and apps in the order you choose, then Ignis, and starts them again when the power is back.

<img alt="UPS: status, the last day and the UPS" src="assets/screenshots/apps/ups.png" width="100%">

##### LED Control

Drives the front panel LEDs of UGREEN NAS boxes from the activity and temperature of your disks.

<img alt="LED Control: mode, front panel and bays" src="assets/screenshots/apps/ledcontrol.png" width="100%">

##### NVIDIA

The NVIDIA driver, so containers can use the GPU. It has no page of its own.

##### Vision Runtime

The image recognition that Photos and Surveillance use. It has no page of its own.

> [!NOTE]
> Some of these apps are brand new. If one is not on the Extensions tab yet, it comes with one of the next releases. **Web & Mail** needs ports 80 and 443 for your websites, so it moves the Ignis interface to ports 8080 and 8443. It asks you to confirm the move first. Web Station's DNS server and AdGuard Home can run side by side, each on its own network card: for example the DNS server on the card that faces the internet and AdGuard Home on your home network's.

You can also make an app of your own. See [extensions](extensions/README.md).

---

## 🧭 How it works

```
USB stick → Installer → choose disks → Ignis on the machine's own disks
                                          └─ web interface at https://<address>
                                               ├─ virtual machines
                                               ├─ containers
                                               ├─ apps
                                               └─ host: storage, network, users, updates
```

Ignis keeps two things apart: **the system**, which each update replaces as a whole, and **your data**: machines, disk images, containers, apps and settings. Your data lives on a volume of its own, so an update never touches it, and a failed update can be undone.

---

## 🖱️ The web interface

| Page | What you do there |
| :-- | :-- |
| **Overview** | The whole box at a glance: its hardware, what runs, the latest messages and every app, with Getting started for a new box |
| **Virtual Machines** | Create, start, stop and edit machines, open their display, take snapshots, clone, import and export |
| **LXC** | Linux containers from ready images: start, stop, console, snapshots, backups and clones |
| **Containers** | Run containers and compose projects, see their logs and usage, update and clean up |
| **Virtual Networks** | The networks your machines and containers use: private networks, bridges that put them straight on your network, or a VLAN from your switch for them |
| **Storage** | Disk images, ISOs, uploads, extra volumes and the drives in your box, shown like a file manager. You choose how large an upload may be (4 GB unless you change it) |
| **Schedules** | Timed start, shutdown, snapshot, backup, container and data check tasks, and the tasks your apps offer: website and mail backups, WordPress updates, downloads only at night, cameras on and off, and more |
| **Passthrough** | Graphics cards, PCI and USB devices your machines can use |
| **Monitor** | The host right now, its **History** over time, **Storage Health**, and the **Storage Analyzer**: what uses the space |
| **Users** | Accounts, roles and their permissions, and who sees which machines and pages |
| **Network & Firewall** | Ignis's own network cards and addresses, VLANs and bonded network cards, the router with its local networks, DHCP and connected devices, and the firewall: access, zones, protection, outgoing traffic, port forwards and what was blocked |
| **System** | The host's name, time, CPU (governor, turbo and clock limits) and fans, linked hosts, the smart home interface, email, services, updates, a terminal, and **shortlinks**: addresses of your own such as `http://<ip>/download` that open a page straight away |
| **Extensions** | Install, update, turn on, restart and remove apps, see which apps need each other and what each package includes |
| **Info** | What this host supports, and a report to copy into a bug report |

Every page has a **?** button with help for that page, and a page with settings has a gear button right beside it.

Pick the look you like from the account menu: a light or dark mode, an accent colour, a wallpaper (northern lights, mountains, waves, dunes and more, or a picture of your own) and either the classic layout with a sidebar or a **desktop** where every page opens in a window of its own, with a taskbar. Both layouts share one top bar, and the layout looks the same whether you choose solid or glass boxes. Each group in the sidebar has its own colour, pages show their key numbers at the top, and whatever runs has a coloured edge for its state, with live CPU and memory rings for machines and containers. Your language and a 12- or 24-hour clock are saved with your account. The account menu is also where you restart or shut down Ignis, if your account may. Settings are switches, and a short note at the bottom of the screen confirms what you saved. The address bar shows just Ignis's address, whatever page you are on.

### 📸 A look inside

<table>
  <tr>
    <td width="50%"><img alt="Monitor: live CPU, memory, load and every core" src="assets/screenshots/monitor.png"><br><sub><b>Monitor</b>: the host right now, down to every core</sub></td>
    <td width="50%"><img alt="History: the last day of CPU, memory, temperatures, fans and network" src="assets/screenshots/history.png"><br><sub><b>History</b>: the last hour, day, week or month</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="The machine editor on its General tab" src="assets/screenshots/vm-editor.png"><br><sub><b>Machine editor</b>: CPU, memory, firmware and TPM on one tab</sub></td>
    <td width="50%"><img alt="Containers: the container list with an immich compose project" src="assets/screenshots/containers.png"><br><sub><b>Containers</b>: containers with their logs, details and updates, beside the machines</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="Extensions: apps to download and the ones installed" src="assets/screenshots/extensions.png"><br><sub><b>Extensions</b>: install the apps you want, each updated on its own</sub></td>
    <td width="50%"><img alt="Network &amp; Firewall on its Access tab: the ports always open and the ones opened for apps" src="assets/screenshots/network-firewall.png"><br><sub><b>Network &amp; Firewall</b>: addresses, router, DHCP and the firewall in one place; your apps grouped in the sidebar</sub></td>
  </tr>
  <tr>
    <td colspan="2"><img alt="The desktop layout: Virtual Machines, Monitor and Containers in windows of their own" src="assets/screenshots/desktop.png"><br><sub><b>Desktop</b>: every page in a window of its own, with a taskbar and your wallpaper</sub></td>
  </tr>
</table>

---

## 📋 What you need

* An x86-64 PC or server, with virtualisation (Intel VT-x or AMD-V) turned on in the BIOS
* For passthrough: Intel VT-d or AMD-Vi, also turned on in the BIOS
* A USB stick for the installer
* At least one disk for Ignis. 64 GB or more is a good start, plus room for your machines
* Two or more disks if you want RAID
* A wired network

Once Ignis is running, the **Info** page shows what your host supports, and what is missing.

---

## 💿 Installing

1. Download the latest ISO from the [releases](https://github.com/AuxXxilium/ignis-hv/releases/latest) and write it to a USB stick
2. Start the machine from the stick and choose **Install**
3. Pick the disks to install to. **Everything on them is erased**
4. Choose where the system goes (one disk or a mirror) and how the disks for your data work together. Only the options your disks allow are offered
5. Set a root password
6. Remove the stick and restart. The screen shows the address to open in your browser. Sign in as `root`

With several disks, every disk can start Ignis, so the machine still boots if one of them fails.

---

## ⬆️ Updates

Ignis checks for new releases by itself and tells you through the bell at the top. You install them under **System → Update**: **Download and stage** fetches the new version and checks it, and your machines keep running meanwhile. **Apply** asks once more and restarts into the new version; the page waits for Ignis to come back and then reloads by itself.

Apps are updated on their own, on the **Extensions** tab.

Your settings, passwords and certificates are kept. Machines, disk images, containers, networks, users and app data are never touched by an update.

The previous version is kept. If something is wrong after an update, choose it from the boot menu to go back.

---

## 🔒 Security

* Every action checks who is signed in and what they may do
* Repeated wrong passwords at the login page or over SSH get the address blocked for a while
* Two-factor sign-in and the screen lock protect your account, even on a shared computer
* A machine's display can only be opened through the signed-in web interface
* Apps and containers have a lot of access to the host, so install only what you trust. Only admins can manage them

---

## 📥 Downloads

Besides Ignis itself, on the [tools](tools/README.md) page:

* **The Ignis app** for Windows, macOS and Linux: Drive, your cameras, and backups of your computer (on Windows with the whole-system backup for Ignis Recovery)
* **Ignis Recovery**, to bring a computer back from its backup: a CD image or a USB stick image. Ignis also offers it over the network, and on the Backup & Sync page

These are on a release of their own, so Ignis never takes them for an update.

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

[![Stars](https://img.shields.io/github/stars/AuxXxilium/ignis-hv?style=for-the-badge&logo=github)](https://github.com/AuxXxilium/ignis-hv)
[![Discord](https://img.shields.io/discord/639072565155069962?style=for-the-badge&logo=discord&label=Discord)](https://discord.auxxxilium.tech)

</div>
