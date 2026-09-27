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

## Good to know

- **Extensions run as root.** They can do anything Ignis can, so install only
  what you trust.
- **Pages in `www/` are not behind the login.** Anyone who can reach Ignis can
  open them. Don't put anything private in those files; load the data from
  Ignis instead, since those calls do check the login.
- **Each step has a time limit:** 5 minutes for install, upgrade and uninstall,
  1 minute for everything else.
- **`status` runs often**, so keep it quick.
- **Don't end `control` with a plain `exit 0` for every case.** Then `status`
  always says the extension is running. The template avoids this for you.
