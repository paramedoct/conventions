# conventions

Codex와 Claude Code에서 함께 사용하는 공용 개발 규약 플러그인입니다.

## 구성

- `instructions/AGENTS.md`: Codex용 전역 지침 원본
- `instructions/CLAUDE.md`: Claude Code용 전역 지침 원본. `AGENTS.md`를 가리키는 상대 심볼릭 링크입니다.
- `skills/bash`: Bash 작업에 적용할 언어별 지침
- `skills/setup`: 사용자 전체 지침 설치 절차

## 사용

Codex에서는 플러그인 디렉터리를 사용자 플러그인 경로에 복사합니다.

```bash
mkdir -p ~/.codex/plugins
cp -R /path/to/conventions ~/.codex/plugins/conventions
```

Claude Code에서는 플러그인 루트를 지정해 로컬 플러그인으로 불러옵니다.

```bash
claude --plugin-dir /path/to/conventions
```

전역 지침 설치는 `setup` 스킬을 호출한 뒤 승인합니다. 이 작업은 기존 `~/.codex/AGENTS.md`와 `~/.claude/CLAUDE.md`를 완전히 교체하며, 기존 파일은 타임스탬프가 붙은 백업 파일로 보존합니다.

```bash
./setup --force
```

## 검증

```bash
./test
```
