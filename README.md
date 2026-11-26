# Animated Web Deck

일러스트와 모션이 있는 브라우저용 발표 교안을 제작하는 Agent Skill입니다. 디자인 레퍼런스 선택, 표지와 본문 디자인, 단계별 공개, 슬라이드를 열어 둔 동안의 움직임, 발표자 조작과 화면 검증을 안내합니다.

## Codex와 Claude Code에 설치

`gh skill`을 지원하는 [GitHub CLI](https://cli.github.com/)가 필요합니다. 사용할 앱에 해당하는 명령을 실행하면 해당 PC의 사용자 범위에 설치됩니다.

**Codex**

```sh
gh skill install unono915/animated-web-deck animated-web-deck --agent codex --scope user
```

**Claude Code**

```sh
gh skill install unono915/animated-web-deck animated-web-deck --agent claude-code --scope user
```

새 세션을 열고 Codex에서는 `$animated-web-deck`, Claude Code에서는 `/animated-web-deck`으로 불러옵니다. 설치한 버전은 `gh skill list`로 확인하고, 새 버전이 나오면 `gh skill update animated-web-deck`으로 갱신합니다.

## 사용 예시

> 웹 교안으로 만들어 줘. 이 링크의 표지 배치와 일러스트 분위기를 참고하고, 절차를 설명하는 슬라이드는 발표자가 한 단계씩 공개할 수 있게 해 줘.

링크 없이 시작하면 교안에 맞는 디자인 방향을 고를 수 있습니다. 본문과 참조 문서는 [스킬 폴더](skills/animated-web-deck)에 있습니다.
