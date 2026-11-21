# Release notes

What each Ignis release brings, the newest first.

## 26.11.21

*2026-11-21*

### 🚑 Starting your computer
- **Ignis starts again on newer UEFI computers.** On computers whose firmware protects its memory (common on recent mainboards), an installed Ignis stopped right after the boot menu and the computer went back to its firmware setup. The boot loader is fixed, and an update now brings the fixed boot loader to your disks too, so an installed Ignis keeps starting.
- **If your Ignis does not start at all:** start the computer from the new installation USB stick and choose to update the existing installation. Your machines, data and settings stay; the boot loader on your disks is written new.
- **Boot menu entry:** Ignis now also adds itself to your computer's firmware boot menu as **Ignis HV**, so computers that only look there find it.
- **Smaller computers can install Ignis:** the installation USB stick and the live mode now start with 2 GB of memory; before, they needed about 6 GB.

### 🌐 Network & WiFi
- **WiFi:** a new **WiFi** app brings the drivers for WiFi cards from Intel, MediaTek, Realtek, Qualcomm Atheros and Broadcom, so only appliances with a WiFi card download them. With it, Network & Firewall › Adapters lets a WiFi card join a WiFi (even as the internet connection) or serve one of its own, with WPA2/WPA3, 2.4 or 5 GHz and an automatic channel. Ticked as a local network under Router, your WiFi gets its own addresses and rules, like a guest WiFi.
- **WiFi timer:** choose for each weekday when your WiFi is on, turn it off now until the next on-time, or keep it always on.
- **Dual band and more:** tick 2.4, 5 and 6 GHz for your WiFi -- each band needs a radio of its own, such as two WiFi cards or a card that is two radios. Keep one name and password on all bands, so devices move between them, or give every band its own WiFi and network, like a guest WiFi on 2.4 GHz beside a private one on 5 GHz. Wider channels and WiFi 6 and 7 are used where your card supports them.
- **WiFi tab:** WiFi now has a tab of its own in Network & Firewall, with a page per WiFi. Tick every band a WiFi should be on and Ignis picks the cards, or choose the card for a band yourself; **New WiFi** adds a second one, like a guest WiFi with its own name, password and network, which can share a card with your main WiFi where the card supports it. Every WiFi has its own timer, or uses another WiFi's; **Off until** pauses it to the next on-time. A card can also join a WiFi, for example as the internet connection.
- **Network overview:** the first tab of Network & Firewall is a map of your network: the internet, Ignis and each of your networks with its devices, which network may use the internet and which may reach another. Click a network, the internet or a device to see its details below the map -- every device with its name, address and whether it is online. Right-click it (or press and hold it, or use **⋯**) to switch its internet, AdGuard filter or reach, change its DHCP range, keep a device off the internet, give it a fixed address or wake it. Without router mode, devices show the names your own router gives them.
- **Always allow an address:** right-click an address on the Blocked tab to never block it again, by blocklists, port-scan detection or failed sign-ins.
- **Router devices:** give a device a name of your own and an address of your choice; it gets it the next time it connects, and answers to its name on your network.
- **Network boot:** Network & Firewall › Network boot lets computers on the networks you pick start from Ignis over the network: Ignis Recovery, ISOs from your storage, or netboot.xyz. Choose the default entry and how long the menu waits. It is off until you switch it on, its ports open only while it is on, and only accounts with the new **Network boot** permission can change it.

### 💾 Backups
- **Computer backups keep running when Ignis gets a new address.** Backup & Sync now has a certificate of its own that your computers trust, so a new network address on Ignis (Docker's, a new network card) no longer stops their backups. Computers set up before are marked on the page: the Ignis app takes the new certificate by itself; if you set up restic by hand, download the certificate once and replace the old file.
- **System backups:** Backup & Sync keeps a copy of a computer's whole disk, every partition with its layout. Open a partition of any system backup right on the page and restore single files from it into a share. Linux computers make system backups with a small script; Windows computers with the Ignis app (below).
- **Whole Windows computer:** the Ignis app for Windows backs up the whole system disk, block by block, while you keep working: Windows, programs, settings and files, with free space costing nothing. Back up now or every week or day, also when nobody is signed in. Windows asks once for administrator rights. Ignis Recovery puts it back onto an empty disk.
- **Ignis Recovery:** a small boot system to put a whole computer back from a system backup. Download it on the Backup & Sync page as an ISO or an image for a USB stick, or start it over the network. It finds your Ignis, signs you in, and lets you pick the computer, the date and the disk to write to, in English, German, French, Spanish or Russian. Over the network it starts on computers in BIOS (legacy) mode for now; for the others, use the USB stick.

### 🎨 Easier to use
- **Getting started:** a short checklist on the Virtual Machines page for new installations (your own admin account, email, two-factor sign-in, apps, backups). Every step opens the right page and ticks itself.
- **Email & notifications** are one page now, with one click for Gmail, Outlook, iCloud, GMX, web.de, Yahoo or this appliance's own Mail Server.
- **Schedules:** ready-made tasks such as nightly snapshots, start and shut-down times, weekly backups and a monthly data check.
- **Storage:** the Disk images and ISOs tiles show what they hold.
- **Virtual Networks** is the new name of the page for your machines' networks, so it is not confused with Network & Firewall.
- **Extensions** are grouped like the sidebar and can be searched.
- Hints that name a place in Ignis are links that take you there.
- **Right-click menus in the apps:** right-click a row, a tile or a box (or press and hold it on a touch screen) in AdGuard, VPN, Surveillance, Download Station, Game Servers, Photos, Video Station, Audio Station, Web & Mail, Network Shares and Backup & Sync for its actions, such as blocking a domain right from the query log, or pausing a backup task.
- **New actions in the apps:** record a camera right now (for a while or until you stop it), open a download's folder in Drive, back up a website with one click, delete photos into Drive's recycle bin, play a film on your TV or receiver with **Play on**, and switch a WireGuard device off and on without deleting it.

### 🛠️ Smaller fixes
- **SSD trim:** Ignis now tells your SSDs once a week which space is free, so they stay fast and wear evenly (Monitor › Storage Health, with Trim now). Virtual machines already free the space of files you delete inside them.
- **Manage in Drive:** the links from Photos, Video Station and Audio Station open Drive at that link again, instead of wherever Drive was last.

## 26.11.20

*2026-11-20*

Everything that changed since the first release (26.11.16).

### 🌐 Network & Firewall: Ignis can be your router
- **New page "Network & Firewall"** in the sidebar. Your network cards, the firewall and the new router are all in one place; the network settings left the System page.
- **Router:** connect one network card to the internet and use the others for your own networks. For each network you decide whether it may go online, whether it may reach your other networks, and whether Ignis hands out addresses there (DHCP, off unless you switch it on).
- **Device list:** see every device on your networks, give it a name and a fixed address.
- If you had the Firewall or DHCP Server app installed, your settings move over by themselves.

### 🧩 Apps
- **Tidier sidebar:** your apps sit right under your machines, grouped into Files, Media, Web & Mail, Network, Apps and Misc. Each group can be folded away.
- **Fewer, bigger packages:** **Shares & Drive** (Network Shares and Drive in one; share links keep working), **Backup & Sync** (Backup and Cloud Sync in one), **Web & Mail** (Web Station, Mail Server and Webmail), **Docker** with App Station, and the **Graphics Runtime** with video conversion on your GPU.
- **New apps:**
  - **App Station:** Jellyfin, Immich, Nextcloud, Home Assistant and more in one click.
  - **Calendar & Contacts:** works with your phone, Thunderbird and your Google account.
  - **Cloud Sync:** keep folders in step with Google Drive, OneDrive, Dropbox and more.
  - **Ignis Sync:** folders kept the same on your phones and computers.
  - **Backup:** now also backs up your VMware and Hyper-V machines.
  - **Speedtest**, and **LED Control** for UGREEN NAS cases.
- **App screens are smoother:** Web Browser, Windows Apps and Android Apps now stream with sound, adapt to your connection, and use your graphics card when one is free.
- **AdGuard Home 1.0:** a fresh look, faster and lighter. New installs use Cloudflare as their DNS server; yours keeps its settings.
- **Video Station:** pick H.264, H.265 or AV1 for converted videos, with HDR shown correctly.
- **Many fixes:** Mail Server sends and receives reliably, new game servers start, SAN logins with CHAP work, SMB is reachable from your network, and Android Apps also starts on processors that used to stop it.

### 🔔 Notifications
- Get notifications by **email** or **webhook** (for example Discord or Home Assistant), and choose for each kind of message where it goes.
- The notification bell is now for admins only.

### 🖥️ Machines & consoles
- **Machine consoles** stream over WebRTC when the Graphics Runtime is installed: smoother and with sound.
- **Console:** a keyboard-layout picker and clearer power buttons.
- **Folders:** each machine gets its own folder for its disks, like on ESXi.
- **DSM machines (Arx):** every model Arx supports, with its loader options.

### 🎨 Interface
- A cleaner look throughout: on/off switches, buttons on the right, short "Saved" messages at the bottom, and explanations moved behind the **?** on each page.
- **Monitor:** a new **Benchmark** tab, and an auto-refresh switch.
- **Storage and Drive:** a photo viewer and a music player.
- **Your account:** pick 12- or 24-hour time, new wallpapers, and **restart and shut down** from the account menu.
- **Shortlinks:** your own short addresses such as `http://<ip>/download` that open a page directly.
- **Uploads:** choose the upload limit (4 GB by default). Files that are too large are refused right away, with the reason.
- **Updates:** downloads show a progress bar, and so do uploaded files, with the percentage.

### 🔒 Security
- SSH is off on new installations until you switch it on.
- The web interface now uses ports **8080/8443** on new installations, so 80/443 stay free for your websites.
- Up-to-date security fixes for the system, PHP, mail and webmail.

### 🛠️ Smaller fixes
- Error pages now look like the rest of Ignis and use your language.
- Machines on a bridged network keep working when Docker is running.
- No more log spam on machines without a serial port.
- The Vision Runtime uses the system's Python now, like every other app, and is smaller.
- Arx DSM and App Station clean up their old downloads and leftover folders again.
- Old task files of the scheduler and old sign-in tokens of linked hosts are cleaned up again.
