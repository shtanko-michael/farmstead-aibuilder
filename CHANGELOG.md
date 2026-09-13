# Изменения / Changelog

Формат — по одному разделу на релиз, новые сверху. Версии следуют
[семантическому версионированию](https://semver.org/lang/ru/).

One section per release, newest first. Versions follow [semantic versioning](https://semver.org/).

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
