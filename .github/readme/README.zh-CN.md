<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">确定性塑造的输出。无需 OCD 诊断！</strong>
</p>
<p align="center">
  <a href="../../LICENSE"><img src="https://img.shields.io/github/license/Hovo-Dev/i-have-ocd?style=flat" alt="License"></a>
  <a href="https://github.com/Hovo-Dev/i-have-ocd/stargazers"><img src="https://img.shields.io/github/stars/Hovo-Dev/i-have-ocd?style=flat" alt="Stars"></a>
</p>

<p align="center">
  <a href="../../README.md" title="English" aria-label="English">🇬🇧</a> ·
  <strong title="简体中文" aria-label="简体中文">🇨🇳</strong> ·
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
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## 安装

复制粘贴到你的 CLI 提示中：

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

或者 🔗 [查看安装说明](../../INSTALL.md).

## 它做什么

一个让你的编程助手不再说“应该可以了”的技能。精确的改动。要么已验证，要么明确说明未验证。所有悬而未决的事项集中在一个列表里 —— 列表为空时会写明 `none`。

## 有什么变化

<table>
<tr>
<td width="50%">

## 之前

> 我更新了认证逻辑，顺便清理了一些地方。这应该能解决你看到的 401 问题。令牌刷新那块可能还有些边界情况，不过大概没事 —— 主流程现在看起来没问题。有什么不对的地方告诉我！

</td>

<td width="50%">

## 之后

> **Changed:** `src/auth.ts:42-58` — `verifyToken` 现在使用来自 `AUTH_PUBLIC_KEY` 的 RS256 密钥调用 `jwt.verify`。
>
> **Verified:** `npm test -- auth.spec.ts` → 14 项通过，0 项失败。
>
> **Not touched:** 会话中间件、cookie 配置、登录界面。
>
> **Open:** 超过 24 小时的令牌刷新未经测试 —— 没有测试覆盖该路径。

</td>
</tr>
</table>

## 规则

共十条。完整版本见 [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. 精确说明改了什么 —— 文件、行号、符号。
2. 绝不说“应该可以”。要么已验证，要么明确说明未验证。
3. 完成或未完成。没有第三种状态。
4. 说明你没有动过什么。
5. 给出一个答案，而不是一份菜单。
6. 未知项集中在一个 `Open:` 列表里 —— 为空时写明 `none`。
7. 不做安慰。直接给出输出。
8. 错误要给出确切原因，而不是复述症状。
9. 不说客套的附和话。
10. 每个回答都要划定边界：涵盖什么，不涵盖什么。

还有一条凌驾于全部十条之上的规则：**精确不等于编造。** 绝不虚构你没有读过的行号。

## 关于这个名字

玩笑在名字上，技能本身不是玩笑。它刻意不提供安慰 —— 寻求安慰是强迫症的症状，而非解药。它做的是拒绝让任何论断停留在未经验证的状态，这对每一位读者都有好处，而默认情况下没有任何助手会这么做。

## 调整它

Fork 本仓库，编辑 `skills/i-have-ocd/SKILL.md`，然后换上你自己的版本：

```bash
claude plugin uninstall i-have-ocd            # 先卸载上游版本：
claude plugin marketplace remove i-have-ocd   # fork 与上游共用同一个名称
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

重启你的编程助手，然后重新调用 `/i-have-ocd`。

## 参与贡献

尤其欢迎翻译 —— 参见 [CONTRIBUTING.md](../../CONTRIBUTING.md)。

## 致谢

本仓库的形态 —— 单个 `SKILL.md`、前后对照表、各平台安装方式 —— 参照了 [Ayoub Ghriss](https://github.com/ayghri) 的 [i-have-adhd](https://github.com/ayghri/i-have-adhd)，该项目在先，采用 MIT 许可。这里的规则完全重新编写，方向恰好相反：那个技能优化的是*开始*（先给行动，其余删掉），这个优化的是*收尾*（不留未验证之处，不留无边界之处）。两者互补，建议都装上。

## 许可证

[MIT](../../LICENSE).

如果它帮你省下一轮“等等，它到底跑没跑测试？”，请点个 ⭐

</div>
