# Release notes

What each Ignis release brings, the newest first.

## 26.11.23

*2026-11-23*

### 💬 Chat & Calls (new app)
- **Messages, pictures and files between the people who have an account on your Ignis**, in a conversation of two or in a group. Unread counts, who is writing, files up to 100 MB by the paper clip, by dragging them in or by pasting a picture.
- **Voice and video calls** in any conversation, with screen sharing. Everyone else in it sees a **Join** card while they have Chat open, and the conversation shows that a call is going on until the last one leaves.
- **No sign-up, nothing outside your Ignis.** Every Ignis user already has their chat account and is signed in with their Ignis sign-in. Nobody without an Ignis account can join, and your Ignis talks to no other chat server. Messages and files stay on the data volume.
- **In the Ignis app too:** a **Chat** tab with the same conversations and calls, on phones and computers.
- Calls go straight between the devices and your Ignis: on your network, over the VPN or wherever its ports TCP 7881 and UDP 7882 can be reached. The Firewall opens them while Chat runs.
- **End-to-end encrypted:** messages, pictures, files and calls are encrypted on your device; the appliance stores and forwards only what it cannot read, so a stolen disk, backups, other users and admins see nothing.
- **Each browser and device you trust keeps the key.** Once a browser, phone or the Ignis app reads your messages, signing in to Ignis there shows them straight away. A new one is trusted by approving it from a device that already reads them, or with your recovery key; the appliance itself never holds the key.
- **Add a device by its code:** a new device can also show a QR code with 16 numbers; scan or type it under **Add a device** on one you already use. And your **recovery key**, made the first time you open Chat, unlocks them anywhere if all else fails (after an admin reset your password, say).
- Times and dates in Chat follow the 12- or 24-hour clock of your profile, in the web page and the app.
- **The bell tells you** about a new message when Chat isn't open (one line per conversation, at most every two minutes; nothing for what you already read) and about a call at once. Only you see your own lines.
- **Element, FluffyChat and other Matrix apps** can show your conversations too: open Chat's settings (the gear) and make a password for them, and enter your recovery key there as their Security Key (they do not unlock by the Ignis sign-in). It is shown once, and a new one signs those apps out; your Ignis password is never used. Phone apps need a trusted certificate (System › Host). Calls stay in Ignis and the Ignis app.
- When an Ignis user is deleted, their chat account is closed a few minutes later.

### 🔑 App passwords
- **Sign-in for other apps**, in your profile: network shares (SMB), FTP/FTPS/SFTP, Calendar & Contacts, Chat apps like Element, and music apps (Subsonic) take your Ignis password as before, and **app passwords** alongside it.
- Make an app password for a device you don't fully trust, give it a name, and switch on only the services it may open. Let Ignis generate a secure one, or type your own (12 characters at least). It is shown once; **New password** replaces it and **Revoke** cuts that device off, without changing your Ignis password.
- Switch **Allow my Ignis password** off and these apps take only app passwords.
- Network shares hold one password per user: while an app password opens them, they take it instead of your Ignis password, and get it back when that app password is revoked.
- These apps cannot ask for a second factor; the profile says so when you have 2FA on.

### 📺 Video Station and Audio Station: who may use the media server
- **Devices seen** lists every TV, receiver and player that has asked the DLNA server, with its address, its hardware address and what it says it is.
- **Block** shuts a device out at once: it can neither browse nor play (the Firewall drops it too). **Allow** and **Forget** undo it.
- Switch on **Only devices I allow** and every device you have not allowed is refused, new ones included.
- In Video Station under **TV and players**, in Audio Station in its settings. Each server has its own list.

### 🎬 Video Station in player apps (Jellyfin, Infuse)
- **Watch your Video Station library in the Jellyfin apps** (Android, Android TV, iPhone and Apple TV with Swiftfin, Findroid, the web player) **and in Infuse.** Add a server with the address `https://<your Ignis>:8443/ext/ignis-video/jf.cgi` and sign in with your Ignis user name and password, or with an app password made in your profile for **Video apps (Jellyfin, Infuse)**.
- Movies, TV shows with seasons and episodes, home videos, search, continue watching and watched are all there; what you watch in an app counts in Video Station too. The apps play the files as they are.
- Revoking that app password signs the apps out. No Jellyfin software runs on your Ignis: Video Station answers the apps itself.

### 📂 Drive & Shares: one page
- **Drive and Network Shares are one page now.** Make a share with **New share** under the shares on the left, and change one with the pencil next to it. A share Drive cannot open (not offered on the network, say) is shown dimmed, still with its pencil.
- **Each share's editor shows both access lists side by side:** who may use it **on the network (SMB, FTP and SFTP)** and who may open it **in Drive**. They stay two lists, as before.
- **Behind the gear:** how to connect (with the addresses to copy), FTP and SFTP, showing the appliance in the network, who signs in to the shares, the storage, and Drive's links and recycle bin.

### 📂 Drive: your FTP, FTPS and SFTP servers
- **Open other servers in Drive:** under **Remote servers**, **Add a server** with its address, user name and password (or a private key for SFTP), and browse it next to your shares. FTPS works with explicit and implicit TLS; for a server with its own certificate there is **Accept any certificate**.
- Open, download and upload files, make folders, rename and delete on the server, and **move or copy** between a server and your shares.
- **Test** checks the connection before you save it. Each user sees only their own servers; the password is kept on the appliance, never in the page.

### 🗄️ Backup & Sync: one page
- **Cloud Sync has no page of its own any more:** its sync tasks are under **Tasks**, below the backup tasks, and its connections under **Destinations** as **Cloud connections**.
- rclone is now part of the system, shared by Cloud Sync and Drive, and updated with each system update.

### 🌍 Dynamic DNS
- **A host name that always points at your Ignis**, even when your internet provider changes its address: **System › Host › Dynamic DNS**.
- **ArcDNS.tech**, free for Ignis and Arc, and presets for DuckDNS, No-IP, Dynu, deSEC, dynv6, FreeDNS, IPv64, Cloudflare, Namecheap, Strato and Hurricane Electric, or any service that speaks dyndns2.
- Ignis checks the address every five minutes and tells the provider when it changed; **Update now** does it at once and shows the answer.

### 📺 Live TV: free channels by country
- **Pluto TV** and **iptv-org** as sources: under **Add a source › IPTV**, pick **Channels from** and your country.
- Pluto TV brings free channels with ads and a programme guide (14 countries); iptv-org collects channels that are freely available (about 250 countries), without a guide.
- Some channels only play in their own country. Like all Live TV channels, they also reach Kodi, Plex, Jellyfin and your TVs.

### 🪟 Tidier pages
- **Forms open as dialogs** instead of panels under the lists: in Backup & Sync (tasks, destinations, restore, VM hosts, system backups and more) and in Ignis Sync (folders, devices, Leave out). No half-empty wide page any more.
- **Settings behind the gear:** Ignis Sync's appliance ID and settings, and Calendar & Contacts' calendars and address books, devices and Google account. Their tab bars keep what you use every day.
- **The clock in the classic layout**, in the same place and with the same calendar as on the desktop: a click shows the month with your Calendar & Contacts events, adds one with **+**, and opens Calendar & Contacts or the date and time settings.

### 💽 Storage
- **Storage Health** and the **Storage Analyzer** moved from Monitor into **Storage**: one page with **Storage**, **Health** and **Analyzer** switched under its title. Monitor keeps Monitor, History and Benchmark. Accounts without the storage permission find Health there, as before under Monitor.

### ⚡ Faster
- **The interface loads with a quarter of the data**: the web server now compresses it (brotli or gzip), about 0.5 MB instead of 2 MB on first load, and much less per language.
- **Every page answers sooner:** each request did about 0.15 s of needless work checking old sign-ins; that is gone. The list of virtual machines builds about three times faster with several machines.
- Pages left open in a background tab stop asking the appliance every few seconds, and catch up the moment you look at them again.
- Logs of the apps are kept to a few MB each instead of growing without end.

### 🌍 Web Browser
- **No more minimize, maximize and close buttons** in Chromium's own controls. They did nothing useful in the browser window, and close ended the browser. The tab strip, address bar and menu stay.

### 🧩 Extensions
- **The list of apps loads faster** when it was asked for a moment ago (the sidebar, the bell and the Extensions tab all use it): about a quarter of the time. Installing, removing, switching on or off shows at once.

## 26.11.22

*2026-11-22*

### 💽 RAID installs: important fix
- **The data volume now mounts on machines installed with RAID.** On an install across several disks, the data volume was not mounted when Ignis started, so machines, settings and apps were stored on the much smaller system volume instead. After this update the data volume is used, and everything that ended up on the system volume is moved onto it automatically at the first start; nothing is lost. If something exists in both places, the copy from the system volume is kept in the hidden folder `.from-system-volume` on the data volume. The first start after the update can take a little longer while this happens.
- **A RAID keeps working with one disk missing.** If a disk fails or is unplugged, Ignis now starts the data volume with the remaining disks instead of without it, and says so on the console. Replace the disk soon: until then there is no spare copy.
- **A disk that comes back is taken in again.** A disk that was missing for a while (a loose cable, unplugged for one start) is added back to its RAID by itself and rebuilt in the background.
- If the data volume can't be started at all — a disk is missing *and* the machine was not shut down cleanly — the console and the **Storage** page now say so and what to do, instead of only "did not mount".
- **Replace a failed disk from Storage.** When a disk of the system or data RAID is missing, **Storage** shows a card with both arrays and the free disks that are big enough. Pick one and choose **Use this disk**: it gets the same partitions as the other disks, the boot loader, and is rebuilt into the RAID in the background (hours on large disks; the machine keeps running, and the card shows the progress). Afterwards the new disk can start the machine on its own. **Monitor › Storage Health** points there too.

### 🗜️ Compression and deduplication for volumes
- **Choose per volume, when you create it or later** (right-click the volume › **Settings…**). Only what the filesystem can do is offered.
- **Compression** for btrfs and ZFS: off, fast or strong. It applies to what is written from then on.
- **Deduplication** for btrfs and XFS: once a week or every day, **at a time you choose** (and a weekday for weekly). At that time identical blocks of files already written are shared, at the lowest priority; the run is also listed in **Schedules**, and **Deduplicate now** starts one at once. The dialog shows the last run and how much it freed.
- **Deduplication for ZFS** works as data is written. It needs about 5 GB of RAM per TB of data, which the page says before you switch it on.
- **ZFS volumes are back.** Pools now come back after a restart and after an update; we checked mirrors, reboots and updates before offering ZFS again.

### ⚙️ Settings behind a gear
- **Every page's settings now open from a gear button right beside the page's ?**, instead of a **Settings** tab among the page's views. This applies to Containers and to every app with settings: AdGuard Home, Android Apps, Antivirus, Audio Station, Documents, Drive, Download Station, Live TV, Photos, Remote Desktop, Video Station, Web & Mail and Windows Apps.
- The gear is highlighted while the settings are open; click it again to go back to the view you came from. People who may not change an app's settings don't see the gear, just as they didn't see the tab.
- A game server's own **Settings** tab stays where it is: it belongs to that server, not to Game Servers as a whole.

### 🌍 Web Browser
- **Chromium's own controls on a computer.** The browser now shows Chromium's own tab strip, address bar and menu, just as you know them, while downloads, full screen and **More** sit in the page header. On a phone or a narrow window the Ignis toolbar stays, which is easier to use by touch. Change it per device under **Settings › On this device › Controls**; the browser follows the device that opened it last.
- **Your tabs are visible with the Ignis toolbar too.** A tab strip under the toolbar shows every open tab with its title. Click one to switch to it, or its **×** to close it. Before, a second tab could stay open without you knowing.
- **The address bar shows the page's address again.** Since the last update it stayed empty.
- **One connection per person.** Opening the browser again — a reload, a second browser tab, or coming back after the network dropped — now takes over your earlier connection instead of counting you twice ("2 watching"). Two connections at once had split the bandwidth between them and turned the picture blurry. The older tab says the browser was opened elsewhere and stays closed, so the two don't take it from each other.
- **Your own mouse pointer** is used over the browser, instead of a picture of the browser's pointer.
- **Settings** open from the gear beside the page's **?**; the toolbar's menu is now **More** (⋮).
- The browser no longer runs into the bottom edge of the window.
- The same one-connection rule applies to Windows Apps, Android Apps, Remote Desktop and the machine consoles: opening one again in a second tab takes it over.

### 📏 Benchmark
- **Monitor › Benchmark is tidier:** all scores in one card as tiles — CPU single and multi core, storage with its IOPS, and the GPU's video encoding. While it runs you see each part as a step: done, running or waiting.
- The system details use Ignis's own words: the Ignis version instead of "Loader", and no more "DSM" line.

### 🏠 Overview (new first page)
- **Overview** is the first page in the sidebar and where admins land after signing in: what the box is (name, Ignis version and whether an update is out, uptime, processor, memory, graphics cards, network cards with speed and address, drives, the UPS), what runs on it (machines, LXC and containers running of all, CPU, memory and storage, the space used per volume), the newest bell messages, and every installed app as a tile in its sidebar section. Every line and tile opens its page; **Add apps** leads to Extensions.
- **Getting started** moved here from Virtual Machines, with **Hide** and **Don't show again** as before.
- In the desktop layout Overview is the first icon too.
- **The Host statistics** are now a small **Host** tab on the bottom edge, at the right. Click it and the statistics slide up; click again and they slide away. Pages keep only that tab's height free at the bottom, so a long page no longer ends with a big gap.

- **This appliance looks tidier:** the Ignis version with its update state as a badge, the processor, graphics cards, memory and UPS as tiles, and the network cards and drives as short lists with their link, address, size and kind.
- **The Overview shows its values at once:** it remembers the last ones in your browser and refreshes them in the background, instead of filling in row by row.

### 📝 Office Editor (new app) and editing in Drive
- **Edit Word, Excel and PowerPoint files right in Drive:** with the new **Office Editor** installed, Drive's preview has an **Edit** button for .docx, .xlsx, .pptx and the OpenDocument files (.odt, .ods, .odp) and their older kin. The file opens in a full office editor in the same window and is saved straight back into the share as you work. Several people can edit the same file at once and see each other's changes.
- **Edit** is also in the right-click menu and in the bar that appears when you select a file. Only people who may write to that share get it.
- The Office Editor is Collabora Online, the online edition of LibreOffice. It starts by itself when you open a document (a few seconds) and stops again after half an hour without one, so it only uses memory (about 500 MB) while someone edits. Switch on **Keep running** on its page if documents should open at once.
- **Without the Office Editor**, Drive still edits text files: plain text, Markdown, code and CSV open in a simple editor with **Save** (or Ctrl+S). If someone changed the file in the meantime, Drive tells you instead of overwriting it. For an Office file, **Edit** tells you to install the Office Editor and takes you there.
- **Documents open like pictures and videos:** a double-click on a document, PDF, spreadsheet, presentation or text file in Drive opens it over the whole window on a dark background, the same way pictures and videos open. The name and "2 of 5" are at the top left, **Edit**, **Share**, Properties, Download and Close at the top right, and arrows at the sides (or the arrow keys) go to the file before and after. While you edit, the editor uses the whole width and the arrows are hidden. On a phone the document takes the full width.

### 📊 Storage Analyzer (new)
- **Monitor › Storage Analyzer** shows what uses the space on your volumes: a map of the folders you can click into, the space by kind of file and by when files last changed, the biggest files and folders, files that are there more than once, empty folders, files nobody has changed for three years, and a line of how the used space grows day by day.
- It scans every night (02:30 unless you choose another time) or when you press **Scan now**, at the lowest priority so your machines don't notice. Duplicates are compared by their content; what was read once is remembered, so later scans are quick.
- A right-click opens a file or folder in **Storage**, copies its path, or moves a file in a share to that share's recycle bin, where Drive can restore it. Every list can be saved as CSV.
- **Storage** has a button that leads straight there.

### 📺 Live TV (new app)
- **Watch TV in the browser:** from a DVB-T/T2, cable or satellite tuner in your box (USB or PCIe), from HDHomeRun and SAT>IP tuners on your network, or from IPTV playlists (M3U) with their guides (XMLTV). A guided search finds the channels of a tuner for your region; number them, mark favourites and switch off the ones you never watch.
- **Programme guide** from the broadcast itself or from XMLTV, as a grid. Click a programme to watch it, record it, or record the whole series.
- **Recordings:** record now, from the guide, at a time you set, or by series rules (title, keyword, channel, weekdays, time of day), with extra minutes before and after. When there are more recordings at once than tuners, the page says which ones can't be recorded. Recordings are saved as MKV in a folder you choose — by default one Video Station shows — and can be kept to the last few of a series or deleted after a number of days. Started, finished and failed recordings and a lost tuner reach the bell, email and webhooks.
- **For Plex, Jellyfin, Kodi, VLC and TVs:** switch on **Other players** to get a playlist and guide address, and Ignis also shows up as an HDHomeRun tuner. The port opens in the firewall only while this is on.
- Tuners in the box need the next system update, which brings their drivers.
- **The picture fits the window:** the player takes the room under the tabs, so the whole stream shows without scrolling, on wide screens too; the channel list beside it scrolls on its own. On a phone the player comes first, the channels below.

### 👥 One account for everything
- **Network Shares use your Ignis users.** A user's password for the web interface now also opens the shares (SMB) — no second account to make. Who may use a share is still set per share; the **Users** tab in Drive & Shares lists the users and links to the **Users** page.
- **FTP, FTPS and SFTP** sign in with the Ignis users too, for users given the new permission **FTP, FTPS and SFTP** on the Users page. Admins have it.
- A user whose password was set before this shows **Shares: set the password once more** on the Users page: set it once and it works for the shares as well.
- The separate share accounts of earlier versions are removed.
- SMB and FTP can't ask for a second factor: users with two-factor sign-in open the shares with their password alone.

### 🔋 UPS (new app)
- **UPS** watches the UPS your box runs on: plugged in by USB (the right driver is suggested for your model), through its network card (SNMP), or followed from another NUT server such as a Synology. The page shows the battery, the runtime left, the load and the voltages, a day of history and every event; going on battery, coming back, a low battery and a shutdown also reach the bell, email and webhooks.
- **When the power fails**, it shuts down cleanly whichever comes first: after a number of minutes on battery, below a battery level, or below a runtime. Your machines, LXC containers, Docker containers and apps go down in the order you set, each with its own time, then Ignis. The UPS can switch itself off and back on with the mains, so the box starts again by itself, and whatever was running before starts again too.
- **Share the UPS**: switch on the NUT server and a Synology, another Ignis or a PC on the same UPS follows it through Ignis and shuts down with it (port 3493, opened only on the adapters you pick).

### 🌐 Network boot
- **UEFI computers start from the network too:** Network & Firewall › Network boot now also starts newer computers that boot with UEFI, both on networks where Ignis hands out the addresses and next to your router. They get a short menu with **Ignis Recovery**; the ISO images and netboot.xyz are one entry further. Secure Boot has to be off on that computer for network boot.
- **Network boot no longer stops answering** after a computer's second try, and it no longer keeps a processor core busy. Android Apps now starts while network boot is on.

### 📹 Surveillance
- **HTTP cameras:** when you add a camera, choose what its address is: an RTSP stream, an MJPEG stream, a snapshot picture fetched every few seconds, or an HLS stream. An example address is shown for each. **Test** now works for https cameras too, without the Video Compute Runtime, and says what the camera sends.
- **Streams for other apps:** in a camera's settings, switch on RTSP, MJPEG, HLS or a snapshot picture for Home Assistant, VLC or a TV. Each stream has its own private address with **Copy**; **New address** or switching the stream off shuts the old address out. RTSP opens only on the networks you pick (Cameras › Streams for other apps), with an entry per camera in the firewall. MJPEG, HLS and the snapshot need the next system update.
- **Before, one user and password let other apps watch every camera over RTSP.** If that was on, each camera now has its RTSP stream switched on instead, at a new address. Copy the new addresses from the cameras' settings into your other apps.
- **Live view fits the screen:** 1, 4, 9 or 16 cameras fill the page without scrolling, and full screen shows every camera whole, on wide monitors too.
- **One camera at a time:** click a camera in the Cameras list (or right-click it and choose **Watch live**) to watch it live in a window of its own, with full screen and a shortcut to its recordings.

### 📅 Calendar & Contacts 1.1.0
- **Calendars and contacts open on the page:** the new **Calendar** tab shows month, week and list views of all your calendars, each in its colour, with your tasks beside them; the **Contacts** tab lists your contacts by letter with a search and shows the one you pick. Under Calendars and address books, **Open** (or a click on the name) takes you there.
- Add, change and delete events: all day or with times in a time zone, repeating daily, weekly, monthly or yearly, with reminders. Changing or deleting one event of a series asks whether it is for this one or all of them. Drag events to another day or time, or their lower edge to make them longer.
- Add and change contacts in place: photo, phone numbers, email addresses, addresses, websites, birthday, notes and groups. Contacts' birthdays can be shown in the calendar. Your phones and Thunderbird see every change.

### 🪟 Windows Apps and app screens
- **Programs without the desktop:** a program opened from its tile in Apps now shows on its own, filling the screen, without the Windows desktop and taskbar; its dialogs open over it, and installers and other fixed-size windows keep their size in the middle of the screen. A list above the screen switches between the open programs, and another between bottles when several run at once. Right-click a tile to open it on the desktop instead; **Open desktop** still opens the whole Windows desktop.
- **Uploading into a bottle works again** ("could not write the file into the bottle"), and the Windows desktop shows instead of staying black.
- **Install and upload from the Desktop view:** **Install a program** and **Upload file** sit in the Desktop view's toolbar, and you can drop files onto the screen: installers (.exe, .msi) go to C:\Installers and start, other files land on the Windows desktop.
- **Internet and Home network per bottle:** switch each off under **Network** on a bottle, or with a right-click on it in Apps or Bottles. Both off, the programs have no network at all; the screen keeps working. New and existing bottles have both on.
- **Drives you share with a bottle as read and write**, and your shared folder, can be written to again from Windows programs.
- **Faster app screens:** the browser no longer holds every picture back for about 70 ms, so clicks, typing and the pointer answer sooner in the Web Browser, Windows Apps, Android Apps and machine consoles.
- **A port for each kind of app screen:** Web Browser 6172, Windows Apps 6173, Android Apps 6174, machine consoles 6175, Remote Desktop 6176 (UDP and TCP), each with its own named entry in the firewall. Change them under Graphics Runtime. Several people and sessions share an app's port.
- The Sessions and Screen settings of Windows Apps, Web Browser and Android Apps are tidied into one row, with what the screen is drawn on shown beside them.

### 📁 Drive & Shares
- **Shares & Drive is now called Drive & Shares**, and opens on Drive.
- **Previews for office files**: Word (.docx, .docm, .dotx, .dotm) and PowerPoint (.pptx, .pptm, .ppsx, .ppsm, .potx, .potm) as pages and slides; Excel (.xlsx, .xlsm, .xltx, .xltm, .xlsb, .xls, .xlt, .xlw) and Lotus sheets as a table with a tab per sheet; OpenDocument (.odt, .ods, .odp and their templates) and the old OpenOffice 1.x files.
- **The old Office formats too**: .doc, .dot, .ppt, .pot, .pps and Works .wps show their text (slide by slide for presentations, with their pictures); Download gives you the original.
- **More previews**: .rtf, .epub e-books, Markdown, code and settings files with line numbers and colours, .csv and .tsv as a table, what is inside .zip and .tar archives, HEIC and TIFF pictures. Share links show the same previews.
- Previews open in a closed-off frame that cannot reach your session; very large and password-protected files are not previewed, Download opens them.
- **Convert files** (Drive and Video Station): videos into H.264 in MP4, which plays almost everywhere (or H.265 / AV1), at their size or at most 1080p or 720p; music into AAC or MP3; HEIC, TIFF and WebP pictures into JPEG. Beside the original or into another folder, and the original into the recycle bin if you like. **Convert new files here…** on a folder converts everything that arrives there once its upload is finished. The **Conversions** tab shows the progress, and the bell tells you when it is done. Uses the graphics card when it can; needs the Graphics Runtime.

### 🎬 Video Station and Audio Station

- **Videos that have to be converted for the browser play again** in Video Station; before, the player stopped with "The stream stopped: manifestLoadError".
- **TVs and players find the media servers again:** the DLNA servers of Video Station and Audio Station stopped right after starting.
- **Convert new files…** on a library folder starts with videos only, so posters and fan art stay as they are.

### 🎨 A fresher look
- Boxes lift off the background with a soft shadow, and box titles carry a touch of your highlight colour.
- Each sidebar group has its own colour (Files, Media, Web & Mail, Network, Apps and the rest), on the desktop's app launcher and icons too.
- Pages show their key numbers under the title: running and stopped machines, vCPUs and memory in use out of the host's, free space, images and more.
- Machine, LXC and container cards show their state as a coloured edge, and running machines show small CPU and memory rings.
- The same state edge everywhere something runs: installed extensions, game servers, cameras, Windows Apps bottles, downloads, VPN servers, devices and tunnels, backup tasks, websites, iSCSI targets and LUNs, apps from App Station, DSM machines and the AI engine. Running containers, LXC containers and game servers show CPU and memory rings too, and the apps' boxes lift off the background like the rest.
- Pages and dialogs open with a short, gentle animation (off if your system asks for less motion).

### 🛡️ Antivirus (new)
- **Antivirus** scans your shares for viruses and other malware with ClamAV. **Scan everything** checks every share (and any folders you add), **Scan this folder** just one; a **Scan for viruses** task on the Schedules tab does it regularly. Disk images and ISOs are left out unless you say otherwise.
- Infected files go into a **quarantine** that only the appliance can read, or are only reported, as you choose. **Restore** puts a file back with its owner and permissions; **Not a threat** stops a signature from being reported again.
- **Scan new files as they arrive** (optional): files copied into the shares are checked within seconds. It needs the scanner kept loaded, which takes about 1 GB of memory; otherwise the scanner loads only while a scan runs.
- The virus definitions download at the first start and update by themselves every 24 hours, or as often as you set under **Settings › Virus definitions**; switch that off to update only by hand or on a schedule. **Update before each scan** fetches new ones before every full, folder and scheduled scan (unless they are under an hour old); if that fails, the scan still runs and History says so. Findings appear under the bell, and by email or webhook if your notifications send security messages there.
- **Leave out** folders you pick by name and kinds of files (`*.iso`, `*.log` …); every scan skips them, new files included. A finding's menu has **Exclude this folder**.

### 🖥️ Remote Desktop (new)
- **Remote Desktop** opens the PCs, servers and virtual machines on your network inside the page, over **RDP** (Windows), **VNC** and **SSH**. Add a connection with its name, address, user and password; the password is kept encrypted on Ignis, or asked each time you connect.
- **RDP** fits the remote screen to your browser window, passes copy and paste and sound, and can show a shared folder of yours in Windows as a drive; **Upload** puts files into it. Network Level Authentication and TLS are chosen by themselves, or set by hand.
- **On the screen:** Ctrl+Alt+Del, Clipboard, full screen and Disconnect. Several people can watch the same connection; one has control at a time and the others can take it.
- **Groups and sharing:** sort connections into groups, keep them for yourself or share them with all users or the ones you pick. The list shows which computers answer, the ones used last come first, and **Test** tries a connection before you save it. **Wake** starts a PC that sleeps (Wake-on-LAN). Your Ignis machines' consoles stay on the Virtual Machines page.
- It shows on its own port, **6176** (UDP and TCP), with an entry of its own in the firewall; change it under Graphics Runtime. Requires the Graphics Runtime.

### 📄 Documents (new app)
- **Documents** is a paperless archive. Scans, PDFs, photos of letters and office files are read with text recognition (German, English, French, Spanish and Russian) and kept as **searchable PDFs** beside the original, in a share you choose, sorted by year.
- **Getting documents in:** drop files on the page, let your scanner save to the inbox folder (scan to share), or have Documents collect the attachments from a mailbox (IMAP). A file it already has is set aside, not filed twice.
- **Filing:** correspondents, document types, tags and fields of your own (an amount, a contract number, a date …). Documents learns from what you file and suggests, or fills in by itself, the correspondent, type and tags of the next letter; **rules** file what always looks the same. The date of the letter is found in its text.
- **Finding:** search for any word in a document, also the start of one (`stadtw*`), with the place it was found; filter by correspondent, type, tag and date, and save a search as a view. Open a document to read it in the page, or download the original or the searchable PDF.
- **Each user has their own documents**, and can share single documents with other users or a role. Admins see everything and choose the archive and inbox under **Settings**.

### 🛠️ Smaller fixes
- **Dialogs** waste less space: slimmer title and button bars, less padding, forms use the window's height instead of scrolling inside a small box, logs and consoles fill nearly the whole window, and on a phone every dialog takes the whole screen. **Remote Desktop**'s file upload works.
- **Network Shares**: Ignis shows up by itself under Network in Windows Explorer, in the Finder on a Mac and in Linux file managers (a switch on the Connect tab turns it off).
- **Network Shares:** accounts made for shares can sign in again; before, only root got in. Each account now sees just the shares it may open.
- **Ignis Recovery** shows French, Spanish, German and Russian correctly on every screen; accents and Cyrillic letters were garbled before.
- The last user account with user rights can be deleted when root has a password, since root still signs in as an admin then.
- In every app, settings you turn on or off are now switches, the same everywhere; boxes you tick to pick things (shares, cameras, days, networks) stay checkboxes.
- **Android Apps** has Android's taskbar at the bottom of the full screen: your pinned apps, all apps and Back, Home and Recents, for switching between apps like on a tablet. Switch it off under Settings › Screen; it shows from the next start.
- **Android Apps** opens on the full Android screen with its home screen by default. With **One window per app**, the page now says that Android shows only the apps you open, with buttons to open an app or switch to the full screen, and **Home** opens the app list.
- **Calendar** and the desktop clock's calendar start the week on Monday.
- **Network Shares** follow a changed network address again: after Shares had restarted once, every later update of its addresses got stuck in the background, and the stuck updates piled up.
- No more false "data volume is not mounted" message on the console at every start.
- **Android Apps** start on Intel and AMD graphics cards again (faster than on the processor). If Android cannot start on the card, it switches to the processor by itself and tells you.
- The top bar looks the same in the classic and the desktop layout (the desktop's slim bar), with the bell, the layout switch and your account in the same places. The desktop's "Show desktop" button is gone: Alt+Shift+D or a right-click on the desktop or the taskbar still does it.
- The classic layout looks the same with solid and with glass boxes: the sidebar and each page's title sit on their own rounded box in both, apps' pages included. The sidebar's first entry sits higher, and longer names such as Calendar & Contacts fit.
- Short pages no longer scroll by the room kept for the Host button; that room is only added when a page is longer than the window.
- **Storage:** the drives in your box are shown as boxes, like Appliance data, Disk images and ISOs above them.

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
- Arx DSM shows the progress bar of a loader update again.

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
