# conventions

Codex 및 Claude Code 환경에서 함께 사용하는 공용 개발 규약 플러그인입니다.

## 제공 기능

- `bash` 스킬: Bash 작업에 공용 개발 규약을 적용합니다.
- `setup` 스킬: 공용 개발 규약을 사용자 전체 지침으로 설치합니다.

## 사용

Codex 또는 Claude Code의 플러그인 설치 기능으로 `conventions` 플러그인을 설치합니다. 이 저장소를 직접 복제해 명령을 실행할 필요는 없습니다.

설치 후 `setup` 스킬을 호출하고 전역 지침 교체를 승인합니다. 기존 `~/.codex/AGENTS.md`와 `~/.claude/CLAUDE.md`는 타임스탬프가 붙은 백업 파일로 보존됩니다.
