# Seedance 2.0 Skill OS 빠른 시작

> 버전 6.6.0 · 설치부터 첫 "연출된" 프롬프트까지 약 5분.
> 자세한 내용은 [README](../README.md) 와 [한국어 가이드](README.ko.md) 참고.

## 이게 뭔가요

Seedance 2.0 Skill OS 는 형용사를 쌓는 대신 영화감독처럼 Seedance 2.0 을 연출하는 agent skill 입니다. 원칙은 하나——**모델을 연출하되, 프레임을 세세히 조작하지 마세요.** 장면이 "무엇을 하고 있는지"를 말하면, 그 의도를 바로 쓸 수 있는 프롬프트로 컴파일합니다.

## 1. 설치 (약 5분)

이 저장소를 `seedance-20` 라는 **하나의** 루트 스킬로 설치하세요. 하위 스킬과 references 는 상대 경로로 자동 로드됩니다.

**Codex (원커맨드 설치 스크립트 제공):**

```bash
python scripts/install_codex_skill.py --force
```

저장소를 `~/.codex/skills/seedance-20`(또는 `$CODEX_HOME/skills/seedance-20`)로 복사합니다. Codex 를 재시작한 뒤 `$seedance-20` 를 호출하세요.

**GitHub 에서 설치 (저장소 URL 설치를 지원하는 클라이언트):**

```text
https://github.com/Emily2040/seedance-2.0
```

**수동 복사 (그 외 클라이언트):** 폴더를 클라이언트의 스킬 디렉터리에 이름 `seedance-20` 그대로 복사하세요. 흔한 위치(보장이 아니라 반드시 본인 클라이언트에서 확인)는 [README 설치 표](../README.md#install)에 있습니다. 예: Claude Code `.claude/skills/`, Cursor `.cursor/skills/`, GitHub Copilot `.github/skills/`, Windsurf `.windsurf/skills/`.

> 보안 우선: 신뢰하는 agent 클라이언트에만 설치하세요. 낯설거나 서드파티 agent 에서 쓰기 전에 [SECURITY.md](../SECURITY.md) 를 먼저 읽으세요.

## 2. 상황에 맞는 스킬 고르기

| 지금 가진 것 | 먼저 로드 |
|---|---|
| 막연한 아이디어 | `seedance-interview` |
| 명확한 장면 | `seedance-prompt` |
| 여러 클립의 이야기 | `seedance-sequence` |
| 승인된 클립의 다음 부분 | `seedance-continuation` |
| 품질이 나쁘거나 차단된 결과 | `seedance-troubleshoot` |
| 캐릭터·브랜드·유명인·실존 인물 | `seedance-copyright` |

## 3. 쓰기 전에 "연출"하기 —— 네 가지 질문

1. **이 장면은 무엇을 하고 있나?** 전환, 폭로, 감정, 아니면 제시인가?
2. **카메라는 그것을 어떻게 말하나?** 고립엔 와이드, 표정엔 클로즈업, 깨달음엔 푸시인.
3. **빛은 무엇을 하나?** 시간대, 강한/부드러운, 따뜻한/차가운 —— 모두 의도를 위해.
4. **소리는 무엇을 하나?** 거의 무음, 하나의 환경음, 혹은 한 줄의 대사.

## 4. 예시 하나

**장식적 (약함):**

```
웅장한 시네마틱 샷, 편지를 읽는 여성, 감성적, 아름다운 조명, 4K
```

**연출적 (강함):**

```
미디엄 클로즈업, 눈높이. 그녀가 편지를 내리자 두 손이 멎고, 느린 푸시인이 다가온다. 부드러운 창빛이 얼굴을 담담하게 유지한다. 거의 무음, 의자 긁히는 소리 하나.
```

## 5. 테이크를 아끼는 두 규칙

- **참조 태그는 적힌 그대로 유지** —— `[Image1]`, `[Video1]`, `[Audio1]`, `@图1`, `@视频1`. 번역하거나 형식을 바꾸지 마세요.
- **이야기 전체를 한 번에 생성하려 하지 마세요.** 먼저 Clip 01 을 생성하고, 그것이 "실제로" 어떻게 끝났는지 관찰한 뒤, 그 진짜 결말에서 Clip 02 를 쓰세요(`seedance-continuation`).

## 6. 안전

- **콘텐츠 안전:** 보호되는 캐릭터, 유명인, 브랜드, 로고, 노래, 또는 실존 인물의 얼굴·목소리를 쓴다면 다른 언어로 숨기지 말고 `seedance-copyright` 로 오리지널·라이선스·후반작업 대체안으로 바꾸세요.
- **agent 안전:** 이 패키지는 **네트워크 통신을 하지 않고 텔레메트리도 없습니다.** 스크립트는 결정론적이며 오프라인으로 동작합니다. API 키, 계정 쿠키, 비공개 소스를 신뢰하지 않는 agent 에 붙여넣지 마세요. [SECURITY.md](../SECURITY.md) 참고.

## 7. 더 깊이

- `references/directing-engine.md` — 장면을 읽고 하나의 의도를 고르기(35개 장르 예제).
- `references/capability-map.md` — 모델의 강점을 따르고 알려진 한계를 피해 설계.
- `references/api-workflow.md` — API, 제공자, 가격, 모델 ID(출처 날짜 표기).
- `references/examples-by-mode.md` — T2V, I2V, V2V, R2V, FLF2V, 편집, 확장 예시.

---

다른 언어: [English](QUICKSTART.md) · [中文](QUICKSTART.zh.md) · [日本語](QUICKSTART.ja.md) · [Español](QUICKSTART.es.md) · [Русский](QUICKSTART.ru.md)
