# agent-skills
[![skills.sh](https://skills.sh/b/pji2918/agent-skills)](https://skills.sh/pji2918/agent-skills)    
제가 쓰려고 만든 스킬들입니다.

## 주의사항

해당 스킬들은 재미로 만든 것입니다.  
토큰 절약이나 성능 향상(성능 하락 가능성도 있음)을 보장하지 않습니다.  
해당 스킬을 사용하여 발생하는 모든 피해의 책임은 사용자에게 있습니다.

## 포함된 스킬

- [`mayo`](./skills/mayo/): 한국어 출력을 간결하게(음슴체로) 만듭니다.
- [`code-editing`](./skills/code-editing/): 모든 코드 편집을 `code-editor` 서브에이전트에 위임하도록 합니다.
- [`terminal-exec`](./skills/terminal-exec/): 모든 터미널 명령 실행을 `terminal-exec` 서브에이전트에 위임하도록 합니다.

## 포함된 에이전트

- [`code-editor`](./agents/code-editor.md): 오케스트레이터가 넘긴 로직대로 코드를 작성/수정합니다. 명령은 실행하지 않습니다. (haiku)
- [`terminal-exec`](./agents/terminal-exec.md): 오케스트레이터가 넘긴 명령을 실행하고 결과를 보고합니다. 위험한 명령은 실행하지 않습니다. (haiku)

`code-editing`, `terminal-exec` 스킬은 같은 이름의 서브에이전트와 함께 써야 동작합니다.

## 설치 방법

### 스킬 설치

Node.js 및 npm이 설치되어 있다고 가정합니다.  
설치되어 있지 않다면 [여기](https://nodejs.org)에서 설치합니다.

터미널에 다음 명령어를 입력합니다.  
(`<스킬 이름>`을 설치하고 싶은 스킬로 바꿉니다)

```bash
npx skills add https://github.com/pji2918/agent-skills --skill <스킬 이름>
```

지시를 따릅니다. 끝!

### 서브에이전트 설치

`npx skills add`는 스킬만 설치합니다.  
서브에이전트는 [`agents/`](./agents/)의 `.md` 파일을 `~/.claude/agents/`(또는 프로젝트의 `.claude/agents/`)에 직접 복사합니다.
