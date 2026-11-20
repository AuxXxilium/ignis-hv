# Release notes

What each Ignis release brings, the newest first.

## Next

### 🌐 Network & WiFi
- **WiFi:** a new **WiFi** app brings the drivers for WiFi cards from Intel, MediaTek, Realtek, Qualcomm Atheros and Broadcom, so only appliances with a WiFi card download them. With it, Network & Firewall › Adapters lets a WiFi card join a WiFi (even as the internet connection) or serve one of its own, with WPA2/WPA3, 2.4 or 5 GHz and an automatic channel. Ticked as a local network under Router, your WiFi gets its own addresses and rules, like a guest WiFi.
- **WiFi timer:** choose for each weekday when your WiFi is on, turn it off now until the next on-time, or keep it always on.
- **Router devices:** give a device a name of your own and an address of your choice; it gets it the next time it connects, and answers to its name on your network.

### 🎨 Easier to use
- **Getting started:** a short checklist on the Virtual Machines page for new installations (your own admin account, email, two-factor sign-in, apps, backups). Every step opens the right page and ticks itself.
- **Email & notifications** are one page now, with one click for Gmail, Outlook, iCloud, GMX, web.de, Yahoo or this appliance's own Mail Server.
- **Schedules:** ready-made tasks such as nightly snapshots, start and shut-down times, weekly backups and a monthly data check.
- **Storage:** the Disk images and ISOs tiles show what they hold.
- **Virtual Networks** is the new name of the page for your machines' networks, so it is not confused with Network & Firewall.
- **Extensions** are grouped like the sidebar and can be searched.
- Hints that name a place in Ignis are links that take you there.

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
