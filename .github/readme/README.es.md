<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Salidas con forma de certeza. ¡No hace falta diagnóstico de TOC!</strong>
</p>
<p align="center">
  <a href="../../LICENSE"><img src="https://img.shields.io/github/license/Hovo-Dev/i-have-ocd?style=flat" alt="License"></a>
  <a href="https://github.com/Hovo-Dev/i-have-ocd/stargazers"><img src="https://img.shields.io/github/stars/Hovo-Dev/i-have-ocd?style=flat" alt="Stars"></a>
</p>

<p align="center">
  <a href="../../README.md" title="English" aria-label="English">🇬🇧</a> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳</a> ·
  <strong title="Español" aria-label="Español">🇪🇸</strong> ·
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
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## Instalación

Copia y pega esto en tu CLI:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

O bien 🔗 [consulta las instrucciones de instalación](../../INSTALL.md).

## Qué hace

Una skill para tu asistente de programación que le impide decir «debería funcionar». Cambios exactos. Verificado, o explícitamente no verificado. Todos los cabos sueltos en una sola lista, y la lista dice `none` cuando está vacía.

## Qué cambia

<table>
<tr>
<td width="50%">

## Antes

> He actualizado la lógica de autenticación y de paso he limpiado algunas cosas. Eso debería arreglar los 401 que veías. Puede que queden algunos casos límite con el refresco del token, pero seguramente esté bien: el camino principal tiene buena pinta. ¡Avísame si ves algo raro!

</td>

<td width="50%">

## Después

> **Changed:** `src/auth.ts:42-58` — `verifyToken` ahora llama a `jwt.verify` con la clave RS256 de `AUTH_PUBLIC_KEY`.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 pasaron, 0 fallaron.
>
> **Not touched:** middleware de sesión, configuración de cookies, interfaz de login.
>
> **Open:** el refresco de token más allá de 24 h no está probado: ningún test cubre esa ruta.

</td>
</tr>
</table>

## Las reglas

Diez. La versión íntegra está en [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Di exactamente qué cambió: archivo, líneas, símbolo.
2. Nunca «debería funcionar». Verificado, o explícitamente no verificado.
3. Hecho o no hecho. No hay tercer estado.
4. Nombra lo que no tocaste.
5. Una respuesta, no un menú.
6. Lo desconocido va en una sola lista `Open:`, que dice `none` cuando está vacía.
7. Nada de tranquilizar. Muestra la salida en su lugar.
8. Los errores llevan causa exacta, no el síntoma repetido.
9. Nada de afirmaciones de relleno.
10. Delimita cada respuesta: qué cubre y qué no.

Y una regla por encima de las diez: **precisión no es fabricación.** Nunca inventes un número de línea que no hayas leído.

## Sobre el nombre

El chiste es el nombre. La skill no es un chiste, y deliberadamente no tranquiliza: buscar tranquilidad es la compulsión, no la cura. Lo que hace es negarse a dejar una afirmación sin verificar, algo que beneficia a cualquier lector y que ningún asistente hace por defecto.

## Ajústala

Haz un fork, edita `skills/i-have-ocd/SKILL.md` y luego pon tu copia en su lugar:

```bash
claude plugin uninstall i-have-ocd            # quita primero la copia original:
claude plugin marketplace remove i-have-ocd   # el fork y el original comparten ambos nombres
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Reinicia tu asistente y vuelve a invocar `/i-have-ocd`.

## Contribuir

Las traducciones son especialmente bienvenidas: consulta [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Créditos

La forma de este repo —un solo `SKILL.md`, una tabla de antes y después, rutas de instalación por agente— sigue a [i-have-adhd](https://github.com/ayghri/i-have-adhd) de [Ayoub Ghriss](https://github.com/ayghri), que llegó primero y tiene licencia MIT. Las reglas de aquí están escritas desde cero y tiran en sentido contrario: aquella skill optimiza el *empezar* (la acción primero, recorta lo demás), esta optimiza el *cerrar* (nada sin verificar, nada sin delimitar). Se complementan. Instala las dos.

## Licencia

[MIT](../../LICENSE).

Dale ⭐ si te ahorró una ronda de «espera, ¿de verdad ejecutó los tests?»

</div>
