---
name: bash
description: Bash 작업에 코드 컨벤션을 적용한다.
---

### Bash
- 버전: `bash 3.2`
- 명령 파일은 사용자가 직접 실행하는 스크립트로 정의한다
- 명령 파일은 저장소 루트 디렉터리에 배치하라
- 명령 파일은 확장자 없이 소문자 단일 단어로 명명하라
- 명령 파일에는 큰 논리적 흐름만 남겨라 
- 모듈 파일은 도메인 로직이 구현된 스크립트로 정의한다
- 모듈 파일은 다음 디렉터리에 배치하라: `utils`
- 모듈 파일은 다음 형식으로 명명하라: `module` 
- 모듈 함수는 다음 형식으로 명명하라: `module_action()`
- 결과는 표준 출력으로 내보내라
- 진단은 표준 오류로 내보내라
- 빈 행은 최상위 구획을 구분할 때만 사용하라
- 다음 형태를 기준으로 삼아라

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
