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
* **Monitor and History**: what the host and every machine are doing right now, and over the last hour, day, week or month. Live readings refresh every few seconds, and you can switch that off
* **Several hosts as one**: link your Ignis hosts and run their machines from one interface. A machine can have a standby copy on a second host, ready if the first one fails
* **For your smart home**: a read-only interface for Home Assistant, Prometheus and similar apps

### 🌐 Network

* **Networks for your machines**: private networks, or bridges that put machines straight on your network. VLANs and bonded network cards are supported, also per machine
* **Network & Firewall**: Ignis's own addresses, a firewall that decides who reaches which service, blocklists, countries and port scans, port forwards, and a **router**: one network card to the internet, the others as local networks. Each local network can reach the internet or stay local only, may or may not reach the other local networks, and gets its own DHCP range if you switch it on. A device list shows who is connected, with names of your own and fixed addresses
* **HTTPS**: with your own certificate or a free one from Let's Encrypt

### 🔐 Sign-in and security

* **Users and roles**: admin, operator and viewer accounts, each limited to the machines and pages you choose. Every permission says what it allows, and which of your apps it opens
* **Two-factor sign-in**: with an authenticator app, recovery codes for emergencies and codes by email. A browser you trust can skip the code for 30 days
* **Screen lock**: Ignis locks itself after the time you choose, and you unlock it with your password

### 🧩 Apps

Add apps from the **Extensions** tab. Install only the ones you need; each one is updated on its own, apart from Ignis. In the sidebar your apps sit right under the machines, grouped into **Files**, **Media**, **Web & Mail**, **Network**, **Apps** and **Misc**, and each group can be folded away. When an app requires another one, the tab tells you and installs it with a click, and apps you have switched on start by themselves when Ignis starts.

Apps that belong together come as one package: **Web & Mail**, **Drive & Shares**, **Backup & Sync**, the **Graphics Runtime**, and **Docker** with App Station. One switch turns the whole package on or off, updates and removes it, and its page has a tab for each part. If you had one of the parts installed on its own before, it moves into its package with everything it holds.

| App | What it does |
| :-- | :-- |
| **Docker** | Runs containers on the Containers page. With **App Station**: popular self-hosted apps such as Jellyfin, Immich, Nextcloud and Home Assistant in one click |
| **Drive & Shares** | **Drive** shows your shared folders in the browser: upload, preview and share files with a link, also with people who have no account. The preview opens Word, Excel and PowerPoint files (the old .doc, .xls and .ppt too), OpenDocument, PDF, e-books, Markdown and code, and lists what is inside archives. **Network Shares** shares the folders over SMB like a NAS, and over SFTP and FTPS if you want |
| **Antivirus** | Scans your shares for viruses and other malware with ClamAV: by hand, on a schedule, and new files as they arrive. Infected files go into a quarantine you can restore from or empty, and the virus definitions update themselves every day |
| **Backup & Sync** | **Backup** makes encrypted, versioned backups of your folders, your computers and your VMware and Hyper-V machines, to a disk, another Ignis or the cloud, on a schedule. **Cloud Sync** keeps folders in step with Google Drive, OneDrive, Dropbox, S3 and many more |
| **Ignis Sync** | Keeps folders the same on your phones and computers, peer to peer and end-to-end encrypted, with the Syncthing apps |
| **Photos** | Your photos as a timeline and in albums, sorted by people, places and things. Edit and share them |
| **Video Station** | Your movies and TV shows with posters, played in the browser. Also plays on TVs, consoles and Kodi |
| **Audio Station** | Your music by album, artist, genre and folder, with playlists, favourites, lyrics and internet radio. Plays in the browser, in music apps that speak Subsonic, and on receivers, speakers and TVs |
| **Surveillance** | Records your IP cameras (RTSP, or HTTP: MJPEG, snapshots and HLS), live view in a grid that fits your screen, motion events and playback. Can recognise people, vehicles, faces and number plates, and alert you. Each camera can also be passed on to Home Assistant, VLC or another recorder, at an address of its own that you can renew at any time |
| **Download Station** | Downloads links, torrents and magnet links into a folder you choose |
| **Web & Mail** | **Web Station** hosts your own websites and their subdomains with the newest PHP or one of the two before it, and databases, including WordPress and phpMyAdmin in one click, each with its own certificate, and a DNS server for your own domains that fills in its records by itself. **Mail Server** is email for your own domain, with a spam filter and help with the DNS settings, and **Webmail** reads it in the browser |
| **VPN** | Reach your home network from anywhere with WireGuard, OpenVPN, IPsec or Tailscale, or send machines and containers through a VPN |
| **SAN Manager** | Offers storage to other computers over iSCSI |
| **Game Servers** | Runs servers for Minecraft, Valheim, Factorio and about 145 more games, with a console, backups and timetables. Requires Docker |
| **AI** | Runs language models on your own GPU, beside online services such as OpenAI, Anthropic and Gemini, all in one chat |
| **Web Browser** | A browser that runs on Ignis and shows inside the page, with tabs and a toolbar like the browser you know. Open your router, cameras and other devices on your home network from anywhere, look something up while you work, and save downloads straight to a shared folder. You choose whether it may reach the internet, your home network or both |
| **Windows Apps** | Runs Windows programs on Ignis and shows them in your browser, without a Windows licence. Each set of programs gets its own Windows with its own drive C:, and sees only the shared folders you allow, plus a folder of your own that all your programs share. Per set, you choose whether it may reach the internet and your home network. Drop an installer or a file on the screen to install or upload it |
| **Android Apps** | Runs Android apps on Ignis and shows them in your browser, each in a window of its own or as a whole Android screen. You choose Android with Google's apps or without. Requires the Graphics Runtime |
| **Graphics Runtime** | The screen that Web Browser, Windows Apps and Android Apps run on (Display Runtime), using your graphics card when one is free, and video conversion on your GPU for the media apps with 3D graphics for Linux machines without passing a card through (Video Compute Runtime). Installed by itself with the apps that need it |
| **DSM machines** | Sets up Synology DSM machines with the Arx loader and keeps the loader up to date |
| **AdGuard Home** | Blocks ads and trackers for your whole network as its DNS server, on the network cards you choose |
| **NVIDIA** | The NVIDIA driver, so containers can use the GPU |
| **Vision Runtime** | The image recognition that Photos and Surveillance use |

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
| **Virtual Machines** | Create, start, stop and edit machines, open their display, take snapshots, clone, import and export |
| **LXC** | Linux containers from ready images: start, stop, console, snapshots, backups and clones |
| **Containers** | Run containers and compose projects, see their logs and usage, update and clean up |
| **Network** | Networks for your machines, VLANs and bonds |
| **Storage** | Disk images, ISOs, uploads, extra volumes and the drives in your box, shown like a file manager. You choose how large an upload may be (4 GB unless you change it) |
| **Schedules** | Timed start, shutdown, snapshot, backup, container and data check tasks, and the tasks your apps offer: website and mail backups, WordPress updates, downloads only at night, cameras on and off, and more |
| **Passthrough** | Graphics cards, PCI and USB devices your machines can use |
| **Monitor** | The host right now, its **History** over time, and **Storage Health** |
| **Users** | Accounts, roles and their permissions, and who sees which machines and pages |
| **Network & Firewall** | Ignis's own network cards and addresses, the router with its local networks, DHCP and connected devices, and the firewall: access, zones, protection, outgoing traffic, port forwards and what was blocked |
| **System** | The host's name, time, CPU (governor, turbo and clock limits) and fans, linked hosts, the smart home interface, email, services, updates, a terminal, and **shortlinks**: addresses of your own such as `http://<ip>/download` that open a page straight away |
| **Extensions** | Install, update, turn on, restart and remove apps, see which apps need each other and what each package includes |
| **Info** | What this host supports, and a report to copy into a bug report |

Every page has a **?** button with help for that page.

Pick the look you like from the account menu: a light or dark mode, an accent colour, a wallpaper (northern lights, mountains, waves, dunes and more, or a picture of your own) and either the classic layout with a sidebar or a **desktop** where every page opens in a window of its own, with a taskbar. Both layouts share one top bar, and the layout looks the same whether you choose solid or glass boxes. Your language and a 12- or 24-hour clock are saved with your account. The account menu is also where you restart or shut down Ignis, if your account may. Settings are switches, and a short note at the bottom of the screen confirms what you saved. The address bar shows just Ignis's address, whatever page you are on.

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

### 🧩 Apps in action

<table>
  <tr>
    <td width="50%"><img alt="Photos: a timeline of pictures grouped by day" src="assets/screenshots/apps/photos.png"><br><sub><b>Photos</b>: your pictures as a timeline, by people, places and things</sub></td>
    <td width="50%"><img alt="Video Station: posters under Continue watching and Recently added" src="assets/screenshots/apps/video.png"><br><sub><b>Video Station</b>: your films and shows with posters, in the browser and on your TV</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="Surveillance: four cameras live in a grid" src="assets/screenshots/apps/surveillance.png"><br><sub><b>Surveillance</b>: live view that fits your screen, recordings, alerts, and streams for other apps</sub></td>
    <td width="50%"><img alt="Drive: a folder of pictures as thumbnails" src="assets/screenshots/apps/drive.png"><br><sub><b>Drive</b>: your shared folders in the browser, with previews of documents, sheets and slides, and share links</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="Web &amp; Mail on its Web Station tab: example.com with its docs and shop subdomains, each with its PHP version, certificate and buttons" src="assets/screenshots/apps/web.png"><br><sub><b>Web &amp; Mail</b>: Web Station's websites, each in a box with its controls, subdomains nested inside, its PHP version and HTTPS per site; Mail Server is a tab away</sub></td>
    <td width="50%"><img alt="Game Servers: five servers with players and usage" src="assets/screenshots/apps/games.png"><br><sub><b>Game Servers</b>: Minecraft, Valheim and about 150 more, with console and backups</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="Download Station: a download queue with progress" src="assets/screenshots/apps/downloads.png"><br><sub><b>Download Station</b>: links and torrents straight onto your storage</sub></td>
    <td width="50%"><img alt="VPN: WireGuard devices with their QR codes" src="assets/screenshots/apps/vpn.png"><br><sub><b>VPN</b>: WireGuard, OpenVPN, IPsec and Tailscale, with a QR code per device</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="Mail Server: the DNS records to set for a domain" src="assets/screenshots/apps/mail.png"><br><sub><b>Mail Server</b>: email for your own domain, with a DNS check</sub></td>
    <td width="50%"><img alt="Web Station's DNS tab: the DNS server on the internet-facing adapter, and zones with records from Web Station and Mail Server" src="assets/screenshots/apps/dns.png"><br><sub><b>DNS server</b>: your domains' records, filled in by your websites and mail</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="Drive: three share links in boxes, with their limits and buttons" src="assets/screenshots/apps/drive-links.png"><br><sub><b>Drive</b>: share links for files and folders, with passwords, expiry, download limits and upload requests</sub></td>
    <td width="50%"><img alt="Game Servers: a Minecraft server's Add-ons tab with its installed Modrinth plugins" src="assets/screenshots/apps/games-addons.png"><br><sub><b>Game Servers</b>: add mods and plugins from Modrinth, with a console, config files and backups per server</sub></td>
  </tr>
  <tr>
    <td width="50%"><img alt="Web Browser settings: start page, downloads folder, the switches for the internet and the home network, and the screen" src="assets/screenshots/apps/browser.png"><br><sub><b>Web Browser</b>: a browser on Ignis, inside the page, with tabs; you choose what it may reach and where downloads go</sub></td>
    <td width="50%"><img alt="Windows Apps: two bottles, each with its drives and buttons, one without internet" src="assets/screenshots/apps/winapps.png"><br><sub><b>Windows Apps</b>: Windows programs in your browser, each set in a bottle that sees only the folders and networks you allow</sub></td>
  </tr>
</table>

<sub>Screenshots of the real interface with sample data.</sub>

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
