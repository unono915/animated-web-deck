# Animated Web Deck

일러스트와 모션이 있는 브라우저용 발표 교안을 제작하는 Agent Skill입니다. 디자인 레퍼런스 선택, 표지와 본문 디자인, 단계별 공개, 슬라이드를 열어 둔 동안의 움직임, 발표자 조작과 화면 검증을 안내합니다.

## Codex와 Claude Code에 설치

### GitHub 링크로 설치

로컬 Codex나 Claude Code에 아래처럼 요청하면 됩니다. 공개 ZIP을 내려받아 설치할 수 있어 GitHub CLI나 Git이 없어도 됩니다.

> https://github.com/unono915/animated-web-deck 에서 animated-web-deck 스킬을 이 PC의 사용자 범위에 설치해 줘. 릴리스 ZIP의 `skills/animated-web-deck` 폴더를 참조 문서까지 통째로 설치하고, 설치 경로를 알려 줘.

직접 설치하려면 [최신 릴리스](https://github.com/unono915/animated-web-deck/releases/latest)에서 **Source code (zip)**을 받아 압축을 풉니다. 그 안의 `skills/animated-web-deck` 폴더를 아래 위치에 복사합니다. `~`는 내 사용자 홈 폴더입니다.

| 앱 | 복사 후 `SKILL.md` 위치 |
|---|---|
| Codex | `~/.agents/skills/animated-web-deck/SKILL.md` |
| Claude Code | `~/.claude/skills/animated-web-deck/SKILL.md` |

### GitHub CLI로 설치

`gh skill`을 지원하는 [GitHub CLI](https://cli.github.com/)가 설치되어 있으면 아래 명령도 사용할 수 있습니다.

**Codex**

```sh
gh skill install unono915/animated-web-deck animated-web-deck --agent codex --scope user
```

**Claude Code**

```sh
gh skill install unono915/animated-web-deck animated-web-deck --agent claude-code --scope user
```

GitHub CLI로 설치한 버전은 `gh skill list`로 확인하고, 새 버전이 나오면 `gh skill update animated-web-deck`으로 갱신합니다.

설치 후 새 세션을 열고 Codex에서는 `$animated-web-deck`, Claude Code에서는 `/animated-web-deck`으로 불러옵니다.

## 사용 예시

> 웹 교안으로 만들어 줘. 이 링크의 표지 배치와 일러스트 분위기를 참고하고, 절차를 설명하는 슬라이드는 발표자가 한 단계씩 공개할 수 있게 해 줘.

링크 없이 시작하면 교안에 맞는 디자인 방향을 고를 수 있습니다. 본문과 참조 문서는 [스킬 폴더](skills/animated-web-deck)에 있습니다.
