# Ovygram Plugins — Python-плагины для Telegram Desktop

Официальный каталог плагинов **Ovygram** — неофициального клиента на основе
[Telegram Desktop](https://github.com/telegramdesktop/tdesktop) со встроенным
Python и Desktop Plugin SDK. Репозиторий предназначен для публикации
прошедших модерацию релизных версий плагинов для Windows и Linux.

Плагины расширяют сообщения, меню, интерфейс и рабочие сценарии Ovygram.
Для их запуска нужен клиент Ovygram: обычный Telegram Desktop не загружает
эти пакеты.

## Ссылки

- [Исходный код клиента Ovygram](https://github.com/Ovygram/Ovygram)
- [Документация Python SDK](https://github.com/Ovygram/Ovygram/blob/main/docs/guide.md)
- [Примеры плагинов](https://github.com/Ovygram/Ovygram/tree/main/tools/ovygram/examples)
- [Бот подачи плагинов — @OvygramApp](https://t.me/OvygramApp)
- [Индекс опубликованных плагинов](index.json)

## Установка и обновление

1. Найдите опубликованный пакет `.ovyplugin` или `.ovyzip` в каталоге
   `plugins/` либо по ссылке из [индекса](index.json).
2. Откройте файл в Ovygram или импортируйте его через **Настройки → Плагины**.
3. Проверьте описание, автора и системный статус в окне установки.
   После импорта плагин включается отдельно.

Если в `index.json` пока нет записей, опубликованных плагинов ещё нет.
Не создавайте каталоги или ссылки на несуществующие версии вручную.

## Для разработчиков плагинов

Создайте Python-плагин для Desktop SDK и отправьте готовый пакет
боту [@OvygramApp](https://t.me/OvygramApp). Для публикации в этом каталоге
укажите `__release__ = True`. После одобрения модератором сервер опубликует
точный проверенный файл и обновит индекс.

Исходники, метаданные, форматы пакетов и порядок подачи описаны в
[CONTRIBUTING.md](CONTRIBUTING.md). Пакеты публикуются сервером реестра;
pull request с файлом не заменяет модерацию.

## Структура каталога

```text
index.json
plugins/
  <plugin_id>/
    info.json
    <version>/
      <plugin_id>.ovyplugin
      # либо <plugin_id>.ovyzip
```

`index.json` содержит последние доступные версии. `info.json` хранит
сведения о плагине и опубликованных версиях. Ссылки на пакеты закрепляются
на конкретном Git-коммите; файлы старых версий остаются в истории.

GitHub-каталог помогает находить и скачивать файлы. Статус доверия клиент
получает отдельно от API реестра: ответ подписан Ed25519 и относится к
точному SHA-256 пакета. Наличие файла или поля `author` само по себе не
присваивает статус `verified` или `official`. Плагины выполняются в процессе
клиента, поэтому включайте код, которому доверяете.

## About Ovygram plugins

Ovygram Plugins is the moderated Python plugin catalog for **Ovygram**,
an open-source Telegram Desktop fork for Windows and Linux. It provides
release packages, a machine-readable plugin index and version history.
Developers can build Telegram desktop extensions with the Ovygram Python
SDK, including message hooks, custom menus and native panel buttons.

Submit plugins through [@OvygramApp](https://t.me/OvygramApp).
The registry publishes approved release files and the client verifies
their signed SHA-256 status. This project is independent of Telegram.
Each plugin retains its author's license; the repository does not assign
a common license to third-party plugin code.
