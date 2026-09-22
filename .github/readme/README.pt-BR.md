<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Saídas moldadas por certeza. Não é preciso diagnóstico de TOC!</strong>
</p>
<p align="center">
  <a href="../../LICENSE"><img src="https://img.shields.io/github/license/Hovo-Dev/i-have-ocd?style=flat" alt="License"></a>
  <a href="https://github.com/Hovo-Dev/i-have-ocd/stargazers"><img src="https://img.shields.io/github/stars/Hovo-Dev/i-have-ocd?style=flat" alt="Stars"></a>
</p>

<p align="center">
  <a href="../../README.md" title="English" aria-label="English">🇬🇧</a> ·
  <a href="README.zh-CN.md" title="简体中文" aria-label="简体中文">🇨🇳</a> ·
  <a href="README.es.md" title="Español" aria-label="Español">🇪🇸</a> ·
  <strong title="Português (Brasil)" aria-label="Português (Brasil)">🇧🇷</strong> ·
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

## Instalação

Copie e cole no prompt da sua CLI:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Ou 🔗 [veja as instruções de instalação](../../INSTALL.md).

## O que faz

Uma skill para o seu assistente de programação que o impede de dizer “deve funcionar”. Mudanças exatas. Verificado, ou explicitamente não verificado. Todas as pontas soltas em uma única lista — e a lista diz `none` quando está vazia.

## O que muda

<table>
<tr>
<td width="50%">

## Antes

> Atualizei a lógica de autenticação e aproveitei para limpar algumas coisas. Isso deve resolver os 401 que você estava vendo. Pode haver alguns casos extremos no refresh do token, mas provavelmente está tudo bem — o caminho principal parece ok agora. Me avise se algo parecer estranho!

</td>

<td width="50%">

## Depois

> **Changed:** `src/auth.ts:42-58` — `verifyToken` agora chama `jwt.verify` com a chave RS256 de `AUTH_PUBLIC_KEY`.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 passaram, 0 falharam.
>
> **Not touched:** middleware de sessão, configuração de cookies, interface de login.
>
> **Open:** refresh de token após 24h não foi testado — nenhum teste cobre esse caminho.

</td>
</tr>
</table>

## As regras

Dez delas. A versão completa está em [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Diga exatamente o que mudou — arquivo, linhas, símbolo.
2. Nunca “deve funcionar”. Verificado, ou explicitamente não verificado.
3. Feito ou não feito. Não existe terceiro estado.
4. Diga o que você não tocou.
5. Uma resposta, não um cardápio.
6. Desconhecidos vão em uma única lista `Open:` — que diz `none` quando está vazia.
7. Nada de tranquilizar. Mostre a saída.
8. Erros recebem causa exata, não o sintoma repetido.
9. Nada de elogios de enchimento.
10. Delimite cada resposta: o que ela cobre e o que não cobre.

Mais a regra que supera as dez: **precisão não é invenção.** Nunca invente um número de linha que você não leu.

## Sobre o nome

A piada é o nome. A skill não é piada, e deliberadamente não tranquiliza — buscar tranquilização é a compulsão, não a cura. O que ela faz é se recusar a deixar uma afirmação sem verificação, algo que beneficia qualquer leitor e que nenhum assistente faz por padrão.

## Ajuste

Faça um fork, edite `skills/i-have-ocd/SKILL.md` e então coloque a sua cópia no lugar:

```bash
claude plugin uninstall i-have-ocd            # remova a cópia original primeiro:
claude plugin marketplace remove i-have-ocd   # fork e original compartilham os dois nomes
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Reinicie seu assistente e invoque `/i-have-ocd` novamente.

## Contribuindo

Traduções são especialmente bem-vindas — veja [CONTRIBUTING.md](../../CONTRIBUTING.md).

## Créditos

O formato deste repositório — um único `SKILL.md`, uma tabela de antes e depois, caminhos de instalação por agente — segue o [i-have-adhd](https://github.com/ayghri/i-have-adhd) de [Ayoub Ghriss](https://github.com/ayghri), que chegou primeiro e é licenciado sob MIT. As regras aqui foram escritas do zero e puxam para o lado oposto: aquela skill otimiza o *começar* (ação primeiro, corte o resto), esta otimiza o *fechar* (nada sem verificação, nada sem limite). Combinam bem. Instale as duas.

## Licença

[MIT](../../LICENSE).

Dê uma ⭐ se economizou uma rodada de “peraí, ele rodou os testes mesmo?”

</div>
