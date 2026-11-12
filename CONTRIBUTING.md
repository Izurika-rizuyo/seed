# Offering a plugin

1. In Seed, open **Settings → Plugins → In project** and use **Download** on your plugin — you get `<id>-v<n>.seedplugin`.
2. Fork this repository and add:
   - `plugins/<id>/<id>-v<n>.seedplugin`
   - an entry in `plugins/index.json`:
     ```json
     { "id": "<id>", "kind": "plugin", "name": "Name", "version": "1.0.0", "author": "you",
       "description": { "en": "One sentence.", "ru": "Одно предложение." },
       "tags": ["…"], "file": "<id>-v<n>.seedplugin", "minSeed": "0.2.2" }
     ```
   Leave `index.json.sig`, `url`, `sha256` and `size` as they are — the maintainer fills them in.
3. Open a pull request: what the plugin does, which rights it asks for (`network.fetch`, `embed`, hooks) and why.

The maintainer reviews the plugin, merges it and re-signs the catalog (`node scripts/seed-channel.mjs catalog` in the Seed sources). Until then Seed does not offer it: an unsigned or changed catalog is ignored.

## Предложить плагин

Скачайте плагин из Seed («Плагины → В проекте → Скачать»), добавьте файл в `plugins/<id>/` и запись в `plugins/index.json` (без `url`, `sha256`, `size` и подписи), откройте pull request с описанием и правами плагина. После проверки сопровождающий принимает его и переподписывает каталог — только тогда плагин появится в Seed.
