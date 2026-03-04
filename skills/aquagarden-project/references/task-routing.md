# Task Routing

이 문서는 사용자 요청을 어떤 명령 흐름으로 처리할지 빠르게 결정하기 위한 예시 모음이다.

## Request -> Command Flow

### "지금 어디까지 됐어?"
- 사용 명령: `/status`
- 필요 시 후속: `/handoff`

### "무엇부터 해야 해?"
- 사용 명령: `/status -> /plan`

### "검색해보고 방향을 정해줘"
- 사용 명령: `/status -> /research -> /plan -> /handoff`

### "이 기능을 구현해줘"
- 사용 명령: `/status -> /plan -> /implement -> /verify -> /handoff`

### "미감을 더 좋게 만들어줘"
- 사용 명령: `/status -> /plan -> /implement -> /verify -> /handoff`
- 우선 검토 순서:
  1. 구도
  2. 색 팔레트
  3. 조명
  4. 움직임

### "문서를 정리해줘"
- 사용 명령: `/status -> /implement -> /handoff`

### "작업 인수인계 상태를 정리해줘"
- 사용 명령: `/status -> /handoff`

## Routing Notes

- 최신성이 필요한 주제는 항상 `/research`를 포함한다.
- 시각 결과가 달라지는 작업은 가능하면 `/verify`를 포함한다.
- 구현 없이 판단만 필요한 요청은 `/implement`를 생략한다.
- 새 작업이 생기면 `/plan` 단계에서 `PLAN.md`를 먼저 갱신한다.
