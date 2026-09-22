<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Auf Gewissheit getrimmte Ausgaben. Keine OCD-Diagnose nötig!</strong>
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
  <strong title="Deutsch" aria-label="Deutsch">🇩🇪</strong> ·
  <a href="README.tr.md" title="Türkçe" aria-label="Türkçe">🇹🇷</a> ·
  <a href="README.et.md" title="Eesti" aria-label="Eesti">🇪🇪</a> ·
  <a href="README.sr.md" title="Српски" aria-label="Српски">🇷🇸</a> ·
  <a href="README.ka.md" title="ქართული" aria-label="ქართული">🇬🇪</a> ·
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## Installation

In die Eingabe deiner CLI kopieren:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Oder 🔗 [sieh dir die Installationsanleitung an](../../INSTALL.md).

## Was es macht

Ein Skill für deinen Coding-Assistenten, der ihn daran hindert, „sollte funktionieren“ zu sagen. Exakte Änderungen. Verifiziert – oder ausdrücklich nicht verifiziert. Alle offenen Punkte in einer einzigen Liste, und die Liste sagt `none`, wenn sie leer ist.

## Was sich ändert

<table>
<tr>
<td width="50%">

## Vorher

> Ich habe die Auth-Logik aktualisiert und bei der Gelegenheit ein paar Dinge aufgeräumt. Das sollte die 401er beheben, die du gesehen hast. Beim Token-Refresh gibt es vielleicht noch ein paar Randfälle, aber wahrscheinlich ist alles in Ordnung – der Hauptpfad sieht jetzt gut aus. Sag Bescheid, wenn dir etwas komisch vorkommt!

</td>

<td width="50%">

## Nachher

> **Changed:** `src/auth.ts:42-58` — `verifyToken` ruft jetzt `jwt.verify` mit dem RS256-Schlüssel aus `AUTH_PUBLIC_KEY` auf.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 bestanden, 0 fehlgeschlagen.
>
> **Not touched:** Session-Middleware, Cookie-Konfiguration, Login-UI.
>
> **Open:** Token-Refresh nach mehr als 24 h ist ungetestet – kein Test deckt diesen Pfad ab.

</td>
</tr>
</table>

## Die Regeln

Zehn Stück. Die vollständige Fassung steht in [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Sage exakt, was sich geändert hat – Datei, Zeilen, Symbol.
2. Niemals „sollte funktionieren“. Verifiziert oder ausdrücklich nicht verifiziert.
3. Erledigt oder nicht erledigt. Einen dritten Zustand gibt es nicht.
4. Benenne, was du nicht angefasst hast.
5. Eine Antwort, keine Speisekarte.
6. Unbekanntes kommt in eine einzige `Open:`-Liste – die `none` sagt, wenn sie leer ist.
7. Keine Beschwichtigung. Zeige stattdessen die Ausgabe.
8. Fehler bekommen eine exakte Ursache, nicht ein wiederholtes Symptom.
9. Keine Füllfloskeln.
10. Grenze jede Antwort ein: was sie abdeckt und was nicht.

Dazu die eine Regel, die über allen zehn steht: **Präzision ist keine Erfindung.** Erfinde niemals eine Zeilennummer, die du nicht gelesen hast.

## Zum Namen

Der Witz ist der Name. Der Skill selbst ist keiner, und er beruhigt bewusst nicht – das Suchen nach Beruhigung ist der Zwang, nicht die Heilung. Stattdessen weigert er sich, eine Behauptung unverifiziert stehen zu lassen. Davon profitieren alle Lesenden, und kein Assistent tut es von sich aus.

## Anpassen

Forken, `skills/i-have-ocd/SKILL.md` bearbeiten, dann deine Kopie einsetzen:

```bash
claude plugin uninstall i-have-ocd            # zuerst die Original-Kopie entfernen:
claude plugin marketplace remove i-have-ocd   # Fork und Original teilen sich beide Namen
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Starte deinen Coding-Assistenten neu und rufe `/i-have-ocd` erneut auf.

## Mitmachen

Übersetzungen sind besonders willkommen – siehe [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Credits

Die Form dieses Repos – ein einziges `SKILL.md`, eine Vorher-Nachher-Tabelle, Installationswege pro Agent – folgt [i-have-adhd](https://github.com/ayghri/i-have-adhd) von [Ayoub Ghriss](https://github.com/ayghri), das zuerst da war und MIT-lizenziert ist. Die Regeln hier sind von Grund auf neu geschrieben und ziehen in die entgegengesetzte Richtung: jener Skill optimiert das *Anfangen* (Aktion zuerst, den Rest streichen), dieser das *Abschließen* (nichts Unverifiziertes, nichts Unbegrenztes). Sie ergänzen sich gut. Installiere beide.

## Lizenz

[MIT](../../LICENSE).

Gib einen ⭐, wenn es dir eine Runde „Moment, hat er die Tests wirklich laufen lassen?“ erspart hat.

</div>
