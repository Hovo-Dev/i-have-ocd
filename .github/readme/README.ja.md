<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">確実さで形づくられた出力。OCD の診断は不要です！</strong>
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
  <strong title="日本語" aria-label="日本語">🇯🇵</strong> ·
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

## インストール

CLI のプロンプトにコピー＆ペーストしてください:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

または 🔗 [インストール手順を確認する](../../INSTALL.md).

## 何をするのか

コーディングアシスタントに「たぶん動くはずです」と言わせないためのスキルです。変更点は正確に。検証済みか、検証していないと明示するかのどちらか。未解決の項目はすべて一つのリストにまとめ、空のときは `none` と書きます。

## 何が変わるのか

<table>
<tr>
<td width="50%">

## 変更前

> 認証まわりのロジックを更新し、ついでにいくつか整理しておきました。これで発生していた 401 は解決するはずです。トークンのリフレッシュ周辺にエッジケースが残っているかもしれませんが、おそらく問題ありません。メインの経路は問題なさそうです。何かおかしければ教えてください！

</td>

<td width="50%">

## 変更後

> **Changed:** `src/auth.ts:42-58` — `verifyToken` は `AUTH_PUBLIC_KEY` の RS256 鍵を使って `jwt.verify` を呼ぶようになりました。
>
> **Verified:** `npm test -- auth.spec.ts` → 14 件成功、0 件失敗。
>
> **Not touched:** セッションミドルウェア、cookie 設定、ログイン UI。
>
> **Open:** 24 時間を超えるトークンリフレッシュは未検証 — その経路を通るテストが存在しません。

</td>
</tr>
</table>

## ルール

全部で 10 個。完全版は [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. 何が変わったかを正確に述べる — ファイル、行、シンボル。
2. 「たぶん動く」は禁止。検証済みか、検証していないと明示するか。
3. 完了か未完了か。第三の状態はない。
4. 触っていないものを明示する。
5. 選択肢の一覧ではなく、答えを一つ。
6. 未確定事項は `Open:` のリスト一箇所にまとめる — 空なら `none` と書く。
7. 安心させない。代わりに出力を見せる。
8. エラーには正確な原因を。症状の言い換えは原因ではない。
9. 中身のない相づちを書かない。
10. すべての回答に範囲を示す — 何を含み、何を含まないか。

そして 10 個すべてに優先する 1 つのルール：**正確さは捏造ではない。** 読んでいない行番号を作り出してはならない。

## 名前について

冗談なのは名前だけです。スキル自体は冗談ではなく、意図的に「安心させること」をしません。安心を求める行為こそが強迫であり、治療ではないからです。代わりにこのスキルは、検証されていない主張をそのまま残すことを拒みます。これはどんな読み手にとっても有益で、そして既定ではどのアシスタントもやってくれないことです。

## 調整する

フォークして `skills/i-have-ocd/SKILL.md` を編集し、自分のコピーに差し替えます:

```bash
claude plugin uninstall i-have-ocd            # 先に元のコピーを削除します:
claude plugin marketplace remove i-have-ocd   # フォークと元リポジトリは両方の名前を共有します
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

コーディングアシスタントを再起動し、`/i-have-ocd` をもう一度呼び出してください。

## コントリビュート

翻訳を特に歓迎します — [CONTRIBUTING.md](../../CONTRIBUTING.md) を参照してください。

## クレジット

このリポジトリの構成 — 単一の `SKILL.md`、Before/After の対比表、エージェントごとのインストール手順 — は [Ayoub Ghriss](https://github.com/ayghri) 氏による [i-have-adhd](https://github.com/ayghri/i-have-adhd) に倣っています。あちらが先行しており、MIT ライセンスです。ここでのルールはゼロから書き起こされ、方向はちょうど逆です。あちらは*始めること*に最適化し（行動を先頭に、他は削る）、こちらは*閉じること*に最適化します（未検証をなくし、範囲を曖昧にしない）。相性は良いので、両方入れるのがおすすめです。

## ライセンス

[MIT](../../LICENSE).

「待って、本当にテスト走らせた？」を一回減らせたら ⭐ をお願いします。

</div>
