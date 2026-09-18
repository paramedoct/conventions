---
name: bash
description: Bash 명령 파일과 모듈 파일을 작성하거나 수정할 때 공용 개발 규약을 적용한다.
---

# Bash 지침

## 적용 범위

Bash 파일을 새로 만들거나 수정할 때 이 지침을 적용한다.

## 규약

- `bash 3.2`을 기준으로 작성한다.
- 명령 파일은 사용자가 직접 실행하는 스크립트로 정의한다.
- 명령 파일은 저장소 루트 디렉터리에 배치한다.
- 명령 파일 이름은 확장자 없는 소문자 단일 단어로 정한다.
- 명령 파일에는 큰 논리적 흐름만 남긴다.
- 모듈 파일은 도메인 로직이 구현된 스크립트로 정의한다.
- 모듈 파일은 `utils` 디렉터리에 배치한다.
- 모듈 파일 이름은 확장자 없는 단일 단어로 정한다.
- 모듈 함수 이름은 `module_action()` 형식으로 정한다.
- 결과는 표준 출력으로 내보낸다.
- 진단은 표준 오류로 내보낸다.

## 기준 형태

```bash
#!/usr/bin/env bash
set -euo pipefail
ROOT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"

usage() {
  echo "$0 <target>" >&2
  exit 1
}

# shellcheck source=/dev/null
source "$ROOT_DIR/utils/source.sh"
source_modules \
  utils/profile.sh \
  utils/target.sh

main() {
  local target
  [ "$#" -eq 1 ] || usage
  target=$1
  profile_prepare
  target_run "$target"
}

main "$@"
```
