---
name: python
description: Python 작업에 코드 컨벤션을 적용한다.
---

### Python
- 버전: 프로젝트에서 명시한 Python 버전
- 타입을 명시하라
- 다음 검사를 통과하라

```bash
ruff check .
ruff format --check .
mypy --strict .
```
