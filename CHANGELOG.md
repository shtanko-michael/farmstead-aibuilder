# Изменения / Changelog

Формат — по одному разделу на релиз, новые сверху. Версии следуют
[семантическому версионированию](https://semver.org/lang/ru/).

One section per release, newest first. Versions follow [semantic versioning](https://semver.org/).

## v1.1.1

- Строки рукопожатия с сервисом в логе сервера подписаны `[Farmstead]` вместо `[hello]`.

- Service handshake lines in the server log are tagged `[Farmstead]` instead of `[hello]`.

## v1.1.0

- Мод говорит по-английски и по-русски: чат — на языке игры каждого игрока, `[language] language` в конфиге закрепляет один.
- Отмена голограммы и выхода из `/aibuild area` — ПКМ или **Backspace** (Esc перехватывало меню паузы).
- Подсказки в чате с кликабельными командами после постройки, снятия и генерации.
- Новые стадии генерации в чате; повтор одной стадии подряд не выводится.
- Строка в консоли сервера на каждую успешную генерацию.
- Отказ вне привата (с RegionGuard или Farmstead Claims) показывает размеры, углы и команды для привата.
- Сообщения подписаны `[Farmstead AI]`, анонс готовой постройки (`[chat] announce_builds`).
- `/aibuild`, `help`, `about`, `status` (операторы).
- Клиенты без мода снова могут зайти на сервер.
- Ошибка укладки не роняет сервер; карты высот после постройки; свой пул HTTP; повтор handshake.
- Кабинет: пауза, кулдаун, автопродление лимита, письма, лента событий.

- The mod speaks English and Russian: chat follows each player's game language, `[language] language` in the config pins one.
- Cancel the hologram and leave `/aibuild area` with RMB or **Backspace** (Esc was taken by the pause menu).
- Chat hints with clickable commands after placing, removing and generating.
- New generation stages in chat; a stage repeated back to back is said once.
- A server console line for every successful generation.
- A refusal outside a claim (with RegionGuard or Farmstead Claims) shows the size, the corners and the commands to claim it.
- Chat lines signed `[Farmstead AI]`; finished builds announced (`[chat] announce_builds`).
- `/aibuild`, `help`, `about`, `status` (operators).
- Clients without the mod can join again.
- A failed print no longer crashes the server; heightmaps after a print; own HTTP pool; handshake retried.
- Cabinet: pause, cooldown, limit auto-extension, emails, event feed.

## v1.0.0 — 13.09.2026

Первый публичный релиз. / First public release.

**Возможности**

- `/aibuild create <описание>` — постройка по тексту: голограмма-прицел, поворот на `R`,
  подтверждение, и укладка блок за блоком на глазах.
- `/aibuild area` — выделить область в мире и сгенерировать постройку под этот объём.
- `/aibuild list` и `/aibuild get <ключ>` — своя библиотека построек, повторная установка бесплатна.
- `/aibuild placed`, `/aibuild undo`, `/aibuild remove <n>` — снять постройку и вернуть то, что
  стояло под ней.
- `/aibuild balance` — остаток дневного лимита игрока.
- Права: уровень из конфига **или** нода `aibuilder.command.*`; ноды объявлены в NeoForge Permission
  API, поэтому LuckPerms читает их без дополнительной настройки.
- RegionGuard — опционален; когда он есть, приваты проверяются, и об этом пишется в лог при старте.
- Дневные лимиты сервера и игрока, персональные лимиты и запреты — в личном кабинете.

**Features**

- `/aibuild create <description>` — a build from text: hologram preview, `R` to rotate, confirm, then
  laid block by block in front of you.
- `/aibuild area` — mark a region in the world and generate a build to fit that volume.
- `/aibuild list` and `/aibuild get <key>` — a personal build library; placing again is free.
- `/aibuild placed`, `/aibuild undo`, `/aibuild remove <n>` — take a build down and restore what was
  under it.
- `/aibuild balance` — what is left of the player's daily cap.
- Permissions: a config level **or** an `aibuilder.command.*` node; the nodes are declared to the
  NeoForge Permission API, so LuckPerms reads them with no extra setup.
- RegionGuard is optional; when present, claims are enforced and the startup log says so.
- Daily caps for the server and per player, personal caps and bans — in the web cabinet.

**Требования / Requirements**

NeoForge 1.21.1, Java 21. Тот же jar нужен и на сервере, и у игроков. /
NeoForge 1.21.1, Java 21. The same jar goes on the server and on players' clients.
