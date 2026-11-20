# Release notes

What each Ignis release brings, the newest first.

## Next

### 🛠️ Smaller fixes
- Old task files of the scheduler and old sign-in tokens of linked hosts are cleaned up again.

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
