---
name: python
description: Python 코드 작업에 공용 개발 규약을 적용한다.
---

### Python
- 버전: 프로젝트에서 명시한 Python 버전
- 명령 파일은 사용자가 직접 실행하는 스크립트로 정의한다
- 명령 파일에는 큰 논리적 흐름만 남겨라
- 모듈 파일은 재사용할 로직이 구현된 파일로 정의한다
- 메서드는 다음 형식으로 명명하라: `snake_case`
- 클래스는 다음 형식으로 명명하라: `PascalCase`
- 타입을 명시하라
- ruff `target-version`: 프로젝트의 Python 버전
- mypy `python_version`: 프로젝트의 Python 버전
- 다음 검사를 통과하라

```bash
ruff check .
ruff format --check .
mypy --strict .
```
