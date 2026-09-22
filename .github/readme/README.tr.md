<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">Kesinlik biçiminde çıktılar. OCD teşhisi gerekmez!</strong>
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
  <strong title="Türkçe" aria-label="Türkçe">🇹🇷</strong> ·
  <a href="README.et.md" title="Eesti" aria-label="Eesti">🇪🇪</a> ·
  <a href="README.sr.md" title="Српски" aria-label="Српски">🇷🇸</a> ·
  <a href="README.ka.md" title="ქართული" aria-label="ქართული">🇬🇪</a> ·
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <a href="README.ar.md" title="العربية" aria-label="العربية">🇸🇦</a>
</p>

<div>

## Kurulum

CLI isteminize kopyalayıp yapıştırın:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

Veya 🔗 [kurulum talimatlarına bakın](../../INSTALL.md).

## Ne işe yarar

Kodlama asistanınızın “çalışması lazım” demesini engelleyen bir skill. Kesin değişiklikler. Ya doğrulanmış, ya da doğrulanmadığı açıkça belirtilmiş. Bütün açık uçlar tek bir listede — ve liste boşken `none` yazar.

## Ne değişir

<table>
<tr>
<td width="50%">

## Önce

> Kimlik doğrulama mantığını güncelledim, bu arada birkaç şeyi de temizledim. Bu, gördüğün 401'leri çözmeli. Token yenilemede birkaç uç durum kalmış olabilir ama muhtemelen sorun yoktur — ana akış şimdi iyi görünüyor. Bir terslik görürsen haber ver!

</td>

<td width="50%">

## Sonra

> **Changed:** `src/auth.ts:42-58` — `verifyToken` artık `AUTH_PUBLIC_KEY` içindeki RS256 anahtarıyla `jwt.verify` çağırıyor.
>
> **Verified:** `npm test -- auth.spec.ts` → 14 geçti, 0 başarısız.
>
> **Not touched:** oturum middleware'i, cookie yapılandırması, giriş arayüzü.
>
> **Open:** 24 saati aşan token yenilemesi test edilmedi — o yolu kapsayan test yok.

</td>
</tr>
</table>

## Kurallar

On tane. Tam hâli: [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. Tam olarak neyin değiştiğini söyle — dosya, satırlar, sembol.
2. Asla “çalışması lazım” deme. Ya doğrulanmış, ya da açıkça doğrulanmamış.
3. Yapıldı ya da yapılmadı. Üçüncü bir durum yok.
4. Neye dokunmadığını söyle.
5. Menü değil, tek bir cevap.
6. Bilinmeyenler tek bir `Open:` listesine girer — boşken `none` yazar.
7. Teselli yok. Onun yerine çıktıyı göster.
8. Hataların kesin bir nedeni olur, tekrarlanmış bir belirti değil.
9. Dolgu övgüsü yok.
10. Her cevabın sınırını çiz: neyi kapsıyor, neyi kapsamıyor.

Ve on kuralın hepsinden üstün olan tek kural: **kesinlik uydurmak değildir.** Okumadığın bir satır numarasını asla uydurma.

## İsim hakkında

Şaka isimde. Skill'in kendisi şaka değil ve bilerek teselli vermiyor — teselli aramak zorlantının kendisidir, çaresi değil. Bunun yerine yaptığı şey, hiçbir iddiayı doğrulanmamış bırakmayı reddetmek. Bu her okur için faydalı ve hiçbir asistanın varsayılan olarak yapmadığı bir şey.

## Kendine göre ayarla

Fork'la, `skills/i-have-ocd/SKILL.md` dosyasını düzenle, sonra kendi kopyanı yerleştir:

```bash
claude plugin uninstall i-have-ocd            # önce yukarı akış kopyasını kaldır:
claude plugin marketplace remove i-have-ocd   # fork ile orijinal iki ismi de paylaşır
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

Kodlama asistanını yeniden başlat, sonra `/i-have-ocd` komutunu tekrar çağır.

## Katkıda bulunma

Özellikle çeviriler memnuniyetle karşılanır — [CONTRIBUTING.md](../../CONTRIBUTING.md) dosyasına bak.

## Teşekkür

Bu deponun biçimi — tek bir `SKILL.md`, önce/sonra tablosu, her ajan için kurulum yolları — [Ayoub Ghriss](https://github.com/ayghri) tarafından yazılan ve MIT lisanslı olan [i-have-adhd](https://github.com/ayghri/i-have-adhd) projesini izliyor; o önce geldi. Buradaki kurallar sıfırdan yazıldı ve ters yöne çekiyor: o skill *başlamayı* optimize ediyor (önce eylem, gerisini kes), bu ise *kapatmayı* (doğrulanmamış hiçbir şey, sınırsız hiçbir şey). Birbirlerini iyi tamamlıyorlar. İkisini de kur.

## Lisans

[MIT](../../LICENSE).

“Dur bakalım, testleri gerçekten çalıştırdı mı?” turundan bir tanesini kurtardıysa ⭐ bırak.

</div>
