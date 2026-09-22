<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Ответы, выстроенные вокруг определённости. Диагноз ОКР не требуется!</strong>
</p>
<p align="center">
  <a href="../../LICENSE"><img src="https://img.shields.io/github/license/Hovo-Dev/i-have-ocd?style=flat" alt="License"></a>
  <a href="https://github.com/Hovo-Dev/i-have-ocd/stargazers"><img src="https://img.shields.io/github/stars/Hovo-Dev/i-have-ocd?style=flat" alt="Stars"></a>
</p>

<p align="center">
  <a href="../../README.md" title="English" aria-label="English">🇬🇧</a> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳</a> ·
  <a href="README.es.md" title="Español" aria-label="Español">🇪🇸</a> ·
  <a href="README.pt-BR.md" title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷</a> ·
  <a href="README.ja.md" title="日本語" aria-label="日本語">🇯🇵</a> ·
  <a href="README.ko.md" title="한국어" aria-label="한국어">🇰🇷</a> ·
  <strong title="Русский" aria-label="Русский">🇷🇺</strong> ·
  <a href="README.fr.md" title="Français" aria-label="Français">🇫🇷</a> ·
  <a href="README.de.md" title="Deutsch" aria-label="Deutsch">🇩🇪</a> ·
  <a href="README.tr.md" title="Türkçe" aria-label="Türkçe">🇹🇷</a> ·
  <a href="README.et.md" title="Eesti" aria-label="Eesti">🇪🇪</a> ·
  <a href="README.sr.md" title="Српски" aria-label="Српски">🇷🇸</a> ·
  <a href="README.ka.md" title="ქართული" aria-label="ქართული">🇬🇪</a> ·
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## Установка

Скопируйте и вставьте в промпт вашего CLI:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Или 🔗 [посмотрите инструкции по установке](../../INSTALL.md).

## Что это делает

Навык для вашего кодинг-ассистента, который не даёт ему сказать «должно работать». Точные изменения. Либо проверено, либо явно указано, что не проверено. Все незакрытые вопросы — в одном списке, и список пишет `none`, когда он пуст.

## Что меняется

<table>
<tr>
<td width="50%">

## До

> Я обновил логику аутентификации и заодно кое-что подчистил. Это должно исправить те 401, которые вы видели. Возможно, остались крайние случаи с обновлением токена, но, наверное, всё в порядке — основной путь теперь выглядит нормально. Дайте знать, если что-то покажется странным!

</td>

<td width="50%">

## После

> **Changed:** `src/auth.ts:42-58` — `verifyToken` теперь вызывает `jwt.verify` с ключом RS256 из `AUTH_PUBLIC_KEY`.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 прошло, 0 упало.
>
> **Not touched:** middleware сессий, конфигурация cookie, интерфейс входа.
>
> **Open:** обновление токена спустя 24 ч не проверено — этот путь не покрыт тестами.

</td>
</tr>
</table>

## Правила

Их десять. Полная версия — [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Точно указывай, что изменилось — файл, строки, символ.
2. Никаких «должно работать». Либо проверено, либо явно не проверено.
3. Сделано или не сделано. Третьего состояния нет.
4. Называй то, что не трогал.
5. Один ответ, а не меню.
6. Неизвестное — в один список `Open:`, который пишет `none`, когда пуст.
7. Никаких успокоений. Покажи вывод вместо этого.
8. У ошибки должна быть точная причина, а не пересказанный симптом.
9. Никаких пустых поддакиваний.
10. Обозначай границы каждого ответа: что он покрывает, а что нет.

И одно правило поверх всех десяти: **точность — это не выдумывание.** Никогда не сочиняй номер строки, которую не читал.

## О названии

Шутка — только в названии. Сам навык не шутка и намеренно не занимается успокоением: поиск успокоения — это и есть компульсия, а не лечение. Вместо этого он отказывается оставлять утверждение непроверенным. Это полезно любому читателю и это то, чего ни один ассистент не делает по умолчанию.

## Настроить под себя

Сделайте форк, отредактируйте `skills/i-have-ocd/SKILL.md`, затем подставьте свою копию:

```bash
claude plugin uninstall i-have-ocd            # сначала уберите исходную копию:
claude plugin marketplace remove i-have-ocd   # форк и оригинал делят оба имени
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Перезапустите ассистента и снова вызовите `/i-have-ocd`.

## Участие

Особенно приветствуются переводы — см. [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Благодарности

Форма этого репозитория — один `SKILL.md`, таблица «до и после», пути установки для каждого агента — следует [i-have-adhd](https://github.com/ayghri/i-have-adhd) авторства [Ayoub Ghriss](https://github.com/ayghri): этот проект был первым и распространяется под лицензией MIT. Правила здесь написаны с нуля и тянут в противоположную сторону: тот навык оптимизирует *начало* (действие вперёд, остальное вырезать), этот — *завершение* (ничего непроверенного, ничего без границ). Они хорошо дополняют друг друга. Ставьте оба.

## Лицензия

[MIT](../../LICENSE).

Поставьте ⭐, если это избавило вас от одного круга «погоди, он вообще тесты запускал?»

</div>
