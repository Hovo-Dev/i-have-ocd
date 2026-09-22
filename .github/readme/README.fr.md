<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Des réponses taillées pour la certitude. Aucun diagnostic de TOC requis !</strong>
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
  <strong title="Français" aria-label="Français">🇫🇷</strong> ·
  <a href="README.de.md" title="Deutsch" aria-label="Deutsch">🇩🇪</a> ·
  <a href="README.tr.md" title="Türkçe" aria-label="Türkçe">🇹🇷</a> ·
  <a href="README.et.md" title="Eesti" aria-label="Eesti">🇪🇪</a> ·
  <a href="README.sr.md" title="Српски" aria-label="Српски">🇷🇸</a> ·
  <a href="README.ka.md" title="ქართული" aria-label="ქართული">🇬🇪</a> ·
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## Installation

Copiez-collez ceci dans l'invite de votre CLI :

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Ou 🔗 [consultez les instructions d'installation](../../INSTALL.md).

## Ce que ça fait

Une skill pour votre assistant de code qui l'empêche de dire « ça devrait marcher ». Des changements exacts. Vérifié, ou explicitement non vérifié. Tous les points en suspens dans une seule liste — et la liste indique `none` quand elle est vide.

## Ce qui change

<table>
<tr>
<td width="50%">

## Avant

> J'ai mis à jour la logique d'authentification et nettoyé deux ou trois choses au passage. Ça devrait régler les 401 que vous observiez. Il reste peut-être quelques cas limites sur le rafraîchissement du token, mais c'est probablement bon — le chemin principal a l'air correct maintenant. Dites-moi si quelque chose vous semble bizarre !

</td>

<td width="50%">

## Après

> **Changed:** `src/auth.ts:42-58` — `verifyToken` appelle désormais `jwt.verify` avec la clé RS256 issue de `AUTH_PUBLIC_KEY`.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 réussis, 0 échec.
>
> **Not touched:** middleware de session, configuration des cookies, interface de connexion.
>
> **Open:** le rafraîchissement de token au-delà de 24 h n'est pas testé — aucun test ne couvre ce chemin.

</td>
</tr>
</table>

## Les règles

Dix. La version intégrale se trouve dans [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Dire exactement ce qui a changé — fichier, lignes, symbole.
2. Jamais « ça devrait marcher ». Vérifié, ou explicitement non vérifié.
3. Fait ou pas fait. Il n'y a pas de troisième état.
4. Nommer ce que vous n'avez pas touché.
5. Une réponse, pas un menu.
6. Les inconnues vont dans une seule liste `Open:` — qui indique `none` quand elle est vide.
7. Pas de réconfort. Montrez la sortie à la place.
8. Les erreurs ont une cause exacte, pas un symptôme reformulé.
9. Pas d'approbations de remplissage.
10. Délimiter chaque réponse : ce qu'elle couvre et ce qu'elle ne couvre pas.

Et une règle qui prime sur les dix : **la précision n'est pas de l'invention.** N'inventez jamais un numéro de ligne que vous n'avez pas lu.

## À propos du nom

La blague, c'est le nom. La skill n'en est pas une, et elle refuse délibérément de rassurer : chercher à être rassuré est la compulsion, pas le remède. Ce qu'elle fait à la place, c'est refuser de laisser une affirmation non vérifiée — ce dont tout lecteur profite, et que aucun assistant ne fait par défaut.

## Personnaliser

Forkez, éditez `skills/i-have-ocd/SKILL.md`, puis mettez votre copie à la place :

```bash
claude plugin uninstall i-have-ocd            # retirez d'abord la copie d'origine :
claude plugin marketplace remove i-have-ocd   # le fork et l'original partagent les deux noms
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Redémarrez votre assistant, puis rappelez `/i-have-ocd`.

## Contribuer

Les traductions sont particulièrement bienvenues — voir [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Crédits

La forme de ce dépôt — un seul `SKILL.md`, un tableau avant/après, des chemins d'installation par agent — suit [i-have-adhd](https://github.com/ayghri/i-have-adhd) de [Ayoub Ghriss](https://github.com/ayghri), arrivé le premier et sous licence MIT. Les règles ici sont écrites de zéro et tirent dans le sens inverse : cette skill-là optimise le *démarrage* (l'action d'abord, on coupe le reste), celle-ci optimise la *clôture* (rien de non vérifié, rien de non délimité). Elles se complètent. Installez les deux.

## Licence

[MIT](../../LICENSE).

Mettez une ⭐ si ça vous a épargné un « attends, il a vraiment lancé les tests ? »

</div>
