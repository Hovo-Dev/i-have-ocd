<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Որոշակիությամբ ձևավորված պատասխաններ։ ՕԿԽ-ի ախտորոշում պետք չէ։</strong>
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
  <a href="README.sr.md" title="Српски" aria-label="Српски">🇷🇸</a> ·
  <a href="README.ka.md" title="ქართული" aria-label="ქართული">🇬🇪</a> ·
  <strong title="Հայերեն" aria-label="Հայերեն">🇦🇲</strong> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## Տեղադրում

Պատճենեք և տեղադրեք ձեր CLI-ի հրահանգում՝

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Կամ 🔗 [տեսեք տեղադրման հրահանգները](../../INSTALL.md).

## Ի՞նչ է անում

Հմտություն ձեր ծրագրավորման օգնականի համար, որը թույլ չի տալիս նրան ասել «հավանաբար կաշխատի»։ Ճշգրիտ փոփոխություններ։ Կա՛մ ստուգված, կա՛մ բացահայտորեն նշված՝ որ ստուգված չէ։ Բոլոր բաց հարցերը մեկ ցուցակում, և ցուցակը գրում է `none`, երբ դատարկ է։

## Ի՞նչ է փոխվում

<table>
<tr>
<td width="50%">

## Առաջ

> Թարմացրի նույնականացման տրամաբանությունը և մի քանի բան էլ մաքրեցի ճանապարհին։ Սա հավանաբար կլուծի այն 401-երը, որ տեսնում էիր։ Թոքենի թարմացման հատվածում գուցե մնացած լինեն եզրային դեպքեր, բայց, կարծում եմ, ամեն ինչ կարգին է — հիմնական ուղին հիմա նորմալ է թվում։ Տեղեկացրու, եթե ինչ-որ բան տարօրինակ թվա։

</td>

<td width="50%">

## Հետո

> **Changed:** `src/auth.ts:42-58` — `verifyToken`-ն այժմ կանչում է `jwt.verify`՝ `AUTH_PUBLIC_KEY`-ից վերցված RS256 բանալիով։
>
> **Verified:** `npm test -- auth.spec.ts` → 14 անցավ, 0 ձախողվեց։
>
> **Not touched:** սեսիայի middleware, cookie-ի կարգավորումներ, մուտքի ինտերֆեյս։
>
> **Open:** 24 ժամից հետո թոքենի թարմացումը ստուգված չէ — ոչ մի թեստ չի ծածկում այդ ուղին։

</td>
</tr>
</table>

## Կանոնները

Տասը հատ։ Ամբողջական տարբերակը՝ [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Ճշգրիտ նշիր, թե ինչ է փոխվել՝ ֆայլ, տողեր, սիմվոլ։
2. Երբեք «հավանաբար կաշխատի»։ Կա՛մ ստուգված, կա՛մ բացահայտորեն չստուգված։
3. Արված է կամ արված չէ։ Երրորդ վիճակ չկա։
4. Նշիր, թե ինչին չես դիպչել։
5. Մեկ պատասխան, ոչ թե ցանկ։
6. Անհայտները՝ մեկ `Open:` ցուցակում, որը գրում է `none`, երբ դատարկ է։
7. Ոչ մի հանգստացնող խոսք։ Դրա փոխարեն ցույց տուր ելքը։
8. Սխալները ստանում են ճշգրիտ պատճառ, ոչ թե կրկնված ախտանիշ։
9. Ոչ մի դատարկ հավանություն։
10. Սահմանիր յուրաքանչյուր պատասխան՝ ինչ է ընդգրկում և ինչ՝ ոչ։

Եվ մեկ կանոն, որը գերակայում է բոլոր տասին՝ **ճշգրտությունը հորինելը չէ։** Երբեք մի հորինիր տողի համար, որը չես կարդացել։

## Անվան մասին

Կատակը անվան մեջ է։ Հմտությունն ինքը կատակ չէ և միտումնավոր չի հանգստացնում — հանգստություն փնտրելը հենց կոմպուլսիան է, ոչ թե բուժումը։ Դրա փոխարեն այն հրաժարվում է որևէ պնդում թողնել չստուգված։ Սա օգտակար է ցանկացած ընթերցողի, և սա այն է, ինչ ոչ մի օգնական լռելյայն չի անում։

## Հարմարեցրու

Fork արա, խմբագրիր `skills/i-have-ocd/SKILL.md`-ը, ապա տեղադրիր քո պատճենը՝

```bash
claude plugin uninstall i-have-ocd            # նախ հեռացրու սկզբնական պատճենը՝
claude plugin marketplace remove i-have-ocd   # fork-ը և սկզբնականը կիսում են երկու անունն էլ
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Վերագործարկիր ծրագրավորման օգնականդ, ապա նորից կանչիր `/i-have-ocd`։

## Ներդրում

Հատկապես ողջունելի են թարգմանությունները — տես [CONTRIBUTING.md](../../CONTRIBUTING.md)։

## Շնորհակալություն

Այս պահոցի կառուցվածքը՝ մեկ `SKILL.md`, «առաջ/հետո» աղյուսակ, տեղադրման ուղիներ ըստ գործակալի — հետևում է [Ayoub Ghriss](https://github.com/ayghri)-ի [i-have-adhd](https://github.com/ayghri/i-have-adhd)-ին, որն առաջինն էր և ունի MIT լիցենզիա։ Այստեղի կանոնները գրված են զրոյից և քաշում են հակառակ ուղղությամբ. այն հմտությունը օպտիմալացնում է *սկսելը* (գործողությունն առաջ, մնացածը կտրել), սա՝ *փակելը* (ոչինչ չստուգված, ոչինչ անսահման)։ Լավ են զուգակցվում։ Տեղադրիր երկուսն էլ։

## Լիցենզիա

[MIT](../../LICENSE).

Դիր ⭐, եթե սա քեզ խնայեց մեկ պտույտ «սպասի՛ր, իսկապե՞ս թեստերն աշխատեցրեց»։

</div>
