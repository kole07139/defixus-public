# Changelog

All notable changes to this project are documented here, following [Keep a Changelog](https://keepachangelog.com/en/1.0.0) and [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Released sections describe their historical artifacts.

## [Unreleased]

### Added

### Changed

### Fixed

### Removed

## [1.1.0-beta.1] - 2026-10-18

### Added

- **NeoForge and Quilt support**
- **Mustlist** preparation before world entry for required mods and active ZIP/directory packs, consented downloads, server-specific pack selection and a post-exit installer with backups and rollback attempts.
- **Version-specific Checklist/Mustlist** mod-reference folders and target-aware multiplayer badges. Flat references, pack references and global lists remain supported.
- **Modrinth update checker through Mod Menu for Fabric/Quilt**
- Brazilian Portuguese and Russian message languages support.
- **Discord Bot for a two-way console**, slash commands, explicit user/role authorization, public command transcripts and runtime log forwarding. Disabled by default. The old one-way console with Webhooks dispach is kept for admin abuse purposes for communities that wants to share the console with their community.
- Multiplayer badges with QoL information.
- In-game settings panel with the `defixus:panel.editor` permission with `/dp` shortcut for the new `/defixus panel` command.
- Separate join/pack-change bypass, scan, download and statistics permissions and the brand new `/defixus download <player> mods|packs|mod|pack|unapprovedmods|unapprovedpacks` commands.
- Paginated reports for rule lists, scans, statistics and download summaries.
- Native `/defixusclient` language settings without optional UI mods.
- Stonecutter source for Minecraft 1.21.11, 26.1.x (26.1, 26.1.1, 26.1.2), 26.2 and 26.3.
- Protocol 2 release/loader/target negotiation before resource manifests, with cross-version Defixus support when Minecraft protocol translation is provided externally. Fabric/Quilt and NeoForge connections remain separate.
- Native Quilt JSON/JSON5 and NeoForge TOML/JarJar dependency preflight, including multi-mod files and provided IDs.
### Changed

- Reverted Minecraft **1.21.11 Active Support**.
- **Renamed Whitelist / Graylist / Blacklist to Allowlist / Checklist / Denylist**, preserving legacy permission/ping/translation/statistics identifiers and backing up migrated list files.
- **Mod Menu and Cloth Config are just suggested as client enhancements for clients** rather than required dependencies for both server and client.
- Replaced the former `/defixus scan mods|packs` rule-reload behavior with `/defixus scan <player> mods|packs` client inspection. `/defixus reload` remains the verification reload command.
- Fabric loader was raised at `0.19.5+` for every Fabric/Quilt build.
- Split server and client source sets.
- Read the release version from shared generated build metadata and separated client/server rank-token files from resource-consent profiles.

### Fixed

- Limited bold formatting in kick messages and removed repeated kick-reason presentation from webhooks titles.
- Fixed event-webhook creation and panel persistence on Windows by closing reads before saving and using atomic UTF-8 replacement; retained legacy migrations, invalid-input backups and failed-toggle rollback.
- Hashed nested Fabric JARs through their parent container, including canonical Defixus fingerprints on virtual archive paths; unknown/inaccessible origins remain in verification as `UNAVAILABLE` without unsupported-origin exceptions.
- Closed statistics readers before deleting expired records and counted only successful deletions, fixing Windows startup/command cleanup.
- Prevented duplicate kick notifications
- Retained session statistics until disconnect/shutdown, classified verification kicks by stable error codes and tied ordinary verification callbacks/timeouts to the current connection.
- Kept server schedulers/IO workers within the server lifecycle and explicitly rehashed changed pack ZIPs during scans.
- Reported Fabric-registered mods, including launcher-managed/nested entries, instead of relying only on files directly inside `mods/`; unreadable origins remain reported as errors.

## [1.1.0-alpha.1] - 2026-10-03

### Added

- Minecraft 26.3 support.
- Client-selectable Defixus message languages (`en_us`, `it_it`, `es_es`, `de_de`, and `fr_fr`) through the Mod Menu settings screen. Open an issue to request additional languages.
- Suggestion from [Issue #4]: Add a config that kicks players if they have mods or packs which aren't on the server. Optional automatic kicks for unapproved mods and resource packs (with configurable warning text, as a Discord suggestion was made for this).
- **Discord Alerts**: Event-specific Discord webhook settings, Minecraft per-command dispatch webhooks, simplified discord alert format as default.
- **Console forwarding to discord**.

### Changed

- Fabric Loader was raised from `0.19.2+` to `0.19.3+` for the `26.1` and `26.2` builds; the `26.3` port requires `0.19.5+` and the deprecated `1.21.11` port requires `0.18.5+`.
- **Marked as Deprecated the Minecraft 1.21.11 support**, with the announcement of The Sift coming to vanilla, i will deprecate most Minecraft versions old support. I plan to maintain Minecraft 1.21.11 deprecated support also for 27.1.
- Cross-version Defixus fingerprints are now hard-coded in source instead of generated/read from a server config file.
- Discord alerts and player-facing verification messages use configured languages; legacy Discord and verification settings are migrated to the new formats. The client will be able to see messages in their selected language, and Discord alerts will be sent in the server's configured language. This will not apply to custom messages the server operator has configured.
- Statistics and player records are stored in organized subdirectories, with migration from the previous file locations and expanded kick-reason and violation reports with the fancy-webhook option enabled.
- **Cloth Config and Mod Menu are now required dependencies** for the client language settings screen. As it is both a client and server mod, the server will also require these dependencies to be installed.

### Removed

- Generation and loading of `verification/defixus_version_hashes.json`; cross-version hashes are maintained in source instead.
- Lot of obsolete code.

### Fixed

- Verification hash caches are cleared on reload, directory hashes use normalized relative paths, and read failures no longer produce partial hashes.
- Player disconnect/server-stop statistics and kick-reason categorization are recorded consistently.


## [1.0.5] - 2026-07-11

### Added

- **Geyser/Floodgate** support: optional support is automatically enabled when the server loads Geyser / Floodgate in order to skip client verification for Bedrock users. **Note that this is built upon Geyser API, so a client can't just spoof his client brand.**

### Fixed

- [Issue #3] - Game crashes on launch when using Defixus 1.0.4 (Mixin ButtonMixin not found)


## [1.0.4] - 2026-07-06

### Fixed

- [Issue #2] - No Join/Leave messages.

- [Issue #1] - Warning won't go away no matter what I do: solved totally.


## [1.0.3] - 2026-06-20

### Fixed

- [Issue #1] - Warning won't go away no matter what I do: solved partially.

## [1.0.2] - 2026-06-20

### Added


- Minecraft 1.21.11 support rolled back as was requested. Now Minecraft 1.21.11 onward are supported.
- Cross versions communication with Defixus. Your client can be different version than the server, but you need to have the same Defixus version.

## [1.0.1] - 2026-06-16

### Added


- Minecraft 26.2 support.

- GitHub issue report and suggestion page.

### Removed

- Minecraft 1.21.11 and earlier versions support.

### Fixed

- Reload Screen Resource Pack Change Server-Side Blocking feature is not working.

## [1.0.0] - 2026-06-03

### Added

- Minecraft 1.21.4-26.2-pre.3 support.

- Java 25 or newer is required.

- Base mechanics of Defixus mod. Client verification, mod and resource-pack whitelists/blacklists, Discord webhooks, and statistics.


[Unreleased]: https://github.com/kole07139/defixus/compare/stable/26.3/1.1.0...HEAD
[1.1.0-beta.1]: https://github.com/kole07139/defixus/compare/26.3/1.1.0-beta.1...HEAD
[1.1.0-alpha.1]: https://github.com/kole07139/defixus/compare/26.3/1.1.0-alpha.1...HEAD
[1.0.5]: https://github.com/kole07139/defixus/compare/26.2/1.0.5.../26.2/1.1.0
[1.0.4]: https://github.com/kole07139/defixus/
[1.0.3]: https://github.com/kole07139/defixus/
[1.0.2]: https://github.com/kole07139/defixus/
[1.0.1]: https://github.com/kole07139/defixus/
[1.0.0]: https://github.com/kole07139/defixus/


[Issue #1]: https://github.com/kole07139/defixus-public/issues/1
[Issue #2]: https://github.com/kole07139/defixus-public/issues/2
[Issue #3]: https://github.com/kole07139/defixus-public/issues/3
[Issue #4]: https://github.com/kole07139/defixus-public/issues/4
[Issue #5]: https://github.com/kole07139/defixus-public/issues/5
[Issue #6]: https://github.com/kole07139/defixus-public/issues/6
[Issue #7]: https://github.com/kole07139/defixus-public/issues/7
[Issue #8]: https://github.com/kole07139/defixus-public/issues/8
[Issue #9]: https://github.com/kole07139/defixus-public/issues/9
[Issue #10]: https://github.com/kole07139/defixus-public/issues/10
