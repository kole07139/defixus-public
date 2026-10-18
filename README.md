<div align="center">

# 🛡️ Defixus: Anti-Cheat and QoL Admin Tool

### 🔒 The Ultimate Anti-Cheat Mod with Integrity Protection 🔒

Detect unauthorized resources • Verify file integrity • Monitor live changes • Resource hash analysis • Protect your community

![built-java25](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact-minimal/built-with/java25_vector.svg)
[![website](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/documentation/website_vector.svg)](https://github.com/kole07139)
[![github](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact-minimal/available/github_vector.svg)](https://github.com/kole07139/defixus-public)
[![modrinth](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact-minimal/available/modrinth_vector.svg)](https://modrinth.com/mod/defixus)
[![discord-singular](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact-minimal/social/discord-singular_vector.svg)](https://discord.gg/mZxXk3fC3w)
[![kofi-singular-alt](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/donate/kofi-singular-alt_vector.svg)](https://ko-fi.com/kole07139)

![minecraft-support](https://img.shields.io/badge/Minecraft-1.21.11%20%7C%2026.1.x%20%7C%2026.2%20%7C%2026.3-green)
![integrity-type](https://img.shields.io/badge/Integrity-SHA--256_Checksum-red)
![discordintegration](https://img.shields.io/badge/Discord_Integration-Webhooks_%26_Bot-5865F2)
![statistics](https://img.shields.io/badge/File_Transfer-Supported-blue)


---

### ⚡ 🔐 SHA-256 Verification & Client Inspector 🔐 ⚡

Defixus is a powerful anti-tampering and verification system for Fabric/Quilt and NeoForge servers, with lots of QoL features.

> A runtime-behavior anticheat is in development inside Defixus, consider help the project on Ko-fi


### Active Support: Minecraft 26.x and 1.21.11 | Geyser/Floodgate & ViaVersion/ViaBackwards authentication supported

![yes-fabric](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/supported/fabric_vector.svg)
![yes-quilt](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/supported/quilt_vector.svg)
![yes-neoforge](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/supported/neoforge_vector.svg)
![no-forge](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/unsupported/forge_vector.svg)


Unlike traditional "whitelist/blacklist" solutions with mod-id's, Defixus validates not only which mods are loaded, but also checks their integrity through SHA-256 checksum hashing and their behavior inspecting the binary files, ensuring that cheated, disguised or tampered clients cannot bypass server security policies defined by Defixus.
Built for whether large or small communities that require a control over the client environment.

![fabric-api](https://cdn.jsdelivr.net/npm/@intergrav/devins-badges@3/assets/compact/requires/fabric-api_vector.svg)



</div>

---

# ✨ Features

Give whether your SMP or Community clear client rules, share the resources your community needs, and keep useful administration tools close at hand.

- 📦 **Mod and resource-pack rules** with Allowlist, Checklist, Denylist and Mustlist.
- 🔐 **SHA-256 integrity checks** for reference files and the Defixus client.
- ⬇️ **Required server resources**, prepared with the player's approval before entering the world.
- 🔎 **In-game client scans** and individual or bulk **client → server downloads**.
- 🎨 **Active resource-pack change reports** and an option to block normal pack selection.
- 🖥️ **An in-game settings panel**, paginated chat reports and multiplayer server-list indicators.
- 🤖 **A two-way Discord console**, using your own bot running inside Minecraft (optional one-way Webhook console too).
- 📡 **Discord event alerts**, including configured player-issued commands, using Webhooks.
- 📊 **Persistent server and player statistics**.
- 🌍 **Lot of client message languages**, used for alerts, kicks and more.


> 📚 Start with [installation](#-installation), or visit the [Defixus Wiki](WIKI/Home.md) for the complete guides.

---

# 🛡️ Why Defixus?

Running a community server often means answering a simple question: **which client resources belong here**?

Here's a table which answers this question. Its important to understand what here is called 📦 **resource** and what are the 📋 Lists.

- A 📦 **resource** is either a 🧩 **mod** or a 🎨 **resource pack**.

| 📋 List | A 📦 resource in this list means that |
|---|---|
|<div align="center"> 🟢 **Allowlist** </div> | “This resource is welcome to join the server.” No particular file build is required. Uses mod-id for mods and a normalized name for resource packs. |
|<div align="center"> 🟡 **Checklist** </div>| “If you use this resource, it **must match** the relative file bit-by-bit (SHA-256 Checksum), and if it doesn't match, then an automatic kick from the server.” |
|<div align="center"> 🔴 **Denylist** </div>| “This resource is prohibited.” Uses mod-id for mods and a normalized name for resource packs. |
|<div align="center"> 🔵 **Mustlist** </div>| “Everyone needs this exact mod or resource pack to be active.” It must match the same file, bit-by-bit (SHA-256 Checksum), and if it doesn't, the player can't join the server. Comes with a simple "Sync Mustilist with Server" button, so the clients do not need to install the Must-have resources manually. Perfect choice for 🗃️ Modpacks. |

- ⚪ **Allowed** resources: a resource which is present in 🟢 **Allowlist** and 🔵 **Mustlist**, or that is present in 🟡 **Checklist** and matches the file integrity with the server's correspondent resource, is marked as
⚪ **Allowed**.


- 🔘 **Unapproved** resources: a resource which is not present in 🟢 **Allowlist** and 🟡 **Checklist**, is marked as
🔘 **Unapproved**. An unapproved resource can be a ⚫ **Prohibited** one when the settings `kick-unapproved-*` are enabled.


- ⚫ **Prohibited** resources: a resource that is present in the 🟡 **Checklist** and does not match the file integrity, or that is present in 🔴 **Denylist**, is marked as ⚫ **Prohibited**, and comes with a kick.

A Checklist reference alone **does not** require players to install that resource. Use Mustlist when it must be present (Modpack oriented servers).

For ordinary mod rules, Denylist takes priority, followed by Allowlist or recognized libraries, then Checklist. Built-in Allowlist entries and pack exceptions also apply, so review the [verification rules](WIKI/Verification-and-Security.md) when setting up a strict modpack.

> In development also a runtime anti-cheat with high success rate, that is not based on 📦 **resources** but on behavior runtime checks (like Vulkan and so on). This is a work in progress, and it will be released in the next months. Consider [leave a tip on Ko-Fi](https://ko-fi.com/kole07139) to help this project.


---

# ⚡ Verification Flow

Defixus uses the client's reported loader mod inventory and selected resource packs.

```text
Connect to the server
         │
         ▼
Prepare Mustlist resources, if needed
Review → Approve → Download and check
         │
         ▼
Required mods loaded and packs active?
         │
         ▼
Enter the world and send the verification report
         │
         ▼
Defixus release → Integrity → Ordinary server rules
         │
    ┌────┴─────┐
    ▼          ▼
  Accepted   Rejected
  or warned  with an error code and kicked out
    │
    ▼
Report subsequent pack-selection changes + Runtime checks
```

Mustlist is checked before ordinary staff and permission bypasses. When mods need changing, the player closes Minecraft to apply them, then restarts through the launcher.

See the [verification guide](WIKI/Verification-and-Security.md) for exceptions and the limits of client reports.

---

# 🎨 Resource Pack Protection

Keep your community's resource-pack choices predictable.

| Feature | Available |
|---|---|
| Pack Allowlist, Checklist and Denylist | ✅ |
| Required, active Mustlist packs | ✅ |
| File and directory fingerprints | ✅ |
| Reports of changes through the normal pack screen | ✅ |
| Block normal in-game pack selection | ✅ |
| Kick for unapproved packs | Optional; off by default |

`block-pack-change` defaults to `true`. Owner, Moderator and explicit pack-change bypass users receive an exemption from the screen block. Required Mustlist packs still apply.

The block controls the normal client interface; it does not independently restore changes made outside that interface. See [pack-change behavior](WIKI/Verification-and-Security.md#resource-pack-changes).

---

# 🧑‍💻 What is Defixus ideal for?

- 🏡 **SMPs and small communities** that want understandable client rules.
- 🧩 **Curated modpacks** with required mods and optional approved additions.
- 🏰 **RPG and economy servers** with shared visual resources.
- 🎪 **Private events** that need consistent player setups.
- 👮 **Staff teams** that want inspection tools, reports and visible administration.

---

# ⚙️ Server admin explanation and setup

All verification paths below are relative to `config/Defixus-anticheat/verification/`.

## 🟢 Allowlist: allow by identifier

Add mod IDs to `mod_allowlist.json` and pack names to `pack_allowlist.json`. These files contain JSON arrays:

```json
["sodium", "iris"]
```

Allowlist entries accept an identifier without enforcing a version or file hash. Built-in entries are always included, and `library-bypass` allows recognized library IDs by default.

## 🟡 Checklist: approve an exact optional file

Put reference mod JARs in `checklist/mods/` and resource-pack ZIPs or directories in `checklist/packs/`.

If a player reports that resource, and it reaches the Checklist check, its hash must match the reference. Missing optional resources are fine unless the option `kick-unapproved-*` is enabled.

> ⚠️ For an exact Checklist comparison, review overlapping Allowlist entries and the library bypass. Allowlist approval happens first, so do not put the same mods in more than one list!

## 🔴 Denylist: prohibit a resource

Add prohibited IDs or pack names to `mod_denylist.json` or `pack_denylist.json`. Both start empty.

Denylist takes priority within ordinary list checks. Staff bypasses and the earlier system/mod-provided pack exceptions have their own behavior; the [wiki](WIKI/Verification-and-Security.md#policy-precedence) describes the full order.

## 🔵 Mustlist: resources everyone needs

Want players to use your community's required mod or pack?

1. Put required mod JARs for your loader in `mustlist/mods/`, or its `1.21.11/`, `26.1.x/`, `26.2/` and `26.3/` subfolders for different client versions.
2. Put required pack ZIPs or directories in `mustlist/packs/`.
3. Run `/defixus reload`.

> 💡 Players can prepare the must-have resources just by **Joining** the server, or click on the icon **↓** next to the server's name in the multiplayer list. The server's multiplayer indicators prepare the client before entering the server world.

When mods need changing, whether different not present or the integrity is corrupted, players choose **Download** and then **Close Minecraft and apply**. Eventual replaced files are backed up; launcher-managed or nested installed mods may need a manual update.

**Mustlist applies to Java staff too.** It requires a minimum set; additional resources follow ordinary rules. A changed Mustlist requests fresh reports from online Java players after reload and **disconnects those who no longer meet it**.

See [player preparation](WIKI/Installation.md#required-server-resources) and [server setup and limits](WIKI/Server-Configuration.md#mustlist).

> ⚠️ Checklist and Mustlist support common mod references plus **client-version overrides**. For example, `verification/mustlist/mods/26.1.x/` selects required files for all three 26.1 patches. Pack references and Allowlist/Denylist stay shared. See [versioned references](WIKI/Server-Configuration.md#version-specific-mod-references).

## 👑 Staff permissions

Ordinary join verification has automatic bypasses for the exact **Owner** and **Moderator** permission sets, after the matching Defixus release check. Separate permission nodes can skip mod or pack checks.

These bypasses do not exempt anyone from Mustlist. Owner and explicit pack-change permission users also skip ordinary pack-change verification; Moderator alone only receives the screen-block exemption.

See the [permission guide](WIKI/Permissions.md) for the precise rules.

## 📥 Inspect and download client resources

Authorized staff can inspect an online player's downloadable mod inventory and installed packs:

```text
/defixus scan <player> mods
/defixus scan <player> packs
```

Reports include hash details on hover and a clickable **Download** action when permitted. Downloads can also be requested directly:

```text
/defixus download <player> mod <mod-id>
/defixus download <player> pack "Pack Name.zip"
/defixus download <player> mods
/defixus download <player> packs
/defixus download <player> unapprovedmods
/defixus download <player> unapprovedpacks
```

These commands require an in-game staff player and a compatible online target. Files are saved under `config/Defixus-anticheat/downloads/<player-uuid>/`; they are not installed automatically. Each file is limited to **256 MiB**, and pack folders are transferred as ZIPs.

Bulk downloads show progress and per-file failures. Nested mods and the Java runtime entry are excluded from the downloadable mod inventory. The `unapproved*` filters use ordinary Allowlist/library and Checklist approval, with Denylist taking priority; they do not consult Mustlist approval.

## 📊 Read useful reports

```text
/defixus list mods
/defixus list packs
/defixus stats global
/defixus stats player <player>
/defixus panel
```

In-game reports use **eight rows per page**, private navigation and five-minute expiry. The console receives full plain-text output for commands available to console sources.

Scan, statistics, download and panel commands have separate access rules. Open the panel with `/dp` as a shortcut. See [commands and statistics](WIKI/Commands-and-Statistics.md).

---

# 🤖 Discord Integration

## Console sharing (Discord Bot or Webhooks)

Your own bot turns one Discord text channel into a shared Minecraft console. Authorized users send slash commands; everyone who can read the channel sees the author, command, response and forwarded runtime logs.

```text
/defixus console command:list
/defixus console command:defixus list mods
/defixus status
```

The bot runs **inside Minecraft**. Create your own Discord application, keep its token locally on the server, configure allowed users or roles, and restart. No separate bot program, Docker or VPS is needed.

Authorized commands have full console permissions. Commands that require a player entity still need to be run in game.

Eventually, you can setup a **one-way Minecraft to Discord** console with webhooks, just to dispatch it in a public discord channel (to pursue the anti admin abuse checks).


> 📖 Follow the [Discord Integration guide](WIKI/Discord-Integration.md) for the webhook one-way configuration or for the application creation, token storage and setup of the two-way Discord Bot.


## Event alerts (Discord Webhooks)

Independent webhooks can send:

| Event | Notification |
|---|---|
| `player_join` | Successful ordinary verification |
| `operator_join` | Automatic Owner/Moderator join bypass |
| `operator_change` | Operator grants/removals through the hooked commands |
| `command_dispatch` | Configured player-issued commands |
| `player_kick` | Ordinary verification kicks |
| `mod_warnings`, `pack_warnings` | Unapproved-content warnings |
| `pack_changes` | Reported pack changes on applicable paths |
| `server_start`, `server_stop` | Server lifecycle alerts |

Configure destinations and switches in `discord/webhook.json`. `fancy-webhooks` adds available statistics and hash details. A separate one-way console webhook remains available when the personal bot is disabled.

---

# 📊 Statistics

Defixus keeps persistent global counters and individual player records.

| Server records | Player records |
|---|---|
| Checked reports and successful verifications | Name, UUID, first/last seen |
| Verification kicks and categorized detections | Connection, join and kick counts |
| Disconnects and staff join bypasses | Recent violations and last observed mod IDs |
| Server starts and stops | Stored play time, average session time and bypass use |

Reports show the supported counters and violation details; additional session data is stored in the player JSON files. Stored violation history keeps up to ten entries, and the player report displays up to five.

Player-statistics files older than **90 days since last seen** are eligible for startup cleanup and `/defixus cleanup`.

---

# ⚙️ A walkthrough on Defixus configurations

The main server files live under `config/Defixus-anticheat/`:

```text
Defixus-anticheat/
├── verification/
│   ├── settings.json
│   ├── mod_allowlist.json
│   ├── mod_denylist.json
│   ├── pack_allowlist.json
│   ├── pack_denylist.json
│   ├── checklist/
│   │   ├── mods/
│   │   └── packs/
│   └── mustlist/
│       ├── mods/
│       └── packs/
├── discord/webhook.json
├── console/
│   ├── discord-bot.json
│   └── discord-webhook.json
└── statistics/
    ├── global.json
    └── players/<uuid>.json
```

The default `verification/settings.json` is:

```json
{
  "config-version": 1,
  "language": "en_us",
  "library-bypass": true,
  "block-pack-change": true,
  "kick-unapproved-mods": false,
  "kick-unapproved-packs": false,
  "unapproved-mod-warning": "",
  "unapproved-pack-warning": ""
}
```

| Setting | What to expect |
|---|---|
| `library-bypass` | Recognized libraries can pass ordinary mod approval without individual entries. |
| `block-pack-change` | Blocks the normal pack screen for players without an exemption; ordinary reported changes are logged and ignored while blocked. Mustlist checks still apply. |
| `kick-unapproved-mods` | Reject unknown mods instead of warning. |
| `kick-unapproved-packs` | Reject unknown packs at join and on activation instead of warning. |
| `language` | Default server-message and Discord event language. |
| `unapproved-*-warning` | Blank uses translated warning text; nonblank text is displayed verbatim. |
| `config-version` | Internal configuration schema. Leave it unchanged. |

Denylist decisions and applicable Checklist mismatches already reject resources, independently of the unknown-content kick switches.

Run **`/defixus reload`** after editing verification rules or resources. Invalid replacement policies leave the previous active rules in place. Discord file changes require a server restart; panel switches are applied immediately when saving succeeds.

> 💾 Back up your configuration before updating. Legacy list paths migrate automatically with backups. The [server configuration guide](WIKI/Server-Configuration.md) contains examples, migrations and all data locations.

---

# 🚀 Installation

## Mod requirements

### Mandatory requirements

- For **Fabric and Quilt**, Fabric API is required. Any version should be fine. Both server and client.

- For **NeoForge** nothing is required. Both server and client.

### Optional client enhancements

- For **Fabric**: 
  <br>↳
    - **Mod Menu** opens Defixus settings from the mod list.
  - **Cloth Config** provides the enhanced settings screen through Mod Menu.

  <br>Both are optional. Without them, use **`/defixusclient`** to open the native language screen (it's a beta test setting screen, a better one in development)


- For **NeoForge**, just the **optional Cloth Config** is suggested for the same reason. The native screen and `/defixusclient` also work without it.

## Server setup

1. Install your loader and accept Minecraft's EULA.
2. Put [mod requirements](#mod-requirements) and Defixus in the server's `mods/` folder.
3. Start the server to generate configuration files.
4. Choose your lists and settings and load your files in mustlist and checklist, then run `/defixus reload`.
5. Share the matching Defixus release (the Defixus server version) and required setup with your players.

## Client setup

1. Install the [mod requirements](#mod-requirements), Defixus and consider download also [optional client enhancements](#optional-client-enhancements).
2. Join the server, or use **↓** to prepare its Mustlist resources.
3. Review requested downloads. If mods change, close Minecraft to apply them, then restart the same profile.

> Recognized Bedrock players, **authenticated with Geyser/Floodgate protocols** are exempt from the Java verification flow.

---

# ⚠️ Security Notice and Goals of this Mod

Defixus helps your community apply client-resource rules. Exact file checks can identify mismatches **in the inventory the client reports**.

A modified client **can always falsify that report**. Allowlist approval intentionally accepts identifiers without checking their bytes, you can still download them from the client to do a manual check. Defixus does not implement movement or combat analysis (at moment), and pack-screen blocking cannot prevent every local modification.


> A runtime-behavior anticheat is in development inside Defixus, consider help the project on Ko-fi

---

# 🏗️ Technical Details & Supported Versions

| Detail | Last version (1.1.0-beta.1) |
|---|---|
| Defixus version | `1.1.0-beta.1` |
| Minecraft targets | `1.21.11`, `26.1.x`, `26.2`, `26.3` |
| Platforms | Shared Fabric/Quilt JAR, separate NeoForge JAR |
| Java | 21 for `1.21.11`; 25 for `26.x` |
| Hash algorithm | SHA-256 |
| Networking | Minecraft configuration and play payloads |
| Discord | Event webhooks, personal two-way console, optional forwarding |
| UI additions | Mod Menu and Cloth Config are optional |

Cross-version Defixus connections use protocol **2**, a loader-family handshake and eight coordinated artifact fingerprints. Minecraft protocol translation must be provided separately (for example, a suitable ViaVersion/ViaBackwards/ViaFabric setup). Connections across Fabric/Quilt and NeoForge families are rejected. Old builds with the same release string but the previous protocol must be replaced.

See [compatibility and mappings](WIKI/DEV/Compatibility-and-Mappings.md) and the [changelog](WORK_DOCS/CHANGELOG.md) for build and release details.

---

# ❤️ Support

If you enjoy Defixus:

⭐ Star the project on GitHub

📥 Download on Modrinth

🐛 Report reproducible bugs on GitHub

💡 Share ideas on GitHub or in my Discord server

🤝 Help shape a better experience for your community

---

<div align="center">

# My Other Projects!

If you enjoy [Defixus Anti-Cheat], you may enjoy my other projects:


</div>

### [Builders Freecam] - (1.17 - 26.4)
A complete well shaped fork of [Freecam], which prevents Hack-like features such as traveling on "solid" blocks and lava, and cave-peeking.

### [Just Redstone Waterlog] - (1.14 - 26.4)
This Mod/Plugin extends all Bedrock Edition **Redstone** components waterloggable blocks into Java Edition.

### [Just Bedrock Waterlog] WIP - (1.14 - 26.4)
This projects extends **all Bedrock** Edition waterloggable blocks into Java Edition. Comes with a config too!

### [ViaAlert (ViaVersion Addon)] - (1.21.11 - 26.4)
It lets you see when people join into your Fabric server which version are they using, and which client they are from.

### [Expanded Redstone] - (1.21.11 - 26.4)
This mod allows redstone signals to propagate downwards over a non-conductor relay. A relay is a new block crafted with 4 vanilla block plus an amethyst shard.

### [Cobalt Age] - (1.21.11 - 26.4)
This is a more shaped technical mods, which adds a complete new energy system called **Cobalt Energy System**, which works parallelly to Redstone, being different in the fact that it is not compatible with redstone signals and that it is waterloggable, and even more features, such as an up to 60 power strength.




[Freecam]: https://modrinth.com/mod/freecam



[Builders Freecam]: https://modrinth.com/mod/buildersfreecam
[Defixus Anti-Cheat]: https://modrinth.com/mod/defixus
[ViaAlert (ViaVersion Addon)]: https://modrinth.com/mod/vva
[Just Redstone Waterlog]: https://modrinth.com/mod/jrw
[Just Bedrock Waterlog]: https://modrinth.com/mod/jrw
[Cobalt Age]: https://modrinth.com/mod/cobalt-age
[Expanded Redstone]: https://modrinth.com/mod/expanded-redstone

[Wiki]: https://github.com/kole07139/defixus-public/wiki
