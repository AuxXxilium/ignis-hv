# Ignis extensions

An extension adds something to Ignis: a background service, a page in the web
interface, or both. It is installed from the **Extensions** tab and keeps
working across reboots and updates.

## Make one in three steps

**1. Copy the template**

```sh
cp -r presets/template my-extension
```

**2. Edit two files**

- `manifest.json`: set `id` and `name`
- `control`: put your work in `DO_WORK`, and set how often it runs with `INTERVAL`

**3. Package it and install it**

```sh
tar czf my-extension.tar.gz my-extension
```

Upload `my-extension.tar.gz` on the **Extensions** tab, then click **Enable**.
A new extension is never started until you enable it.

That's it. The template already handles starting, stopping, the status badge
and the log.

> **Just want a page, with no background work?** Set `NEEDS_SERVICE=no` in
> `control` and put your page in `www/index.html`.

## The examples

| Folder | What it is |
| :-- | :-- |
| [`presets/template/`](presets/template) | The starting point. Copy this one |
| [`hello-world/`](hello-world) | A finished example: a service that logs the number of machines every 30 seconds, and a page that shows it |

## The extensions made for Ignis

Ignis's own extensions, each installed from the **Extensions** tab like any
other and updated on its own, apart from Ignis. The tab lists what the
[releases](https://github.com/AuxXxilium/ignis-hv/releases) of this repository
publish, and installs or updates it from there:

| Extension | What it is |
| :-- | :-- |
| `ignis-docker` | Docker for the Containers page. Images and containers stay on disk while it is turned off |
| `ignis-shares` | Network Shares: folders shared over SMB like a NAS, and over SFTP and FTPS if you want. Accounts made here open the shares and nothing else |
| `ignis-drive` | Drive: the shared folders in the browser, with uploads, previews and share links for people without an account. Requires Network Shares |
| `ignis-photos` | Photos: a timeline, albums, people, places and things, editing and sharing |
| `ignis-video` | Video Station: movies and TV shows in the browser, and a DLNA server for TVs, consoles and Kodi |
| `ignis-surveillance` | Surveillance: records IP cameras, live view, motion events and playback, and recognises people, vehicles, faces and plates |
| `ignis-downloads` | Download Station: links, torrents and magnet links into a folder you choose |
| `ignis-web` | Web Station: your own websites with PHP 8.3, 8.4 or 8.5 and databases, WordPress in one click, memcached, and a DNS server for your own domains on the network cards you choose. Takes ports 80 and 443, so the interface moves to 8080 and 8443 |
| `ignis-mail` | Mail Server: email for your own domain, with webmail and a spam filter. Works best with Web Station: webmail, certificates, and its DNS server gets the mail records by itself |
| `ignis-vpn` | VPN: WireGuard, OpenVPN, IPsec and Tailscale, to reach home or to send machines and containers through a VPN |
| `ignis-san` | SAN Manager: storage for other computers over iSCSI |
| `ignis-games` | Game Servers: about 150 games, with a console, backups and timetables. Requires Docker |
| `ignis-ai` | AI: language models on your own GPU beside online services, in one chat, with an API for other apps |
| `ignis-arx` | Synology DSM machines on the Arx loader, kept up to date |
| `ignis-adguard` | AdGuard Home as the DNS server for your network, on the network cards you choose; it can share port 53 with Web Station's DNS server on another card. dnsmasq must be off under **System > Services** |
| `ignis-dhcp` | A DHCP server for the networks you choose |
| `ignis-firewall` | Who can reach which service, and filtering between two network ports. The interface, SSH and the consoles always stay open, and a change undoes itself unless you confirm it. Locked out anyway? `ignis-ext disable ignis-firewall` on the console |
| `ignis-nvidia` | The NVIDIA driver for containers. Made for one Ignis release's kernel, so the tab offers the one that fits your system |
| `ignis-vcrt` | Video Compute Runtime: video conversion on the GPU for the media apps, and 3D graphics for Linux machines. Made for one Ignis release, so the tab offers the one that fits |
| `ignis-vision` | Vision Runtime: the image recognition Photos and Surveillance use |

Every extension with a page has an endpoint of its own next to it, the way
described under [An endpoint of your own](#an-endpoint-of-your-own).

### Where they come from

A release does not need to carry every extension. For each one the tab offers
the newest release that contains it, so a release with only the system update,
or with one or two extensions, leaves the others as they were. Pre-releases are
skipped. Every download is checked against the SHA-256 GitHub records for it,
and one without a checksum is not installed.

Your own extensions are not published there: install them from a file with the
upload button at the top of the same tab.

## What's in an extension

```
my-extension/
  manifest.json     required: what it is
  control           required: the script Ignis calls
  www/              optional: a page, shown at /ext/<id>/
```

### manifest.json

```json
{
  "id": "my-extension",
  "name": "My Extension",
  "version": "1.0.0",
  "description": "One line about what it does.",
  "author": "you",
  "api": 1
}
```

- **`id`**: 2–32 characters, lowercase letters, digits and dashes. This is what
  the extension is installed as, whatever its folder is called
- **`name`** and **`version`**: shown on the Extensions tab
- **`api`**: leave it at `1`
- **`requires`** and **`recommends`** (optional): other extensions yours needs, or works better with, each with a short reason, e.g. `"requires": [{"id": "ignis-docker", "why": "runs each server as a container"}]`. The Extensions tab shows them, offers to install them, and will not turn yours on while something it requires is missing
- **`schedules`** (optional): tasks yours offers on the Schedules tab, each with an `id`, a `label` and its settings; Ignis runs them with the `schedule` script in your extension's folder (`schedule run <task> <settings.json>`)
- **`icon`** and **`perm`** (optional): the sidebar entry for the extension's
  page, below, and the extension's row on the Extensions tab. `perm` is the
  permission an account needs to see the entry and to call the extension's
  endpoints, such as `system`, `storage` or `service`; a name that is not one
  of Ignis's permissions is refused at install. `icon` is either the name of one of Ignis's own icons or one emoji:
  - **A name** draws that icon in the interface's own outline style, so it sits
    with the built-in pages and follows the theme. Written exactly as here, as
    the extensions made for Ignis use them: `activity`, `ban`, `battery`, `box`,
    `brickWall`, `camera`, `check`, `clock`, `containers`, `copy`, `cores`, `cpu`,
    `database`, `disc`, `display`, `download`, `edit`, `eraser`, `expand`,
    `extensions`, `file`, `fileText`, `folder`, `folderOpen`, `folderPlus`,
    `folderShare`, `gauge`, `globe`, `gpu`, `hardDrive`, `health`, `heart`,
    `history`, `import`, `info`, `key`, `layers`, `link`, `list`, `machines`,
    `memory`, `monitor`, `moon`, `more`, `move`, `network`, `passthrough`,
    `pause`, `pie`, `plug`, `plus`, `powerOff`, `radio`, `refresh`, `rename`,
    `restart`, `schedules`, `search`, `shield`, `shutdown`, `sliders`,
    `sparkles`, `spinner`, `start`, `stop`, `storage`, `sun`, `system`, `tag`,
    `terminal`, `thermometer`, `timer`, `trash`, `upload`, `usb`, `user`,
    `userPlus`, `users`, `warning`, `zap`, and since November also `apps`,
    `arrowUp`, `chevronDown`, `close`, `eye`, `film`, `gamepad`, `helpCircle`,
    `image`, `layoutDesktop`, `layoutSidebar`, `mail`, `maximize`, `minimize`,
    `pin`, `restoreWindow`, `showDesktop`, `snapLeft`, `snapRight`
  - **Anything else** is shown as written, which is how an emoji works. A name
    Ignis does not have is shown as plain text too, so check the spelling
    against the file

### control

A shell script. Ignis runs it with one word saying what to do:

| Word | When |
| :-- | :-- |
| `install` | the first time it is installed |
| `upgrade` | when a newer version is installed over it. If this fails, the old version is put back |
| `start` / `stop` | when you enable or disable it, and at boot and shutdown |
| `status` | to show the Running badge. Exit 0 if running |
| `log` | when you click **Log**. Print the log |
| `uninstall` | before it is removed |

The template fills in all of these. You only need the parts marked as yours.

### What your script can use

| Variable | What it is |
| :-- | :-- |
| `IG_EXT_DIR` | your own folder. **Keep your files here.** It survives updates and is deleted when the extension is removed |
| `IG_EXT_ID` | your id |
| `IG_ROOT` | the Ignis data folder, `/storage/ignis` |

The Ignis commands are available by name, for example:

```sh
ignis-vm list          # machines and their state
ignis-vm start <name>
ignis-net list         # virtual networks
```

## A page in the interface

Anything in `www/` is shown at `/ext/<id>/`. A plain `index.html` is enough,
with no framework and no build step. The page can call Ignis with the session of
whoever is signed in:

```js
const token = localStorage.getItem('ignis_session_token');
const r = await fetch(`../../listVMs.cgi?token=${encodeURIComponent(token)}`);
```

`hello-world/www/index.html` shows this working.

While the extension is enabled, its page also gets an entry of its own under
**Extensions** in the sidebar and opens inside Ignis.

### Looking like the rest of Ignis

Link the interface's extension theme in your page's `<head>`:

```html
<link rel="stylesheet" href="../../ignis-ext.css">
<script src="../../ignis-ext.js"></script>
```

The page then gets the same background, cards and buttons as the interface.
It follows the user's dark mode and highlight colour, and updates live when
they change either one. Both files ship with Ignis under these fixed names, so
the links keep working after updates. Put the script in `<head>` so a dark page
doesn't flash white while it loads.

Headings, paragraphs, links, `code`, `pre` and form fields are styled without
any class. For the rest:

| Class | What it is |
|---|---|
| `ig-page` | A centred page column |
| `ig-header`, `ig-header-title`, `ig-header-actions` | The page heading, with buttons on the right |
| `ig-icon-tile` | The coloured tile for your extension's icon (an emoji or an `<svg>`) |
| `ig-stack` | Cards stacked with the interface's spacing |
| `ig-grid` | Equal columns that fold to one on a narrow window |
| `ig-card`, `ig-card-header`, `ig-card-body` | A card with a title band |
| `ig-stat`, `ig-stat-label`, `ig-stat-value` | A small figure on a tile |
| `ig-btn`, `ig-btn-primary`, `ig-btn-danger` | Buttons |
| `ig-badge` + `-success` / `-warning` / `-error` / `-info` | Status badges |
| `ig-dot` + `-success` / `-warning` / `-error` | A status dot |
| `ig-notice`, `ig-notice-error` | A callout box |
| `ig-table` | A table |
| `ig-muted`, `ig-small`, `ig-mono` | Text helpers |

The template and `hello-world` both use these, so they are a good place to
start.

### An endpoint of your own

A page that needs to change something on the host can ship its own `.cgi` in
`www/`. It runs as root, like Ignis's own endpoints.

Ignis checks every request before your script runs. It refuses the request
unless the extension is enabled, the caller is signed in, and, when the
manifest names a `perm`, the account holds that permission. Send the session
token in the query string (`?token=…`), as every example here does, so your
script still gets the request body untouched. Only scripts directly in `www/`
or a folder under it are run, and only while the extension is enabled.

That check is a floor. An endpoint that needs a stricter permission for some
actions checks for it itself, the same way Ignis's own endpoints do:

```bash
#!/usr/bin/env bash
. /opt/ignis/lib/vm.lib.sh
. /opt/ignis/lib/auth.lib.sh
auth_parse_params
require_session          # anyone signed in
require_perm system      # and allowed to do this
vm_ok '"hello":"world"'
```

Ignis has already done this once by the time the script runs, so checking
again costs little. The script also gets `IG_EXT_ID`, `IG_EXT_DIR` and
`IG_EXT_WWW`, as `control` does, and `IG_USER`, the account asking.

The extensions made for Ignis that have a page all work this way: `www/api.cgi`
next to the page.

## Machines an extension looks after

An extension that creates virtual machines can mark them as its own, and the
Machines tab then shows that on each one's card.

Create the machine through `saveVM.cgi` like the interface does, with the
extension's id in the definition:

```json
"managed_by": { "ext": "my-extension" }
```

The editor keeps the field when someone changes the machine. To say something
about the machine on its card, write `vms/<machine name>.json` in the
extension's own folder (`$IG_EXT_DIR`), at most 4 KB:

```json
{ "label": "Loader 1.0.1 · DSM 7.4", "note": "Update available", "attention": true }
```

The card shows `label` as a chip that opens the extension's page, or the
extension's name if there is no label. `note` appears beside it, highlighted
when `attention` is true. Write the file whenever the status changes; Ignis
reads it each time it lists the machines and never writes it.

## Good to know

- **Extensions run as root.** They can do anything Ignis can, so install only
  what you trust.
- **The files in `www/` are not behind the login**, only the `.cgi` scripts
  are. Anyone who can reach Ignis can open the rest. Don't put anything private in those files; load the data from
  Ignis instead, since those calls do check the login.
- **Each step has a time limit:** 5 minutes for install, upgrade and uninstall,
  1 minute for everything else.
- **`status` runs often**, so keep it quick.
- **Don't end `control` with a plain `exit 0` for every case.** Then `status`
  always says the extension is running. The template avoids this for you.
