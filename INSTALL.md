# Установка Seed

Последняя версия — на странице [Releases](https://github.com/Izurika-rizuyo/seed/releases/latest).

| Система | Файл |
|---|---|
| macOS (Apple Silicon) | `Seed-<версия>-mac-arm64.dmg` |
| Windows x64 | `Seed-Setup-<версия>-win-x64.exe` |

Устанавливать нужно один раз. Дальше Seed обновляется сам: «Настройки → Платформа → Обновления → Проверить обновления».

## macOS

1. Откройте `.dmg` и перетащите **Seed** в «Программы».
2. Запустите Seed.

### «Файл „Seed“ не был открыт»

Seed пока не подписан сертификатом Apple Developer ID, поэтому при первом запуске macOS показывает окно «Apple не удалось подтвердить, что файл „Seed“ не содержит вредоносного ПО». Нажмите **«Готово»** — не «Переместить в Корзину» — и разрешите запуск одним из способов.

**Через Настройки**
1. «Системные настройки» → «Конфиденциальность и безопасность».
2. Внизу, у строки «Приложение „Seed“ заблокировано…», нажмите **«Всё равно открыть»**.
3. Подтвердите паролем или Touch ID.

Кнопка появляется в течение часа после попытки открыть приложение. В новых версиях macOS правый клик → «Открыть» это окно больше не обходит.

**Через Терминал**

```bash
xattr -dr com.apple.quarantine /Applications/Seed.app
```

Команда снимает с приложения отметку «скачано из интернета». Если Seed лежит в другой папке, подставьте её путь.

Разрешить нужно один раз: обновления через «Проверить обновления» приходят внутрь уже разрешённого приложения.

## Windows

1. Запустите `Seed-Setup-<версия>-win-x64.exe`.
2. Если появится «Windows защитила ваш компьютер» (SmartScreen), нажмите **«Подробнее» → «Выполнить в любом случае»**. Окно появляется, потому что установщик пока не подписан сертификатом разработчика.
3. Seed появится в меню «Пуск» и на рабочем столе.

## Переход с Keelson или Hub Desktop

Keelson и Hub Desktop — прежние названия Seed. Для системы это другое приложение, поэтому обновлением его не переименовать: Seed нужно установить заново. Данные при этом сохраняются.

| Что | Где хранится | При переустановке |
|---|---|---|
| Чаты, документы, знания, плагины проекта | папка проекта (`.hub/`) | не затрагиваются |
| Список проектов, входы агентов, библиотека плагинов, обновления | `~/.config/hub-local` | общие для старой и новой версии |
| Ключи и секреты | хранилище Seed | сохраняются |
| Настройки интерфейса (тема, вид, язык) | профиль приложения | Seed копирует их из Keelson / Hub Desktop при первом запуске |
| Входы Claude Code, Codex | сами эти программы | не затрагиваются |

Порядок:

1. Полностью закройте Keelson (⌘Q на Mac, «Выход» в трее на Windows), чтобы профиль скопировался целиком.
2. Установите Seed по шагам выше и запустите его.
3. Проверьте, что на месте проекты, чаты и настройки.
4. Удалите старое приложение (`Keelson.app` из «Программ» или `~/Applications`, ярлык из Dock). Папку `~/Library/Application Support/Keelson` (Windows: `%APPDATA%\Keelson`) стоит оставить на пару недель как запасную копию.

Заново может понадобиться только разрешить доступ к папкам и связке ключей.

## Обновления

- **Обычно:** «Настройки → Платформа → Обновления → Проверить обновления» → «Скачать» → «Установить». Seed проверяет подпись канала, размер и SHA-256 файла. Вернуться на предыдущую версию можно там же.
- **Без интернета или со старой версии (до 0.2.2):** скачайте `Seed-update-<версия>-<система>.seedupdate` своей системы со страницы выпуска и выберите «Установить из файла».
- **Если нужен новый Electron:** Seed предложит скачать установщик вместо файла обновления.

---

# Installing Seed (English)

Download from [Releases](https://github.com/Izurika-rizuyo/seed/releases/latest): `Seed-<version>-mac-arm64.dmg` (macOS, Apple Silicon) or `Seed-Setup-<version>-win-x64.exe` (Windows x64). After that Seed updates itself via **Settings → Platform → Updates → Check for updates**.

- **macOS, "Seed" was not opened:** Seed is not yet signed with an Apple Developer ID. Click **Done** (not Move to Trash), then open **System Settings → Privacy & Security** and click **Open Anyway**, or run `xattr -dr com.apple.quarantine /Applications/Seed.app`. Needed once.
- **Windows SmartScreen:** click **More info → Run anyway**.
- **Coming from Keelson / Hub Desktop:** quit the old app, install Seed, check your projects, then delete the old app. Projects, chats, documents, plugins, keys and the project list are kept; interface settings are copied on first launch.
