# conventions

Codex 및 Claude Code 환경에서 함께 사용하는 공용 개발 규약 플러그인입니다.

## 제공 기능

- `bash` 스킬: Bash 작업에 공용 개발 규약을 적용합니다.
- `python` 스킬: Python 작업에 공용 개발 규약을 적용합니다.
- `setup` 스킬: 공용 개발 규약을 사용자 전체 지침으로 설치합니다.

## 설치

### Codex

```bash
codex plugin marketplace add paramedoct/conventions
codex plugin add conventions@conventions
```

새 세션을 시작한 뒤 `$conventions:setup`을 호출합니다. 자세한 marketplace 사용법은 [OpenAI Docs](https://developers.openai.com/plugins/build/plugins)를 참고합니다.

### Claude Code

```bash
claude plugin marketplace add paramedoct/conventions
claude plugin install conventions@conventions
```

새 세션을 시작한 뒤 `/conventions:setup`을 호출합니다. 자세한 설치 방법은 [Claude Code 문서](https://code.claude.com/docs/en/discover-plugins)를 참고합니다.

`setup` 스킬은 전역 지침 교체 전에 승인을 요청합니다. 기존 `~/.codex/AGENTS.md`와 `~/.claude/CLAUDE.md`는 타임스탬프가 붙은 백업 파일로 보존됩니다.
