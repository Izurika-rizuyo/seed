# Seed — official channel

Public channel of the [Seed](https://github.com/Izurika-rizuyo/seed/releases) desktop app: releases, the update feed and the plugin catalog.

| File | What it is |
|---|---|
| `channel.json` + `.sig` | The latest release: version, notes and, per system, the update file (`.seedupdate`) with size and SHA-256 and the installer. Seed reads it on **Check for updates** and once a day. |
| `plugins/index.json` + `.sig` | The plugin catalog shown in **Settings → Plugins → Catalog**. |
| `plugins/<id>/<id>-v<n>.seedplugin` | Plugin files listed in the catalog. |

Both JSON files are signed with the maintainer's Ed25519 key. Seed ships only the public key and installs nothing whose signature, size or SHA-256 does not match.

## Install

Download from [Releases](https://github.com/Izurika-rizuyo/seed/releases/latest):

- **macOS (Apple Silicon):** `Seed-<version>-mac-arm64.dmg`
- **Windows (x64):** `Seed-Setup-<version>-win-x64.exe`

After that, Seed updates itself from this channel: **Settings → Platform → Updates → Check for updates**.

## Changelog

See [CHANGELOG.md](CHANGELOG.md).

## Plugins

The **Design Workflow** pack (Brief, Decisions, Sitemap, Documents) is built into Seed. Other plugins come from this repository — see [CONTRIBUTING.md](CONTRIBUTING.md) to offer yours.

---

# Seed — официальный канал

Выпуски, лента обновлений и каталог плагинов Seed. Установщики — в [Releases](https://github.com/Izurika-rizuyo/seed/releases/latest); дальше Seed обновляется сам: «Настройки → Платформа → Обновления → Проверить обновления». Плагины — «Настройки → Плагины → Каталог». Как предложить свой плагин — [CONTRIBUTING.md](CONTRIBUTING.md).
