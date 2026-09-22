<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Излаз обликован извесношћу. Није потребна дијагноза ОКП!</strong>
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
  <a href="README.ru.md" title="Русский" aria-label="Русский">🇷🇺</a> ·
  <a href="README.fr.md" title="Français" aria-label="Français">🇫🇷</a> ·
  <a href="README.de.md" title="Deutsch" aria-label="Deutsch">🇩🇪</a> ·
  <a href="README.tr.md" title="Türkçe" aria-label="Türkçe">🇹🇷</a> ·
  <a href="README.et.md" title="Eesti" aria-label="Eesti">🇪🇪</a> ·
  <strong title="Српски" aria-label="Српски">🇷🇸</strong> ·
  <a href="README.ka.md" title="ქართული" aria-label="ქართული">🇬🇪</a> ·
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## Инсталација

Копирај и налепи у промпт свог CLI-ја:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Или 🔗 [погледај упутства за инсталацију](../../INSTALL.md).

## Шта ради

Вештина за твог програмерског асистента која му не да да каже „требало би да ради“. Прецизне измене. Или проверено, или изричито наведено да није проверено. Сви отворени крајеви у једној листи — и листа пише `none` када је празна.

## Шта се мења

<table>
<tr>
<td width="50%">

## Пре

> Ажурирао сам логику аутентификације и успут почистио неколико ствари. Ово би требало да реши оне 401 грешке које си видео. Можда је остало неколико граничних случајева око освежавања токена, али вероватно је у реду — главна путања сада изгледа добро. Јави ако ти нешто делује чудно!

</td>

<td width="50%">

## После

> **Changed:** `src/auth.ts:42-58` — `verifyToken` сада позива `jwt.verify` са RS256 кључем из `AUTH_PUBLIC_KEY`.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 прошло, 0 пало.
>
> **Not touched:** middleware сесије, подешавања колачића, интерфејс за пријаву.
>
> **Open:** освежавање токена после 24 ч није проверено — ниједан тест не покрива ту путању.

</td>
</tr>
</table>

## Правила

Има их десет. Пуна верзија је у [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Реци тачно шта се променило — фајл, линије, симбол.
2. Никад „требало би да ради“. Или проверено, или изричито непроверено.
3. Урађено или неурађено. Трећег стања нема.
4. Наведи шта ниси дирао.
5. Један одговор, а не мени.
6. Непознато иде у једну `Open:` листу — која пише `none` када је празна.
7. Без умиривања. Уместо тога покажи излаз.
8. Грешке добијају тачан узрок, а не препричан симптом.
9. Без празних похвала.
10. Ограничи сваки одговор: шта покрива, а шта не.

И једно правило изнад свих десет: **прецизност није измишљање.** Никад не измишљај број линије који ниси прочитао.

## О имену

Шала је у имену. Сама вештина није шала и намерно не умирује — тражење умирења јесте компулзија, а не лек. Уместо тога, она одбија да остави било коју тврдњу непровереном. То користи сваком читаоцу и то ниједан асистент не ради подразумевано.

## Подеси по своме

Направи fork, измени `skills/i-have-ocd/SKILL.md`, па убаци своју копију:

```bash
claude plugin uninstall i-have-ocd            # прво уклони изворну копију:
claude plugin marketplace remove i-have-ocd   # fork и извор деле оба имена
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Рестартуј свог програмерског асистента, па поново позови `/i-have-ocd`.

## Доприноси

Преводи су посебно добродошли — погледај [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Захвалнице

Облик овог репозиторијума — један `SKILL.md`, табела „пре и после“, путеви инсталације по агенту — прати [i-have-adhd](https://github.com/ayghri/i-have-adhd) аутора [Ayoub Ghriss](https://github.com/ayghri), који је стигао први и има MIT лиценцу. Правила овде су писана из нуле и вуку на супротну страну: она вештина оптимизује *почињање* (прво акција, остало исеци), ова оптимизује *затварање* (ништа непроверено, ништа без граница). Добро иду заједно. Инсталирај обе.

## Лиценца

[MIT](../../LICENSE).

Остави ⭐ ако ти је уштедело један круг „чекај, да ли је стварно покренуо тестове?“

</div>
