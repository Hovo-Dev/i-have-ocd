<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="../../logo-dark.png">
    <img src="../../logo.png" alt="i-have-ocd" width="140" />
  </picture>
</p>
<p align="center">
  <strong align="center">확실성으로 다듬은 출력. OCD 진단은 필요 없습니다!</strong>
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
  <strong title="한국어" aria-label="한국어">🇰🇷</strong> ·
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

## 설치

CLI 프롬프트에 복사해 붙여넣으세요:

```text
Install the i-have-ocd skill/plugin from https://github.com/Hovo-Dev/i-have-ocd, refer to the repo's AGENTS.md for instructions.
```

또는 🔗 [설치 안내 보기](../../INSTALL.md).

## 무엇을 하는가

코딩 어시스턴트가 “아마 될 겁니다”라고 말하지 못하게 하는 스킬입니다. 변경 사항은 정확하게. 검증했거나, 검증하지 않았다고 명시하거나 둘 중 하나. 남은 미결 항목은 전부 하나의 목록에 모으고, 비어 있으면 `none`이라고 적습니다.

## 무엇이 달라지는가

<table>
<tr>
<td width="50%">

## 이전

> 인증 로직을 업데이트하면서 몇 가지도 함께 정리했습니다. 보고 계시던 401 문제는 이걸로 해결될 겁니다. 토큰 갱신 쪽에 엣지 케이스가 남아 있을 수도 있지만 아마 괜찮을 거예요. 메인 경로는 이제 괜찮아 보입니다. 이상한 점 있으면 알려주세요!

</td>

<td width="50%">

## 이후

> **Changed:** `src/auth.ts:42-58` — `verifyToken`이 이제 `AUTH_PUBLIC_KEY`의 RS256 키로 `jwt.verify`를 호출합니다.
>
> **Verified:** `npm test -- auth.spec.ts` → 14개 통과, 0개 실패.
>
> **Not touched:** 세션 미들웨어, 쿠키 설정, 로그인 UI.
>
> **Open:** 24시간이 지난 토큰 갱신은 검증되지 않음 — 해당 경로를 덮는 테스트가 없습니다.

</td>
</tr>
</table>

## 규칙

열 개입니다. 전문은 [SKILL.md](../../skills/i-have-ocd/SKILL.md).

1. 무엇이 바뀌었는지 정확히 밝힌다 — 파일, 줄, 심볼.
2. “아마 될 겁니다”는 금지. 검증했거나, 검증하지 않았다고 명시하거나.
3. 완료 또는 미완료. 세 번째 상태는 없다.
4. 건드리지 않은 것을 밝힌다.
5. 선택지 목록이 아니라 하나의 답을 준다.
6. 미확인 항목은 `Open:` 목록 한 곳에 모은다 — 비어 있으면 `none`이라고 쓴다.
7. 안심시키지 않는다. 대신 출력을 보여준다.
8. 오류에는 정확한 원인을. 증상을 되풀이하는 것은 원인이 아니다.
9. 빈말로 맞장구치지 않는다.
10. 모든 답변에 범위를 명시한다 — 무엇을 포함하고 무엇을 포함하지 않는지.

그리고 열 개 모두보다 우선하는 규칙 하나: **정확함은 지어내는 것이 아니다.** 읽지 않은 줄 번호를 만들어내지 말 것.

## 이름에 대하여

농담인 것은 이름뿐입니다. 스킬 자체는 농담이 아니며, 의도적으로 안심시키지 않습니다. 안심을 구하는 행위가 곧 강박이지 치료가 아니기 때문입니다. 대신 이 스킬은 검증되지 않은 주장을 그대로 두기를 거부합니다. 이는 어떤 독자에게나 도움이 되는 일이며, 기본 설정의 어떤 어시스턴트도 해주지 않는 일입니다.

## 직접 손보기

포크한 뒤 `skills/i-have-ocd/SKILL.md`를 수정하고, 자신의 사본으로 교체하세요:

```bash
claude plugin uninstall i-have-ocd            # 먼저 원본 사본을 제거합니다:
claude plugin marketplace remove i-have-ocd   # 포크와 원본은 두 이름을 모두 공유합니다
claude plugin marketplace add <your-username>/i-have-ocd
claude plugin install i-have-ocd@i-have-ocd
```

코딩 어시스턴트를 재시작한 뒤 `/i-have-ocd`를 다시 호출하세요.

## 기여하기

번역 기여를 특히 환영합니다 — [CONTRIBUTING.md](../../CONTRIBUTING.md)를 참고하세요.

## 크레딧

이 저장소의 형태 — 하나의 `SKILL.md`, 전후 비교 표, 에이전트별 설치 경로 — 는 [Ayoub Ghriss](https://github.com/ayghri)의 [i-have-adhd](https://github.com/ayghri/i-have-adhd)를 따랐습니다. 그쪽이 먼저였고 MIT 라이선스입니다. 여기의 규칙은 처음부터 새로 썼고 방향은 정반대입니다. 그 스킬은 *시작하기*에 최적화되어 있고(행동을 먼저, 나머지는 잘라내기), 이 스킬은 *끝맺기*에 최적화되어 있습니다(검증되지 않은 것 없이, 범위가 불분명한 것 없이). 서로 잘 맞으니 둘 다 설치하세요.

## 라이선스

[MIT](../../LICENSE).

“잠깐, 테스트 진짜 돌린 거 맞아?”를 한 번 줄여줬다면 ⭐ 부탁드립니다.

</div>
