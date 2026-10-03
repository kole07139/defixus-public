<div align="center">

# 🛡️ Defixus (Anti-Cheat) and QoL Admin Tool

### 🔒 Advanced Fabric Client Verification & Integrity Protection

Detect unauthorized mods • Verify file integrity • Monitor resource packs • Protect your community

![Fabric](https://raw.githubusercontent.com/kole07139/defixus-public/refs/heads/images/fabric-banner.png)
[![Kofi](https://raw.githubusercontent.com/kole07139/defixus-public/refs/heads/images/kofi-banner.png)](https://ko-fi.com/kole07139)
[![Discord Server](https://raw.githubusercontent.com/kole07139/defixus-public/refs/heads/images/discord-banner.png)](https://discord.gg/mZxXk3fC3w)

![Minecraft](https://img.shields.io/badge/Minecraft-1.21.11_–_26.3-green)
![Java](https://img.shields.io/badge/Java-25-orange)
![SHA256](https://img.shields.io/badge/Integrity-SHA--256-red)
![Discord](https://img.shields.io/badge/Discord-Webhooks_Integration-5865F2)
![Statistics](https://img.shields.io/badge/Player_Statitstics-Supported-blue)

---

### ⚡ 🔐 SHA-256 Live Verification 🔐 ⚡

Defixus is a powerful anti-tampering and verification system for Fabric servers.

### Supports Minecraft 26.x and 1.21.11 | ViaVersion/ViaFabric/Geyser/Floodgate integrated



Unlike traditional whitelist solutions, Defixus validates not only which mods are installed, but also their exact integrity through SHA-256 checksum hashing, ensuring that modified, disguised or tampered clients cannot bypass server security policies defined by Defixus.
Built for whether large or small communities that require a control over the client environment.

</div>

---

# ✨ Features


## 🔍 Advanced Verification Engine & QoL Admin Tool

Defixus verifies every mod installed on the client.

Unlike traditional whitelist systems, Defixus checks:

- 📦 Mod Verification and Compilation Integrity
- 🎨 Resource Pack Verification and Compilation Integrity
- 🔐 SHA-256 File Hash for Graylisted Mods and Resourcepacks
- 🧩 Client Anti-Cheat Integrity
- ⚡ Runtime Resource Pack Monitoring for in-game changes
- 🛡️ Ability to **Block Resource Pack changes in-game**
- 📡 Ability to send all the information with **Discord Webhook** alterts
- 📊 Tracks everything for statistics puroposes
- 🔢 Quality of Life Discord Embeds with statistics related to the alert
- 👮 OP Bypass Join Mod/packs verification
- ⚙️ Ability to track every command someone does with a **Discord Webhook** alert
- 🖥️ Ability to track the console with a **Discord Webhook** code forwarding


## 🤖 Defixus to Discord Integration

Receive real-time security notifications directly inside Discord by using Discord Webhooks URLs directly in the config files. You can choose which alert goes through which discord channel, and you can use that whether for security or transparency with your community. About the command tracking, no restriction on who uses the command, even OP's are checked by real-time verifications.

> For more information, see the [admin explanation section](#-server-admin-explanation-and-setup) and the [admin configuration section](#-a-detailed-walkthrough-on-defixus-configurations).

> For download instuctions, see the [installation section](#-installation).


---
# 🛡️ Why Defixus?

Most whitelist systems only verify:

```text
Mod ID
Version
```

Defixus verifies:

```text
Mod ID
Version
Resource Packs
SHA-256 Hash both for Mods and Resource Packs
Client and Defixus Integrity
Runtime Client Modifications for Mods and Resource Packs
Ability to Block Runtime modifications
```

Left to you the ability to select **which of these runtime checks can result in a Discord Altert** with Discord Webhooks URLs and in **which discord channel**.

Defixus also does:

```text
Huge statistics both total and per player
JOIN / QUIT Server Discord Alert
START / STOP Server Discord Alert
OP Bypass with Discord Alert
Command Tracking with Discord Alert for every command (you can program it in configs)
```

This means that even if a malicious player modifies a whitelisted mod and keeps the same Mod ID and Version, Defixus can still detect it which results in a tamper and a kick from the server.

Example verification data:

```text
defixus:1.0.0:d43fa1c9c9...
sodium:0.6.13:ab923e4f11...
iris:1.8.5:f38ac52f9f...
```

---

# ⚡ Verification Flow


Verification happens automatically when a player joins.

```text
Player joins
      │
      ▼
Client Presence Check
      │
      ▼
Mod Scan
      │
      ▼
SHA-256 Checksum
      │
      ▼
Resource Pack Scan
      │
      ▼
Data Sent To Server
      │
      ▼
Whitelist Validation
      │
 ┌────┴────┐
 │         │
PASS     FAIL
 │         │
 ▼         ▼
Join     Kick
Allowed  + Error Code
+
Runtime
Tracking
```

Most verifications complete in less than a second. It depends on the number of mods and resource packs the client does have.

---

# 🎨 Resource Pack Protection

Defixus provides the same level of protection for resource packs as it does for mods.

## Supported Features

| Protection              | Supported |
| ----------------------- | --------- |
| Pack Whitelist          | ✅         |
| Pack Blacklist          | ✅         |
| Pack Graylist           | ✅         |
| SHA-256 Validation      | ✅         |
| Runtime Monitoring      | ✅         |
| Modified Pack Detection | ✅         |
| Pack Change Detection   | ✅         |
| Auto Kick               | Optional  |

If you are an admin, you can also enable:

```json
"block-pack-change": true
```

to prevent players from changing the active resource pack through the normal in-game selection interface. See the admin example config down below.


---

# 🧑‍💻 What is Defixus ideal for?

Defixus is particularly suitable for:

* 🏆 Competitive Servers
* ⚔️ PvP Servers
* 🏰 RPG Servers
* 💰 Economy Servers
* 🔒 Private Communities
* 🎪 Event Servers
* 📜 Whitelisted Servers
* 🧩 Curated Modpacks

Any server requiring a strict control over the client environment can benefit from Defixus.


---

# ⚙️ Server admin explanation and setup

## 🟢 Whitelists


Allows the files which matches the whitelisted secured **mod ids**. This by default include the libraries (most of them). You want to put the ids in `mod_whitelist.json` or `pack_whitelist.json`

### Supported

* Mods
* Resource Packs

### Validation process

```text
File Name
Version
SHA-256 Hash
```

## 🔴 Blacklists


Known prohibited content can be blocked immediately by adding its identifiers to `mod_blacklist.json` or `pack_blacklist.json`. These lists are empty by default; administrators supply the entries. However, for Modpack oriented servers, i recommend to use the graylist system instead of blacklists, because it allows you to have a more strict control over the mods and resource packs that are allowed on your server (see graylist section below).

Useful for:

* Cheat mods
* Exploit mods
* Unauthorized utilities
* Prohibited resource packs

It already comes with a series of known hack mods.

### Supported

* Mods
* Resource Packs

### Scanning process

```text
File Name
Version
SHA-256 Hash
```

## 🟡 Graylists


Graylists are folders where the server places mods (`graymods/`) and resource packs (`graypacks/`) that it wants to verify the integrity of and **compare with the client correspondent mod**. When a client connects, the server checks whether the corresponding mods or packs are present on the client and compares them against the server versions using integrity SHA-256 hash check. If the client ones do not match with the gray-listed ones of the server, the client cannot join the server.

Unlike whitelists, graylists allow administrators to selectively enforce validation on specific files whether jars (mods) or zips (packs), giving them much finer control. As a result, gray-lists provide a more powerful way to ensure the integrity of mods and resource packs when they are present on the client. You can use graylists to enforce that only these mods can be allowed to be in the client by enabling the `kick-unapproved-mods` and `kick-unapproved-packs` options in the `verification/settings.json` file.

With "unapproved" is meant that the mod or pack **is not present** in the whitelist or graylist, so in this sense is not "approved" by the server.


Perfect for:
* More strict control whether mod or pack
* Exact match of the jar file (mod) or zip file (pack)
* Modpack oriented servers that want to enforce a specific modpack and its version

### Supported

* Mods
* Resource Packs

### Scanning process

```text
File Name
Version
SHA-256 Hash
Check if SHA-256 is equal to the same file loaded on graymods/ or graypacks/
Ability to kick the player if the file is not present in graylist or whitelist
```
Q: What does all this discussion mean?

A: It means that if you have large amount of space of your server, you can force players to use only that specific mods and that specific version of mods, and they must be equal bit by bit throught the hash SHA-256 verification. This can be perfect for servers that shares a must have modpack.


---

# 👑 OP Bypass System and Admin Abuse Checks


Server operators can optionally bypass mod and packs verifications.

Useful for:

* Administration
* Development
* Testing
* Emergency maintenance
* Civil Respect and Transparency with the Community by alert when someone uses a command. No restriction on who uses the command. You can choose the commands that sends an alert in Discord.

The OP bypass does **not** bypass:

```json
"block-pack-change": true
```

So resource-pack changes will remain blocked even for operators.

### 📢 Make administration visible

Every bypass event can be logged and sent to Discord.

You can also track administrative commands such as:

- `/gamemode`
- `/give`
- `/effect`
- `/recipe`
- and any other configured command you want to log to Discord.

This makes it possible to create a transparent community channel where administrative activity can be monitored through Discord Webhooks for the entire community.

---

## 📊 Statistics

Defixus stores persistent statistics globally and per player.

Statistics can be used for administration, monitoring and QoL Discord alerts, and can also be accessed through in-game admin commands.

### 🌍 Global Statistics

Tracked automatically:

| Metric |
|---|
| 👥 Total Players Verified |
| ✅ Successful Verifications |
| ❌ Failed Verifications |
| 🦶 Total Kicks |
| 🚫 Illegal Mods Detected |
| 🧬 Modified Mods Detected |
| 🎨 Resource Pack Violations |
| 👑 OP Bypass Events |
| 🖥️ Server Sessions |

### 👤 Player Statistics

Every player can have an individual security profile:

| Metric |
|---|
| 📅 First Seen |
| 🕐 Last Seen |
| 🔗 Connection Count |
| ✅ Successful Joins |
| ⏱️ Total Play Time |
| ⌛ Session Duration |
| 🦶 Kick History |
| 🚫 Illegal Mod Detections |
| 🎨 Resource Pack Violations |
| 👑 OP Bypass Usage |

### 📡 Supported Events and Discord Webhook Alerts

| Event | Unique Discord Webhook URL |
|---|:---:|
| ✅ Player Verified | ✅ |
| ❌ Verification Failed | ✅ |
| 🦶 Player Kicked | ✅ |
| 🚫 Illegal Mod | ✅ |
| 🧬 Modified Mod | ✅ |
| ❓ Missing Mod | ✅ |
| 🎨 Resource Pack Violation | ✅ |
| 🔄 Resource Pack Changed | ✅ |
| 🛡️ Anti-Cheat Tampering | ✅ |
| 👑 OP Join | ✅ |
| 🔐 OP Permission Change | ✅ |
| 📊 Statistics Events | ✅ |
| ⚙️ Configuration Reload | ✅ |
| 🟢 Server Startup | ✅ |
| 🔴 Server Shutdown | ✅ |
| 📜 Customizable command Execution  | ✅ |


---

# ⚙️ A detailed walkthrough on Defixus configurations

Defixus configuration is stored under `config/Defixus-anticheat/`:

```text
Defixus-anticheat/
├── verification/
│   ├── settings.json
│   ├── mod_whitelist.json
│   ├── mod_blacklist.json
│   ├── pack_whitelist.json
│   ├── pack_blacklist.json
│   ├── graymods/
│   └── graypacks/
├── discord/
│   └── webhook.json
├── console/
│   └── discord-webhook.json
└── statistics/
    ├── global.json
    └── players/
        └── <uuid>.json
```

## Discord webhooks

`discord/webhook.json` has a global `enabled` switch and per-event enable flags and URLs. A notification is sent only when the global switch and that event's enable flag are `true`; events use their configured URL, while command alerts can use either a per-command URL or the general command-dispatch URL. The same webhook URL can be used for multiple events or commands.

```json
{
  "enabled": false,
  "fancy-webhooks": false,
  "command_tracking": {
    "enabled": true,
    "commands": {
      "gamemode": "https://discord.com/api/webhooks/...",
      "give": "https://discord.com/api/webhooks/...",
      "effect": "",
      "recipe": ""
    }
  },
  "events": {
    "player_join": {"enabled": true, "url": ""},
    "operator_join": {"enabled": true, "url": ""},
    "operator_change": {"enabled": true, "url": ""},
    "command_dispatch": {"enabled": true, "url": ""},
    "player_kick": {"enabled": true, "url": ""},
    "mod_warnings": {"enabled": true, "url": ""},
    "pack_warnings": {"enabled": true, "url": ""},
    "pack_changes": {"enabled": true, "url": ""},
    "server_start": {"enabled": true, "url": ""},
    "server_stop": {"enabled": true, "url": ""}
  }
}
```

Discord webhook messages use the server language configured as `language` in `verification/settings.json`, including after `/defixus reload`. The former `language` value in `discord/webhook.json` is ignored; it is removed the next time that file is saved. Translation resources use `assets/defixus/lang/<locale>.json`, and missing translations fall back to English. `fancy-webhooks` defaults to `false`, it simply makes the webhooks full of statistical things to just decorate them. For most of you this can be just false, as it will omit player statistics and hashes of mods. Set it to `true` to include those things.

Command alerts are sent only if `enabled`, `command_tracking.enabled`, and `events.command_dispatch.enabled` are all `true`, and the executed command name appears in `command_tracking.commands`. Set a command's value to its own webhook URL to route it separately. An empty value uses `events.command_dispatch.url`. Add or remove command keys to control which commands are tracked. Existing configurations using the old command-name array are automatically migrated to entries with empty URLs, so each existing command continues to use the general command-dispatch URL. Configuration changes are loaded at server startup.

## Runtime console forwarding

The console-to-Discord integration has its own configuration and lifecycle; it does not use or change the anti-cheat event settings above. Configure:

```text
config/Defixus-anticheat/console/discord-webhook.json
```

```json
{
  "enabled": false,
  "webhook-url": ""
}
```

Set `enabled` to `true` and provide an HTTPS Discord webhook URL (`discord.com` or `discordapp.com`). While a server is running, Log4j messages at `INFO` level and above from Minecraft and loaded mods are forwarded, including warning/error details and stack traces; `DEBUG` and `TRACE` events are excluded. Messages are grouped into fenced `text` code blocks and sent by a background worker, not the server thread. Forwarding is limited to one Discord message every two seconds; oversized output is split, the in-memory queue is bounded, and any dropped lines are reported in a later batch. The webhook is not loaded by `/defixus reload`; restart the server after changing this file.

Console forwarding can include usernames, chat or command-related log details, file paths, and exception data emitted by any installed mod. Send it only to a private channel whose audience is authorized to see server logs. Server startup messages emitted before the server lifecycle starts are not included.

## General settings

`verification/settings.json` controls the server's client verification options:

```json
{
  "config-version": 1,
  "language": "en_us",
  "library-bypass": true,
  "block-pack-change": false,
  "kick-unapproved-mods": false,
  "kick-unapproved-packs": false,
  "unapproved-mod-warning": "",
  "unapproved-pack-warning": ""
}
```

- `config-version` is the integer schema version. Current version is `1`. Existing files without the field are interpreted as version `0` and migrated to `1` when loaded. This version does not represent the Defixus mod release version.
- `language` is the server's default language for Defixus messages. Supported values are `en_us`, `it_it`, `es_es`, `de_de`, and `fr_fr`. Default: `en_us`. Each connected client can select a separate language for messages shown to that player. The client infact can choose in which language the messages from the server will appear from its POV, and that will override the server language. The server language is used for Discord webhook messages by the way.
- `library-bypass` allows recognized library/dependency mod IDs without adding them to the mod whitelist. Default: `true`.
- `block-pack-change` blocks the normal client resource-pack selection interface and ignores reported changes while enabled. Default: `false`.
- `kick-unapproved-mods` kicks players for mods not in the mod whitelist or graylist, treating them as prohibited mods. Recognized libraries still follow `library-bypass`; graylisted mods with mismatched hashes are already rejected. Default: `false`.
- `kick-unapproved-packs` kicks players for resource packs not in the pack whitelist or graylist, treating them as prohibited packs. This applies during join verification and when an unapproved pack is activated in-game; removing a pack does not trigger this option. Graylisted packs with mismatched hashes are already rejected. Default: `false`.
- `unapproved-mod-warning` replaces only the mod-warning sentence shown before the unapproved mod names. If missing or blank, the built-in sentence is translated using the client's selected language.
- `unapproved-pack-warning` replaces only the pack-warning sentence shown before the unapproved pack names. A nonblank value is shown verbatim, even if it is identical to the old default English sentence, and is never replaced by a translation selected by an individual client. Leave it blank to use the localized built-in message. This is indeed, as unapproved mod warning, a warning that is shown to the player when he has unapproved mods or packs. You can customize it to your liking, but if you leave it blank, the default message will be used and translated in the language of the client as said before.

`mod_whitelist.json` and `mod_blacklist.json` contain mod IDs. `pack_whitelist.json` and `pack_blacklist.json` contain pack names; pack rules may end in `*` to match a prefix. Built-in whitelist entries are always included. Blacklisted entries and graylist hash mismatches are rejected; unlisted mods and packs warn by default and are rejected when their corresponding `kick-unapproved-mods` or `kick-unapproved-packs` option is enabled.

Each client selects its own Defixus message language from the Defixus settings screen in Mod Menu (Cloth Config is required):

```json
{
  "language": "en_us"
}
```

The setting is stored in `config/Defixus-anticheat/client.json`. Available values are `en_us`, `it_it`, `es_es`, `de_de`, and `fr_fr`. It affects translated Defixus messages shown to that player only and does not change Minecraft's interface language. Nonblank server warning overrides are shown verbatim, independent of the client's language; blank warning settings use localized built-in text. The client sends its selected locale to the server as a preference for player-facing translated messages; the server does not send its own locale to the client. The server language in `verification/settings.json` is also used for Discord webhook translations.

To add another language, please, open an issue and I will add it for you.

## Migration

Defixus moves legacy `verification/config.json`, `statistics.json`, and `players/<uuid>.json` files to the current locations without overwriting a file already present at the destination. A legacy Discord webhook config is converted to the event-based structure while preserving its URLs, event flags, and command list. The old verification settings format has no `config-version` field and is migrated from version `0` to version `1`.


> 💾 **Always back up your configuration directory before updating, and DO NOT touch the internal versioning migration parameter "config-version".**


---

# 🚀 Installation

## Common mod requirements (both Server and Client)

* Fabric Loader
* Fabric API
* Java 25
* Mod Menu
* Cloth Config
## Setup

### Server


1. Install a Fabric server and launch it once to generate the `mods/` folder
2. Enable EULA in `eula.txt` by changing `eula=false` to `eula=true`
3. Place the [common mod requirements](#common-mod-requirements-both-server-and-client) inside the `mods/` folder.
4. Start the server
5. Configure verification settings, take a look at the [configuration section](#-a-detailed-walkthrough-on-defixus-configurations) for more information.
6. Restart or reload

### Client

Players must install the [common mod requirements](#common-mod-requirements-both-server-and-client) and put them inside the `mods/` folder, alongside the approved mods defined by the admins.


---

# ⚠️ Security Notice and Goals of this Mod

Defixus is designed to detect:

✅ Unauthorized Mods

✅ Modified Mods

✅ Tampered Clients

✅ Resource Pack Violations

✅ Resource Pack Runtime Changes

✅ Integrity Mismatches

✅ Anti-Cheat Modifications

While no client-side verification system can guarantee absolute security, Defixus significantly increases the difficulty of using modified or unauthorized clients.
However, having Defixus does not mean having the best. You should use also a Runtime anticheat like Vulkan or others to decrase even more the probabilities of allowing hacked clients.

---

# 🏗️ Technical Details & Supported Versions


| Detail                | Value          |
| ------------------------ | --------------- |
| Minecraft Version        | 1.21.11 (Depracated), 26.1.x, 26.2, 26.3            |
| Loader                   | Fabric          |
| Java Version             | 25              |
| Hash Algorithm           | SHA-256         |
| Networking               | Custom Payloads Client <-> Server |
| Statistics               | Persistent      |
| Discord Integration      | Webhooks Only        |
| Resource Pack Monitoring | Real-Time       |

### Minecraft version 1.21.11 will not receive any kind of support when 27.1 will come out.
#### Defixus is designed to work with the latest versions of Minecraft and Fabric, and older versions may not be compatible or secure, as Mojang is fixing so many bugs in lastes 26.x versions, so I won't update them anymore.


---

# ❤️ Support

If you enjoy Defixus:

⭐ Star the project on GitHub

📥 Download on Modrinth

🐛 Report bugs on GitHub

💡 Suggest features as issues on GitHub or on my Discord Server

🤝 Contribute ideas as issues on GitHub or on my Discord Server

---

<div align="center">

# 🛡️ Defixus

### Trust Through Verification

Secure • Lightweight • Transparent

Made with ❤️ for the Minecraft Fabric Community.

</div>
