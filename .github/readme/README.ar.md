<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">مخرجات مصاغة على اليقين. لا حاجة لتشخيص الوسواس القهري!</strong>
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
  <a href="README.hy.md" title="Հայերեն" aria-label="Հայերեն">🇦🇲</a> ·
  <strong title="العربية" aria-label="العربية">🇸🇦</strong>
</p>

<div dir="rtl">

## التثبيت

انسخ والصق في موجّه سطر الأوامر لديك:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

أو 🔗 [راجع تعليمات التثبيت](../../INSTALL.md).

## ما الذي يفعله

مهارة لمساعدك البرمجي تمنعه من قول «يُفترض أن يعمل». تغييرات دقيقة. إمّا مُتحقَّق منها، أو مذكور صراحةً أنها غير مُتحقَّق منها. كل الأمور المعلّقة في قائمة واحدة — وتكتب القائمة `none` حين تكون فارغة.

## ما الذي يتغيّر

<table>
<tr>
<td width="50%">

## قبل

> حدّثت منطق المصادقة ونظّفت بعض الأمور على الطريق. هذا يُفترض أن يحل مشكلة 401 التي كنت تراها. قد تبقى بعض الحالات الحدّية في تحديث الرمز، لكن على الأرجح لا بأس — المسار الرئيسي يبدو جيدًا الآن. أخبرني إن بدا أي شيء غريبًا!

</td>

<td width="50%">

## بعد

> **Changed:** `src/auth.ts:42-58` — `verifyToken` يستدعي الآن `jwt.verify` بمفتاح RS256 من `AUTH_PUBLIC_KEY`.
>
> **Verified:** `npm test -- auth.spec.ts` → نجح 14، وفشل 0.
>
> **Not touched:** وسيط الجلسة، إعدادات الكوكيز، واجهة تسجيل الدخول.
>
> **Open:** تحديث الرمز بعد 24 ساعة غير مُختبَر — لا يوجد اختبار يغطي هذا المسار.

</td>
</tr>
</table>

## القواعد

عشر قواعد. النسخة الكاملة في [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. اذكر بالضبط ما الذي تغيّر — الملف، الأسطر، الرمز.
2. لا تقل أبدًا «يُفترض أن يعمل». إمّا مُتحقَّق منه، أو غير مُتحقَّق منه صراحةً.
3. مُنجَز أو غير مُنجَز. لا حالة ثالثة.
4. اذكر ما لم تمسّه.
5. إجابة واحدة، لا قائمة خيارات.
6. المجهولات في قائمة `Open:` واحدة — تكتب `none` حين تكون فارغة.
7. لا طمأنة. اعرض المخرجات بدلًا من ذلك.
8. للأخطاء سبب دقيق، لا عَرَض مُعاد صياغته.
9. لا عبارات مجاملة حشوية.
10. حدّد نطاق كل إجابة: ما تغطيه وما لا تغطيه.

وقاعدة واحدة تعلو القواعد العشر جميعًا: **الدقة ليست اختلاقًا.** لا تختلق أبدًا رقم سطر لم تقرأه.

## بخصوص الاسم

النكتة في الاسم وحده. المهارة ليست نكتة، وهي تمتنع عمدًا عن الطمأنة — فطلب الطمأنة هو القهر نفسه، لا العلاج. ما تفعله بدلًا من ذلك هو رفض ترك أي ادّعاء دون تحقّق، وهو أمر يستفيد منه كل قارئ ولا يفعله أي مساعد افتراضيًا.

## خصّصها

اعمل fork، وعدّل `skills/i-have-ocd/SKILL.md`، ثم ضع نسختك مكانها:

```bash
claude plugin uninstall i-have-ocd            # احذف النسخة الأصلية أولًا:
claude plugin marketplace remove i-have-ocd   # الـ fork والأصل يتشاركان الاسمين
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

أعد تشغيل مساعدك البرمجي، ثم استدعِ `/i-have-ocd` من جديد.

## المساهمة

الترجمات مُرحَّب بها بشكل خاص — راجع [CONTRIBUTING.md](../../CONTRIBUTING.md).

## شكر وتقدير

شكل هذا المستودع — ملف `SKILL.md` واحد، جدول «قبل وبعد»، مسارات تثبيت لكل وكيل — يتبع [i-have-adhd](https://github.com/ayghri/i-have-adhd) من [Ayoub Ghriss](https://github.com/ayghri)، الذي سبق إليه وهو مرخّص بـ MIT. القواعد هنا مكتوبة من الصفر وتشدّ في الاتجاه المعاكس: تلك المهارة تُحسّن *البدء* (الفعل أولًا، واحذف الباقي)، وهذه تُحسّن *الإغلاق* (لا شيء دون تحقّق، ولا شيء دون حدود). تتكاملان جيدًا. ثبّت كلتيهما.

## الرخصة

[MIT](../../LICENSE).

ضع ⭐ إن وفّرت عليك جولة واحدة من «مهلًا، هل شغّل الاختبارات فعلًا؟»

</div>
