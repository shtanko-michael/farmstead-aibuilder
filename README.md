<h1 align="center">Farmstead AI Builder</h1>

<p align="center">
  <b>Мод для Minecraft, который строит по текстовому описанию.</b><br>
  Игрок пишет <code>/aibuild create средневековая таверна с верандой</code> — через пару минут
  постройка вырастает у него на глазах, блок за блоком.
</p>

<p align="center">
  <i>A Minecraft mod that generates buildings from a text prompt: type what you want, aim the
  hologram, watch it built block by block. NeoForge 1.21.1.</i>
</p>

<p align="center">
  <img src="https://img.shields.io/github/v/release/shtanko-michael/farmstead-aibuilder?label=версия&color=4caf50" alt="Последняя версия">
  <img src="https://img.shields.io/github/downloads/shtanko-michael/farmstead-aibuilder/total?label=скачиваний&color=55ffff" alt="Скачиваний">
  <img src="https://img.shields.io/badge/Minecraft-1.21.1-blue" alt="Minecraft 1.21.1">
  <img src="https://img.shields.io/badge/loader-NeoForge-orange" alt="NeoForge">
</p>

<p align="center">
  <img src="assets/demo-build.gif"
       alt="Генерация постройки по описанию в Minecraft: голограмма-превью, затем постройка растёт блок за блоком"
       width="860">
</p>

<p align="center">
  <a href="https://github.com/shtanko-michael/farmstead-aibuilder/releases/latest/download/farmstead-aibuilder-neoforge-1.21.1.jar"><b>⬇ Скачать последнюю версию</b></a>
  ·
  <a href="https://farmsteadminecraft.online/cabinet/ai-builder"><b>Получить токен</b></a>
  ·
  <a href="#команды">Команды</a>
  ·
  <a href="#права-и-luckperms">Права</a>
</p>

---

## Что умеет мод

**Генерация построек по описанию.** Игрок описывает словами, что хочет — дом, башню, мост, ферму,
целую площадь — и получает готовую структуру. Не заранее заготовленные схематики: каждая постройка
собирается под конкретный запрос, поэтому «маленький рыбацкий домик на сваях» и «высокая каменная
башня с флагом» выходят разными зданиями, а не одним шаблоном с другой текстурой.

**Голограмма перед установкой.** В мир не пишется ни одного блока, пока игрок не согласится.
Постройка сначала показывается призраком под прицелом: её можно отнести подальше, повернуть на `R`
нужной стороной к дороге и только потом подтвердить. Отмена — один клик, и ничего не произошло.

**Стройка на глазах, а не «раз — и появилось».** Блоки ложатся рядами снизу вверх, за фронтом
укладки идёт светящаяся пыль, каждый севший блок вспыхивает, сверху бьёт луч. Это не косметика ради
косметики: игрок видит, что именно и куда встаёт, и успевает передумать. Сервер при этом не
проседает — укладка идёт с бюджетом в пару миллисекунд на тик, а не одним куском.

**Генерация в выделенную область.** `/aibuild area` — отметить углы прямо в мире, и постройка будет
сгенерирована **под этот объём**: не обрезана по нему, а спланирована так, чтобы в него попасть.
Удобно вписывать здание в готовую застройку.

**Полная отмена.** Мод помнит, что стояло под каждой постройкой, и `/aibuild undo` возвращает землю
в прежний вид — вместе с деревьями, склоном и чужой дорогой, по которой прошлись. Отменить можно и
не последнюю постройку, а любую из списка `/aibuild placed`.

**Своя библиотека у каждого игрока.** Постройки сохраняются: `/aibuild list` показывает свои,
`/aibuild get <ключ>` ставит ещё раз — в другом месте, другой стороной, сколько угодно раз, и уже
бесплатно.

**Работает с ванильным клиентом.** Игрок без мода тоже может пользоваться командой — постройка
просто ставится перед ним, без прицеливания. Но голограмму и анимацию рисует клиентская часть, так
что мод стоит раздать всем.

**Контроль расходов у администратора.** Генерация оплачивается токенами с вашего аккаунта, и вы
задаёте, кто и сколько может тратить: общий лимит сервера в сутки, лимит на игрока, персональный
лимит конкретному человеку, запрет отдельным игрокам. Всё это — на одной странице в кабинете, вместе
с отчётом «кто сколько потратил».

---

## Как это работает

1. **Игрок пишет команду.** `/aibuild create <описание>` — обычный текст, на русском или английском.
2. **Генерация идёт на нашем сервисе.** Ваш сервер отправляет описание на
   `ai.farmsteadminecraft.online` и получает готовый набор блоков. Модели, промпты и вычисления —
   на нашей стороне; вашему серверу не нужны ни видеокарта, ни ключи от нейросетей.
3. **Мод ставит постройку.** Голограмма, подтверждение, послойная укладка, запись для отмены.

Платит **владелец токена** — вы, со своего баланса AI-токенов на
[farmsteadminecraft.online](https://farmsteadminecraft.online). Одна постройка обычно стоит
**200–600 токенов**; лимиты и расход видны в кабинете.

---

## Поддерживаемые сборки

| Загрузчик | Версия игры | Файл релиза |
|---|---|---|
| NeoForge | 1.21.1 | `farmstead-aibuilder-neoforge-1.21.1.jar` |

Paper/Purpur, Fabric и Forge 1.20.1 — в планах.

Имя файла не содержит версию намеренно: обновление **перезаписывает** старый jar, а не кладёт рядом
второй с тем же mod id (FML в такой ситуации молча загрузит один из них). Версия — в названии релиза
и в манифесте jar. Постоянная ссылка на свежую сборку:
[releases/latest/download/farmstead-aibuilder-neoforge-1.21.1.jar](https://github.com/shtanko-michael/farmstead-aibuilder/releases/latest/download/farmstead-aibuilder-neoforge-1.21.1.jar).

## Требования

- Сервер **NeoForge 1.21.1**, Java 21.
- **Тот же jar у игроков** в `mods/` клиента: клиентская половина рисует голограмму-прицел
  (`R` — поворот, ЛКМ/Enter — поставить, ПКМ/Esc — отменить) и всю анимацию стройки.
- Аккаунт на [farmsteadminecraft.online](https://farmsteadminecraft.online) с AI-токенами на балансе.
- Исходящий HTTPS с сервера на `ai.farmsteadminecraft.online`.
- **LuckPerms — необязателен.** Нужен, только если хотите раздавать команды по группам, а не
  уровнями прав из конфига.

Игрок **без** мода на сервер зайдёт (его не отвергают), но постройка просто появится перед ним — без
прицела и без анимации. Это аварийный режим, а не способ играть.

## Установка

1. Скачайте [последний релиз](https://github.com/shtanko-michael/farmstead-aibuilder/releases/latest)
   и положите jar в `mods/` сервера. Тот же файл раздайте игрокам.
2. Запустите сервер один раз — появится `config/farmstead_aibuilder.toml`.
3. В кабинете [farmsteadminecraft.online/cabinet/ai-builder](https://farmsteadminecraft.online/cabinet/ai-builder)
   нажмите «Создать токен». Значение показывается **один раз** — скопируйте сразу.
4. Впишите его в конфиг:

   ```toml
   [api]
   api_base_url = "https://ai.farmsteadminecraft.online"
   bearer_token = "fsm_..."
   ```

5. Перезапустите сервер. В логе появятся две строки:

   ```
   [hello] AI service OK: server='Основной сервер' mode=external apiVersion=1 …
   [regionguard] API not available (…) — claim checks are skipped
   ```

   Первая — токен принят. Если вместо неё `[hello] the AI service rejected this server's token`,
   токен вписан неверно или отозван. Вторая — про защиту территорий, см. [ниже](#территория).

Токен — это ключ к вашему кошельку. Не публикуйте конфиг. Утёк — отзовите в кабинете и создайте новый.

## Команды

Токены тратит только `create` (и `area build`). Всё остальное бесплатно.

| Команда | Что делает | Токены | Нода |
|---|---|---|---|
| `/aibuild create <описание>` | Сгенерировать постройку и поставить через голограмму | **да** | `aibuilder.command.create` |
| `/aibuild area` | Режим выделения: ЛКМ — угол 1, ПКМ — угол 2, Esc — выход | — | `aibuilder.command.area` |
| `/aibuild area build <описание>` | Сгенерировать **в выделенную область** | **да** | `aibuilder.command.area` |
| `/aibuild area pos1` / `pos2` / `clear` | Углы с позиции игрока (для клиента без мода) и сброс | — | `aibuilder.command.area` |
| `/aibuild list [страница]` | Свои постройки списком, строка кликабельна | — | `aibuilder.command.list` |
| `/aibuild get <ключ>` | Поставить свою постройку ещё раз | — | `aibuilder.command.get` |
| `/aibuild placed [страница]` | Что из своего стоит в этом мире | — | `aibuilder.command.placed` |
| `/aibuild undo` | Снять последнюю постройку и вернуть, что было под ней | — | `aibuilder.command.undo` |
| `/aibuild remove <n>` | То же для любой строки `placed` | — | `aibuilder.command.undo` |
| `/aibuild balance` | Сколько токенов осталось игроку на сегодня | — | `aibuilder.command.balance` |
| `/aibuild topup` | Объясняет, что генерации оплачивает администратор | — | `aibuilder.command.topup` |

Постройки игроков вашего сервера видны только на нём: у них нет доступа к лаунчеру и маркету
Farmstead, и ваш собственный кабинет их не показывает — только расход.

## Права и LuckPerms

У каждой подкоманды **две двери, и достаточно любой**:

1. **Vanilla permission level** из `config/farmstead_aibuilder.toml`, секция `[permissions]`:
   `0` — все, `2` — операторы (уровень `/give`, `/setblock`), `4` — владелец/консоль.
2. **Нода** `aibuilder.command.*`, выданная менеджером прав.

По умолчанию все уровни — `0`, команды открыты всем: настоящий ограничитель — ваши дневные лимиты в
кабинете, а не права.

> **Порядок важен.** Нода при `level = 0` ничего не меняет: уровень 0 проходят все, и до проверки
> ноды дело не доходит. Сначала поднимите уровень, потом выдавайте ноду.

Мод объявляет свои ноды в NeoForge Permission API, поэтому **LuckPerms видит их сам** — ставить
ничего дополнительно не нужно.

Типовой сценарий «генерация только донатерам, остальное всем»:

```toml
# config/farmstead_aibuilder.toml
[permissions]
create_level = 4   # закрыли create и area от всех, кроме консоли
area_level   = 4
```

```
/lp creategroup builder
/lp group builder permission set aibuilder.command.create true
/lp group builder permission set aibuilder.command.area true
/lp user Steve parent add builder
```

Разово одному игроку: `/lp user Steve permission set aibuilder.command.create true`.
Забрать обратно: `/lp group builder permission unset aibuilder.command.create` — тогда снова решает
уровень.

Полный список нод:

```
aibuilder.command.create    aibuilder.command.area     aibuilder.command.get
aibuilder.command.list      aibuilder.command.placed   aibuilder.command.undo
aibuilder.command.balance   aibuilder.command.topup
```

`undo` и `remove` делят одну ноду (`aibuilder.command.undo`): это одна власть над одними записями.

**Без менеджера прав** ноды никто не выдаёт, и весь гейт — уровни из конфига. Операторы проходят
всё: `/op` даёт уровень 4, а он перекрывает любой уровень ниже.

## Лимиты и расход

Всё в кабинете, на той же странице, где создан токен:

- **Общий лимит в день** — сколько токенов сервер может потратить за сутки (UTC).
- **Лимит на игрока в день** — по умолчанию для всех; в таблице игроков можно задать персональный
  или **запретить** игроку генерацию.
- **Отчёт** — кто сколько потратил за 7 / 30 дней, по игрокам и по дням.

Лимиты считаются на стороне сервиса, а не в моде: действуют сразу, перезапуск не нужен, обновление
мода их не сбрасывает.

## Территория

Мод умеет спрашивать только **RegionGuard**. Что он делает, видно в логе при старте:

| Строка в логе | Что значит |
|---|---|
| `[regionguard] API available — claims are enforced for non-operators` | Приваты проверяются: постройка целиком должна попадать в регион игрока |
| `[regionguard] API not available (…) — claim checks are skipped` | Плагина нет, мод о ваших приватах не знает и территорию **не проверяет** |

Без RegionGuard игрок поставит постройку везде, где ему разрешена команда. Варианты: поднять
`create_level`/`area_level` и выдавать ноду доверенным, ограничить дневным лимитом — или поставить
RegionGuard.

Если RegionGuard стоит, но его вызов упал, мод **откажет** в установке и напишет
`[regionguard] claim check failed` — сломавшаяся защита не должна читаться как «разрешено».

## Что уходит на сервис

С каждым запросом сервис получает: **описание постройки**, **ID игрока** (UUID) и **его ник** — чтобы
показать вам расход по игрокам. Ничего другого с сервера не читается. Снимок «что стояло под
постройкой» хранится как непрозрачные байты и нужен только для `/aibuild undo`.

## Если что-то не так

| В логе или в чате | Что это значит |
|---|---|
| `[hello] … rejected this server's token` | Токен неверный или отозван — проверьте `bearer_token` |
| `Ваш лимит на сегодня исчерпан` | Дневной лимит игрока — поднимите в кабинете или подождите до полуночи UTC |
| `Дневной лимит сервера исчерпан` | Общий лимит сервера — то же |
| `Администратор сервера закрыл вам генерацию` | Игрок в списке запрещённых |
| `Сервис занят` | Слишком много одновременных генераций — попробуйте через минуту |
| `Недостаточно токенов` | На вашем AI-кошельке меньше минимума — пополните в кабинете |
| `[regionguard] claim check failed` | RegionGuard стоит, но его вызов упал; установка отклоняется, пока это не починено |
| Команда с русским текстом «не проходит» | Какой-то мод фильтрует символы в командах (у NeoEssentials — `security.allowUnsafeCommands`) |

Ошибки и предложения — в [Issues](https://github.com/shtanko-michael/farmstead-aibuilder/issues).

---

## English

**Farmstead AI Builder** is a Minecraft mod that generates buildings from a text prompt. A player
types `/aibuild create a medieval tavern with a porch`, aims a hologram preview, rotates it with `R`,
confirms — and the structure is laid block by block in front of them. Everything can be undone:
`/aibuild undo` restores exactly what stood there before.

**Features**

- Text-to-build generation: houses, towers, bridges, farms, whole plazas — planned per prompt, not
  picked from a schematic pack.
- Hologram preview before anything is written to the world; rotate, reposition, confirm or cancel.
- Block-by-block construction with particles, sound and a beacon beam, on a per-tick time budget so
  the server does not stall.
- Generate **into a selected region** (`/aibuild area`) so a building fits an existing street.
- Full undo of any placement, including what the build covered.
- Per-player build library: place a saved build again for free.
- Vanilla clients work (the build lands in front of them); clients with the mod get the hologram.
- Owner-side spend control: daily caps for the server and per player, per-player bans, and a spend
  report — all in the web cabinet.

**How it works.** Generation runs on `ai.farmsteadminecraft.online`, not on your machine: your server
sends the prompt and receives blocks. No GPU, no model keys on your side. Generations are billed to
the token owner's AI-token balance (~200–600 tokens per build).

**Requirements.** NeoForge 1.21.1 server (Java 21), the same jar on players' clients, an account on
[farmsteadminecraft.online](https://farmsteadminecraft.online) with AI tokens, and outbound HTTPS.
LuckPerms is optional — it is only needed to hand commands out per group.

**Install.** Drop the jar into `mods/`, start once, paste the `fsm_…` token from
[the cabinet](https://farmsteadminecraft.online/cabinet/ai-builder) into
`config/farmstead_aibuilder.toml`, restart, and check the `[hello]` line in the log.

**Permissions.** Every subcommand is gated by a vanilla permission level (`[permissions]` in the
config) **or** a node — `aibuilder.command.create`, `.area`, `.get`, `.list`, `.placed`, `.undo`,
`.balance`, `.topup`. The mod registers these with the NeoForge Permission API, so LuckPerms reads
them without any extra setup. Note that a node does nothing while the level is `0`: everyone clears
level 0 already. Raise the level first, then grant the node.

Full documentation is in Russian above.

## Лицензия

Мод распространяется как есть для установки на серверы. Исходный код закрыт; декомпиляция,
модификация и перераспространение запрещены. Все права принадлежат Farmstead.
