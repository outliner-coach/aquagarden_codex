# Command Structure

이 문서는 AquaGarden 프로젝트에서 에이전트가 사용할 작업 명령 구조를 정의한다.
명령은 셸 커맨드가 아니라 `작업 모드`다.

## Core Commands

### `/status`
목적:
- 현재 상태를 빠르게 복원한다.

수행:
- `AGENTS.md`, `PLAN.md`, `PROGRESS.md`를 읽는다.
- 필요하면 프로젝트 `references/`를 훑는다.
- 현재 엔트리 파일과 다음 우선 작업을 요약한다.

출력:
- 현재 상태 요약
- 이어서 할 작업 1~3개

파일 갱신:
- 없음

### `/plan`
목적:
- 사용자 요청을 작업 항목으로 연결한다.

수행:
- 요청을 기존 작업 ID에 매핑한다.
- 없으면 `PLAN.md`에 새 작업을 추가한다.
- 하나의 대표 작업을 `in_progress`로 둘지 판단한다.

출력:
- 이번 턴에서 다룰 작업 범위
- 완료 기준

파일 갱신:
- `PLAN.md`

### `/research <topic>`
목적:
- 최신 근거가 필요한 내용을 조사한다.

수행:
- 웹 검색 후 핵심 인사이트를 정리한다.
- 결과를 프로젝트 `references/`에 날짜 기반 문서로 저장한다.
- 조사 결과가 우선순위를 바꾸면 `PLAN.md`를 갱신한다.

출력:
- 핵심 인사이트
- 프로젝트 적용 메모

파일 갱신:
- `references/*.md`
- 필요 시 `PLAN.md`

### `/implement <task-id>`
목적:
- 특정 작업을 실제 파일 변경으로 수행한다.

수행:
- 한 번에 하나의 주 작업을 중심으로 구현한다.
- 필요하면 작은 하위 단계로 나눠 진행한다.
- 디자인 작업은 구도, 색, 조명, 움직임 우선순위를 지킨다.

출력:
- 구현 결과
- 수정 파일

파일 갱신:
- 코드/문서 파일
- 필요 시 `PLAN.md`

### `/verify`
목적:
- 변경 내용을 빠르게 검증한다.

수행:
- 브라우저 로드 확인
- 콘솔 확인
- 관련 인터랙션 확인
- 시각 변화가 크면 캡처 저장

출력:
- 검증 결과
- 남은 리스크

파일 갱신:
- 필요 시 캡처 파일
- 필요 시 `PROGRESS.md`

### `/handoff`
목적:
- 다음 에이전트가 즉시 이어받을 수 있게 상태를 정리한다.

수행:
- 완료/중단 상태를 `PLAN.md`에 반영한다.
- `PROGRESS.md`에 완료 내용, 검증 결과, 다음 액션을 남긴다.
- 구조 규칙이 바뀌면 `AGENTS.md`도 갱신한다.

출력:
- 완료 요약
- 다음 액션

파일 갱신:
- `PLAN.md`
- `PROGRESS.md`
- 필요 시 `AGENTS.md`

## Recommended Sequences

### 조사 중심 요청
`/status -> /research -> /plan -> /handoff`

### 구현 중심 요청
`/status -> /plan -> /implement -> /verify -> /handoff`

### 짧은 문서 작업
`/status -> /implement -> /handoff`

### 구조 변경 작업
`/status -> /plan -> /implement -> /verify -> /handoff`
그리고 필요 시 `AGENTS.md`도 함께 갱신한다.
