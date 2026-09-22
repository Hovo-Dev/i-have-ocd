<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">სიზუსტეზე აგებული პასუხები. OCD-ის დიაგნოზი არ გჭირდებათ!</strong>
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
  <strong title="ქართული" aria-label="ქართული">🇬🇪</strong> ·
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## ინსტალაცია

დააკოპირეთ და ჩასვით თქვენს CLI-ში:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

ან 🔗 [იხილეთ ინსტალაციის ინსტრუქციები](../../INSTALL.md).

## რას აკეთებს

უნარი თქვენი კოდის ასისტენტისთვის, რომელიც ხელს უშლის მას თქვას „უნდა იმუშაოს“. ზუსტი ცვლილებები. ან შემოწმებულია, ან პირდაპირ აღნიშნულია, რომ არ არის შემოწმებული. ყველა ღია საკითხი ერთ სიაში — და სია წერს `none`, როცა ცარიელია.

## რა იცვლება

<table>
<tr>
<td width="50%">

## მანამდე

> განვაახლე ავთენტიფიკაციის ლოგიკა და გზადაგზა რამდენიმე რამ დავალაგე. ეს უნდა გამოასწოროს ის 401-ები, რასაც ხედავდი. ტოკენის განახლებასთან შეიძლება დარჩეს რამდენიმე სასაზღვრო შემთხვევა, მაგრამ ალბათ ყველაფერი რიგზეა — მთავარი გზა ახლა კარგად გამოიყურება. შემატყობინე, თუ რამე უცნაური მოგეჩვენება!

</td>

<td width="50%">

## შემდეგ

> **Changed:** `src/auth.ts:42-58` — `verifyToken` ახლა იძახებს `jwt.verify`-ს RS256 გასაღებით `AUTH_PUBLIC_KEY`-დან.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 გაიარა, 0 ჩავარდა.
>
> **Not touched:** სესიის middleware, cookie-ს კონფიგურაცია, შესვლის ინტერფეისი.
>
> **Open:** ტოკენის განახლება 24 საათის შემდეგ შემოწმებული არ არის — ვერცერთი ტესტი არ ფარავს ამ გზას.

</td>
</tr>
</table>

## წესები

ათი წესი. სრული ვერსია: [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. ზუსტად თქვი, რა შეიცვალა — ფაილი, ხაზები, სიმბოლო.
2. არასდროს „უნდა იმუშაოს“. ან შემოწმებულია, ან პირდაპირ შემოწმებული არ არის.
3. გაკეთებულია ან არ არის გაკეთებული. მესამე მდგომარეობა არ არსებობს.
4. დაასახელე ის, რასაც არ შეხებიხარ.
5. ერთი პასუხი, და არა მენიუ.
6. უცნობი საკითხები ერთ `Open:` სიაში — რომელიც წერს `none`, როცა ცარიელია.
7. არავითარი დამშვიდება. სამაგიეროდ აჩვენე გამოსავალი.
8. შეცდომებს აქვს ზუსტი მიზეზი, და არა გადმოთქმული სიმპტომი.
9. არავითარი ცარიელი შექება.
10. შემოსაზღვრე ყოველი პასუხი: რას მოიცავს და რას არა.

და ერთი წესი, რომელიც ყველა ათს აღემატება: **სიზუსტე არ ნიშნავს გამოგონებას.** არასდროს გამოიგონო ხაზის ნომერი, რომელიც არ წაგიკითხავს.

## სახელის შესახებ

ხუმრობა სახელშია. თავად უნარი ხუმრობა არ არის და განზრახ არ ამშვიდებს — დამშვიდების ძიება სწორედ კომპულსიაა და არა წამალი. ამის ნაცვლად ის უარს ამბობს რომელიმე მტკიცება შეუმოწმებელი დატოვოს. ეს ყველა მკითხველისთვის სასარგებლოა და ეს ის არის, რასაც არცერთი ასისტენტი ნაგულისხმევად არ აკეთებს.

## მოირგე

გააკეთე fork, დაარედაქტირე `skills/i-have-ocd/SKILL.md` და შემდეგ ჩასვი შენი ასლი:

```bash
claude plugin uninstall i-have-ocd            # ჯერ წაშალე თავდაპირველი ასლი:
claude plugin marketplace remove i-have-ocd   # fork და ორიგინალი ორივე სახელს იზიარებენ
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

გადატვირთე შენი კოდის ასისტენტი და ხელახლა გამოიძახე `/i-have-ocd`.

## წვლილის შეტანა

განსაკუთრებით მისასალმებელია თარგმანები — იხილეთ [CONTRIBUTING.md](../../CONTRIBUTING.md).

## მადლობა

ამ რეპოზიტორიის ფორმა — ერთი `SKILL.md`, „მანამდე/შემდეგ“ ცხრილი, ინსტალაციის გზები აგენტების მიხედვით — მიჰყვება პროექტს [i-have-adhd](https://github.com/ayghri/i-have-adhd), ავტორი [Ayoub Ghriss](https://github.com/ayghri); ის პირველი იყო და MIT ლიცენზიით ვრცელდება. აქაური წესები ნულიდან დაიწერა და საპირისპირო მიმართულებით მიდის: ის უნარი ოპტიმიზაციას უკეთებს *დაწყებას* (ჯერ მოქმედება, დანარჩენი მოჭერი), ეს კი — *დასრულებას* (არაფერი შეუმოწმებელი, არაფერი შემოუსაზღვრავი). კარგად ავსებენ ერთმანეთს. დააინსტალირე ორივე.

## ლიცენზია

[MIT](../../LICENSE).

დადე ⭐, თუ დაგიზოგა ერთი წრე „მოიცა, მართლა გაუშვა ტესტები?“

</div>
