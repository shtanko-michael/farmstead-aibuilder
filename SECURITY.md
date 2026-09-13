# Безопасность / Security

## Если утёк токен / If your token leaked

**RU.** Токен `fsm_…` — это доступ к вашему кошельку AI-токенов. Если он попал в скриншот, публичный
конфиг, чужие руки:

1. Откройте [кабинет](https://farmsteadminecraft.online/cabinet/ai-builder) и нажмите «Отозвать» —
   мод на сервере перестанет работать немедленно, и никто больше не потратит ваши токены.
2. Создайте новый токен и впишите его в `config/farmstead_aibuilder.toml`.
3. Посмотрите отчёт по игрокам за период: если по токену тратили не ваши игроки, напишите нам.

Отзыв действует сразу, а расход по отозванному токену невозможен — ждать ничего не нужно.

**EN.** An `fsm_…` token is access to your AI-token wallet. If it ends up in a screenshot, a public
config or someone else's hands:

1. Open the [cabinet](https://farmsteadminecraft.online/cabinet/ai-builder) and press "Revoke" — the
   mod on your server stops working immediately and nobody can spend your tokens through it.
2. Create a new token and put it into `config/farmstead_aibuilder.toml`.
3. Check the per-player report for the period: if the spend was not your players, tell us.

Revocation is immediate; a revoked token cannot spend anything.

## Как сообщить об уязвимости / Reporting a vulnerability

**RU.** Не открывайте публичный issue для уязвимостей — особенно если нашли способ обойти проверку
токена, лимиты или права, или получить чужие постройки. Напишите на `shtanko.michael@gmail.com` с
темой `AI Builder security`.

Опишите, что вы сделали и что получилось; по возможности приложите версию мода
(`Implementation-Version` в манифесте jar) и строки лога. Мы отвечаем в течение нескольких дней.

Пожалуйста, не выкладывайте детали публично, пока мы не выпустим исправление.

**EN.** Do not open a public issue for security problems — especially if you found a way around the
token check, the limits or the permissions, or a way to read somebody else's builds. Write to
`shtanko.michael@gmail.com` with the subject `AI Builder security`.

Describe what you did and what happened; where possible include the mod version
(`Implementation-Version` in the jar manifest) and the relevant log lines. We reply within a few days.

Please do not publish the details until a fix is out.

## Поддерживаемые версии / Supported versions

**RU.** Исправления выходят только для последнего релиза. Обновление — это тот же файл
`farmstead-aibuilder-neoforge-1.21.1.jar` поверх старого.

**EN.** Fixes ship for the latest release only. Updating means putting the same
`farmstead-aibuilder-neoforge-1.21.1.jar` over the old one.
