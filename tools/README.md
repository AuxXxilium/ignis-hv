# 🧰 Tools

Programs to go with Ignis. They are on a release of their own, [tools-26.11.22](https://github.com/AuxXxilium/ignis-hv/releases/tag/tools-26.11.22), so Ignis never takes them for an update.

## 💻 The Ignis app 0.5.1

Drive, Chat & Calls, your cameras, and backups of your computer — for your computer.

| System | Download | Notes |
|---|---|---|
| Windows | [ignis-app-0.5.1-windows-x64.zip](https://github.com/AuxXxilium/ignis-hv/releases/download/tools-26.11.22/ignis-app-0.5.1-windows-x64.zip) | Unzip and start `ignis_app.exe`. Includes the whole-system backup for Ignis Recovery. Windows may warn once, because the app isn't signed |
| macOS | [ignis-app-0.5.1-macos.dmg](https://github.com/AuxXxilium/ignis-hv/releases/download/tools-26.11.22/ignis-app-0.5.1-macos.dmg) | The app isn't signed: open it the first time with right-click › **Open** |
| Linux (x86-64) | [ignis-app-0.5.1-linux-x64.tar.gz](https://github.com/AuxXxilium/ignis-hv/releases/download/tools-26.11.22/ignis-app-0.5.1-linux-x64.tar.gz) | Unpack and start `ignis-app`. The tray icon needs a desktop that shows tray icons (on GNOME: the AppIndicator extension) |

* **Starts at login**, quietly into the tray. Switch it off in the app's settings.
* **Backups of your computer**: your own files without any password. Backing up every user's files, or the whole computer for Ignis Recovery, asks once for the administrator password (on Linux the system's own password dialog, on macOS the usual one, on Windows the usual prompt).
* Sign in with your Ignis user, the same as in the browser.
* **Chat & Calls**: your conversations and voice and video calls, end-to-end encrypted. A new device is approved from one you already use, by its code, or with your recovery key.

## 🛟 Ignis Recovery

Brings a computer back from its backup on Ignis: start the computer from Ignis Recovery, sign in, pick the computer and the date, pick the disk, and it is written back.

| Download | Notes |
|---|---|
| [ignis-recovery.iso](https://github.com/AuxXxilium/ignis-hv/releases/download/tools-26.11.22/ignis-recovery.iso) | Burn it, or write it to a USB stick (the same file works for both, e.g. with Rufus or balenaEtcher). Starts on BIOS and UEFI computers |

You can also start Ignis Recovery **over the network** without any stick: switch on **Network & Firewall › Network boot** on Ignis and start the computer from the network. The **Backup & Sync** page offers the same image for download.

## ✅ Checksums

[SHA256SUMS](https://github.com/AuxXxilium/ignis-hv/releases/download/tools-26.11.22/SHA256SUMS) — the SHA-256 of every file above.
