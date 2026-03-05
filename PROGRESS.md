# PROGRESS.md

## 개요

이 문서는 지금까지 완료된 작업과 인수인계 메모를 기록한다.
새 작업을 시작하는 에이전트는 반드시 이 문서를 읽고 현재 상태를 파악한 뒤 작업을 이어간다.

---

## 현재 상태 요약

- 앱 형태: `단일 HTML 파일 기반 브라우저 앱`
- 메인 엔트리: `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 현재 목적: 관상용 3D 디지털 수족관의 심미성, 몰입감, 상호작용 품질 고도화
- 협업 문서:
  - `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`

---

## 완료 기록

### 2026-03-05

#### DOC-001

- 완료 내용
  - 프로젝트 운영 규칙 문서 `AGENTS.md`를 생성했다.
  - 프로젝트 목적, 현재 폴더 구조, 권장 확장 구조, 기본 동작, 구현/디자인/검증 룰을 정리했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
- 검증
  - 파일 생성 및 내용 확인 완료
- 인수인계 메모
  - 이후 구조가 바뀌면 `AGENTS.md`도 반드시 함께 갱신해야 한다.

#### DOC-002

- 완료 내용
  - 멀티 에이전트 협업을 위한 `PLAN.md`, `PROGRESS.md` 운영 체계를 도입했다.
  - `AGENTS.md`에 작업 시작 전 `AGENTS.md`, `PLAN.md`, `PROGRESS.md`를 읽고 갱신하도록 규칙을 추가했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
- 검증
  - 세 문서 생성/수정 완료
- 인수인계 메모
  - 다음 작업부터는 반드시 작업 종료 시 `PLAN.md` 상태와 `PROGRESS.md` 기록을 함께 갱신한다.

#### DOC-004

- 완료 내용
  - 외부 검색 기반 레퍼런스를 저장하기 위한 `references/` 폴더를 생성했다.
  - 아쿠아스케이프 미학 자료와 Three.js 구현 자료를 요약해 저장했다.
  - 조사 결과를 바탕으로 개선 로드맵 문서를 작성하고 `PLAN.md`, `AGENTS.md`에 반영했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/references/README.md`
  - `/Users/friends/ai/aquagarden_2026_codex/references/2026-03-05-aquascape-aesthetics.md`
  - `/Users/friends/ai/aquagarden_2026_codex/references/2026-03-05-rendering-and-experience.md`
  - `/Users/friends/ai/aquagarden_2026_codex/references/2026-03-05-improvement-roadmap.md`
- 검증
  - 문서 생성 및 내용 확인 완료
- 인수인계 메모
  - 다음 작업은 `AQ-101`부터 시작하는 것이 가장 자연스럽다.
  - 구현 전 `references/2026-03-05-improvement-roadmap.md`를 먼저 보고 단계별로 반영할 것.

#### DOC-005

- 완료 내용
  - 프로젝트 작업을 위한 커맨드 구조를 설계했다.
  - 프로젝트 전용 스킬 `skills/aquagarden-project/`를 생성했다.
  - 스킬 안에 `command-structure.md`, `task-routing.md`를 작성해 요청 유형별 작업 흐름을 정리했다.
  - `AGENTS.md`에 `skills/` 폴더와 운영 규칙을 반영했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/skills/aquagarden-project/SKILL.md`
  - `/Users/friends/ai/aquagarden_2026_codex/skills/aquagarden-project/agents/openai.yaml`
  - `/Users/friends/ai/aquagarden_2026_codex/skills/aquagarden-project/references/command-structure.md`
  - `/Users/friends/ai/aquagarden_2026_codex/skills/aquagarden-project/references/task-routing.md`
- 검증
  - 스킬 구조 생성 완료
  - `quick_validate.py` 실행 결과 `Skill is valid!`
- 인수인계 메모
  - 이후 반복 작업은 가능하면 `skills/aquagarden-project/`의 명령 흐름을 기준으로 진행한다.

#### DOC-006

- 완료 내용
  - 프로젝트 전용 스킬 `aquagarden-project`를 사용자 스킬 경로에 설치했다.
  - 스킬 로컬 사본과 설치 사본 모두 유지되도록 정리했다.
- 변경 파일
  - `/Users/friends/.codex/skills/aquagarden-project`
- 검증
  - `quick_validate.py` 기준 구조 유효성 확인 완료
- 인수인계 메모
  - 새 세션에서 스킬을 안정적으로 인식하려면 Codex 재시작이 필요하다.

#### AQ-108

- 완료 내용
  - 사용자 피드백을 반영해 `물고기 형태와 유영 현실화 1차 패스`를 시작했다.
  - 물고기 본체를 단순 구/원뿔 조합에서 곡선 기반 실루엣과 분절 꼬리 구조로 교체했다.
  - 어종별 유영 로직에 군영 중심 이동, 개체 간 간격 유지, 부드러운 방향 전환, 몸통/꼬리 위상 차 애니메이션을 추가했다.
  - 물고기 개체 수를 줄이고 속도를 재조정해 풍경을 덜 압도하도록 조정했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-realism-pass.png`
    - `/Users/friends/ai/aquagarden_2026_codex/aq-realism-pass-v2.png`
- 인수인계 메모
  - 현재 패스는 `프리미티브 느낌 완화` 단계다. 완전한 현실감을 원하면 다음 단계에서 `glTF` 또는 스킨드 메시 기반 어종 교체를 검토해야 한다.
  - 특히 엔젤피시는 여전히 평면적이어서 추가 개선 우선순위가 높다.

#### AQ-109

- 완료 내용
  - 메인 유목에 보조 가지와 잔가지를 추가해 실루엣 밀도를 높였다.
  - 유목 표면에 활착 이끼 느낌의 작은 군락을 추가해 하드스케이프 연결감을 보강했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - Playwright 캡처 기준으로 기존보다 유목 실루엣이 풍성해진 것 확인
- 인수인계 메모
  - 현재는 `TubeGeometry` 기반이라 가지 끝 taper가 제한적이다. 다음 패스에서는 굵기 감소가 있는 브랜치 생성 방식 또는 외부 모델 사용을 검토한다.

#### AQ-110

- 완료 내용
  - 수초 블레이드에 곡률과 테이퍼를 추가해 평면 종이 느낌을 줄였다.
  - 바위 지오메트리 분할 수를 높이고 변형 강도를 조정해 표면을 조금 더 자연스럽게 만들었다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - Playwright 캡처 기준으로 수초와 바위의 직선적/각진 느낌이 일부 완화됨
- 인수인계 메모
  - 절차 생성 기반 한계가 아직 뚜렷하다. 더 높은 현실감이 필요하면 텍스처, 노멀, 자산 교체를 우선 검토한다.

#### AQ-108 추가 기록

- 완료 내용
  - 물고기 현실감 2차 패스를 진행했다.
  - 네온 테트라와 앰버 라스보라 본체를 더 매끈한 곡면 몸체로 교체하고, 종별 피부 텍스처와 광택 레이어를 추가했다.
  - 입, 아가미, 반투명 지느러미 디테일을 넣어 얼굴과 실루엣의 장난감 느낌을 줄였다.
  - 엔젤피시는 몸체 비율과 크기를 다시 조정해 과도한 존재감을 낮췄다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-realism-pass-v3.png`
    - `/Users/friends/ai/aquagarden_2026_codex/aq-realism-pass-v4.png`
- 인수인계 메모
  - 현재 단계는 `절차 생성으로 가능한 현실감 상한`에 가까워지고 있다.
  - 더 높은 완성도를 원하면 다음 단계에서 `glTF` 물고기 자산 도입 또는 어종 수 축소 후 디테일 집중 중 하나를 선택하는 것이 효율적이다.

#### AQ-109 추가 기록

- 완료 내용
  - 유목 현실감 2차 패스를 진행했다.
  - `TubeGeometry` 기반 가지를 taper가 있는 세그먼트 브랜치로 교체해 끝으로 갈수록 가늘어지는 실루엣을 만들었다.
  - 절차 생성 목재 텍스처와 활착 잎 클러스터를 추가해 유목 표면 밀도와 자연스러운 연결감을 높였다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-hardscape-pass-v1.png`
    - `/Users/friends/ai/aquagarden_2026_codex/aq-hardscape-pass-v3.png`
- 인수인계 메모
  - 현재는 메인 유목이 더 자연스러워졌지만, 전체 레이아웃과의 명도 대비는 아직 추가 조정 여지가 있다.

#### AQ-110 추가 기록

- 완료 내용
  - 수초와 바위 현실감 2차 패스를 진행했다.
  - 넓은 잎 형태의 식재 변형을 추가해 군락 실루엣 반복을 줄였다.
  - 바위를 더 매끈한 메시로 바꾸고 rock texture를 절차 생성 방식으로 갱신해 각진 느낌을 완화했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-hardscape-pass-v2.png`
    - `/Users/friends/ai/aquagarden_2026_codex/aq-hardscape-pass-v3.png`
- 인수인계 메모
  - 바위 형상은 개선됐지만 현재 캡처 기준으로 명도가 다소 낮다. 다음 패스에서 조명 또는 색 밸런스 조정과 함께 다루는 편이 좋다.

#### AQ-103

- 완료 내용
  - 조명 시스템을 `프리셋 + 슬라이더` 구조로 확장했다.
  - `중성 낮`, `차분한 아침`, `몽환적 저녁` 3개 프리셋을 추가하고, 각 프리셋이 밝기/색온도/배경/안개/노출/광원 위치를 함께 바꾸도록 구성했다.
  - 상부 shimmer 조명을 추가해 수조 상면 하이라이트를 더 자연스럽게 만들었다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 프리셋 버튼 클릭 시 슬라이더/라벨 동기화 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-lighting-day.png`
    - `/Users/friends/ai/aquagarden_2026_codex/aq-lighting-morning.png`
    - `/Users/friends/ai/aquagarden_2026_codex/aq-lighting-dusk.png`
- 인수인계 메모
  - 저녁 프리셋은 분위기 차이는 확실하지만, 하드스케이프 명도가 함께 낮아진다. 이후 `AQ-102`나 `AQ-101`과 맞물려 미세 조정하면 좋다.

#### AQ-108 추가 기록 2

- 완료 내용
  - 물고기 유영 정교화 3차 패스를 진행했다.
  - 종별 pace 변화, surge 리듬, lane 기반 수심 유지, obstacle avoidance를 넣어 물고기가 바위와 하드스케이프를 덜 관통하게 조정했다.
  - 엔젤피시는 더 느리고 떠 있는 느낌으로, 네온은 조금 더 군영감 있게 조정했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 조명 프리셋 검증 캡처에서도 물고기 유영 상태 함께 확인
- 인수인계 메모
  - 현재 움직임은 이전보다 자연스럽지만, 여전히 `풍경 중심 구성` 관점에서는 일부 장면에서 물고기 존재감이 조금 강하다. 다음에는 `AQ-102`와 연동해 어종 수/채도/배치를 같이 정리하는 편이 맞다.

#### AQ-109 추가 기록 2

- 완료 내용
  - 사용자 피드백을 반영해 유목 존재감을 다시 상향했다.
  - 메인 가지 굵기와 명도를 높이고 목재 텍스처를 밝게 조정해 장면 안에서 더 분명히 읽히도록 수정했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-feedback-brighter.png`
- 인수인계 메모
  - 존재감은 확실히 좋아졌지만, 이후 `AQ-101`을 다시 잡을 때 유목 포컬 포인트 위치를 같이 검토하는 편이 좋다.

#### AQ-109 추가 기록 3

- 완료 내용
  - 사용자 피드백에 맞춰 유목 밀도를 다시 높였다.
  - 메인 유목 하부와 후방에 추가 분지를 넣어 화면에서 읽히는 목재 질량을 키웠다.
  - 유목 접합부와 가지 아래에 녹색 이끼 클러스터와 늘어지는 이끼 커튼을 추가해 더 자연스러운 활착 느낌을 만들었다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-driftwood-moss-v1.png`
- 인수인계 메모
  - 유목 존재감은 이전보다 분명히 좋아졌지만, 이후 `AQ-101`을 재개할 때 메인 포컬 포인트와 수영 공간을 침범하지 않는지 같이 점검하는 편이 맞다.

#### AQ-102

- 완료 내용
  - 풍경 중심 감상을 위해 붉은 수초 군락을 단일 포컬 클러스터로 축소했다.
  - 붉은 수초 팔레트를 저채도 톤으로 조정해 화면 내 색 충돌을 줄였다.
  - 물고기 개체 수, 스케일, 기본 속도를 낮추고 종별 personal space를 넓혀 과밀감을 완화했다.
  - 네온 테트라/앰버 라스보라의 텍스처와 지느러미 색을 완화해 시선 과집중을 줄였다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - 현재 샌드박스 정책상 로컬 서버 포트 바인딩이 차단되어 Playwright 시각 검증은 이번 턴에서 수행하지 못함
- 인수인계 메모
  - 사용자 환경에서 브라우저로 한 번 확인해 물고기 존재감이 충분히 낮아졌는지 최종 튜닝하는 것이 좋다.
  - 다음 자연스러운 작업은 `AQ-101` 재개(구도/여백 정리) 또는 `AQ-104` 관상 모드 UX 추가다.

#### AQ-109 추가 기록 4

- 완료 내용
  - 사용자가 제공한 레퍼런스 이미지(`/Users/friends/ai/aquagarden_2026_codex/reference.png`)를 기준으로 유목 실루엣을 재조정했다.
  - 좌측에서 우측 상단으로 뻗는 아치형 가지와 세부 잔가지를 추가해 상부 유목 존재감을 강화했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-reference-inspired-v3.png`
- 인수인계 메모
  - 유목 방향성과 상단 실루엣은 레퍼런스와 더 가까워졌고, 이후에는 구도(`AQ-101`)와 함께 포컬 지점 위치를 미세조정하면 좋다.

#### AQ-110 추가 기록 3

- 완료 내용
  - 레퍼런스 이미지 기준으로 수초/바위 구성을 보강했다.
  - 좌측 대형 바위에 이끼 패치와 이끼 쿠션(볼륨)을 추가해 녹색 덩어리감을 만들었다.
  - 우측 바위를 더 납작한 레이어 형태로 조정하고, 우측 붉은 수초 위치를 전진시켜 시인성을 높였다.
  - 전경 잔디와 바위 상단 군락 수초를 추가해 식재 밀도를 끌어올렸다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-reference-inspired-v3.png`
- 인수인계 메모
  - 현재 단계는 레퍼런스 반영 1차로, 다음에는 조명 프리셋별 명도 차이를 줄이면서 이끼/바위 대비를 더 자연스럽게 정리하는 것이 좋다.

#### AQ-109 추가 기록 5

- 완료 내용
  - 유목 그룹에 전역 스케일과 위치 보정(`+25%`)을 적용해 포컬 질량을 키웠다.
  - 상단 포컬 실루엣 강화를 위해 중간 가지 2개와 잔가지 3개를 추가했다.
  - 이끼/활착 표현은 `addMossCluster`, `addMossCurtain`, `addAttachedLeafCluster` 내부 밀도 스케일로 상향했다.
  - 유목 관통 완화를 위해 상부 분지 영역에 `swimObstacles` 2개를 추가했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-plan-implement-v1.png`
- 인수인계 메모
  - 유목 존재감은 크게 올라갔고, 이후 `AQ-101`에서 메인 포컬 위치와 시선 흐름을 다시 정렬하면 완성도가 더 좋아진다.

#### AQ-110 추가 기록 4

- 완료 내용
  - 식재 생성 함수 `createPlantCluster`에 군락 분포 파라미터(`clusterBias`, `edgeFade`, `heightJitter`)를 추가했다.
  - 식재 생성 시 `isOpenPathZone` 기반 통로 보호를 적용해 자연 군락형 밀도를 유지하면서 수영 공간을 보호했다.
  - 좌측 이끼 언덕의 패치 밀도를 1.5배로 올리고 이끼 쿠션 2개를 추가해 볼륨을 확장했다.
  - 전경/중앙/우측 완충 식재 카운트를 계획 비율로 상향했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-plan-implement-v1.png`
- 인수인계 메모
  - 현재는 데스크톱 우선 밀도 기준이며, 성능 이슈가 나오면 전경 잔디 → 이끼 커튼 순으로 감산하는 것이 안전하다.

#### AQ-108 추가 기록 3

- 완료 내용
  - 물고기 유영을 `cruise/school/split` 상태 기반으로 확장했다.
  - species 설정에 군영 이벤트 파라미터(`schoolEventInterval`, `schoolEventDuration`, `schoolParticipation`, `schoolCohesionBoost`, `schoolLeaderWeight`, `dispersionAfterSchool`)를 추가했다.
  - 네온 9, 앰버 5, 엔젤 2 구성으로 조정하고, 버킷 단위 부분 군영 이벤트를 도입했다.
  - 군영 종료 후 분산 복귀(`split`)와 프레임당 속도 변화 제한(speed clamp)을 넣어 움직임 급변을 완화했다.
  - 군영 중에는 35% 위상 동기화를 적용해 완전 동기화로 보이지 않도록 조정했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 40초 관찰 기준 군영→분산 전환 동작 확인
  - 조명 프리셋 버튼 회귀 확인(`중성 낮/차분한 아침/몽환적 저녁`)
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-plan-implement-v1.png`
- 인수인계 메모
  - 현재 군영 강도는 중간 설정이며, 추가 튜닝 시 `schoolParticipation`와 `dispersionAfterSchool`부터 조정하는 것이 영향 대비 안전하다.

#### AQ-110 추가 기록 2

- 완료 내용
  - 사용자 피드백을 반영해 전반 광량과 바위 명도를 상향했다.
  - rock texture의 암부를 완화하고 조명/안개/배경 값을 밝게 조정해 장면이 지나치게 가라앉지 않도록 수정했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 추출 스크립트 기준 `node --check` 통과
  - Playwright 브라우저 로드 확인
  - 콘솔 메시지 `0`건
  - 캡처 저장
    - `/Users/friends/ai/aquagarden_2026_codex/aq-feedback-brighter.png`
- 인수인계 메모
  - 현재 밝기 밸런스는 이전보다 낫지만, 저녁 프리셋에서는 여전히 다소 무거울 수 있다. 이후 `AQ-102` 색 조정과 함께 세밀하게 맞추는 편이 좋다.

#### DOC-007

- 완료 내용
  - GitHub 업로드를 위해 저장소용 `.gitignore`를 추가했다.
  - 검증 캡처와 임시 출력물이 원격 저장소에 불필요하게 포함되지 않도록 정리했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/.gitignore`
- 검증
  - 파일 생성 완료
- 인수인계 메모
  - 현재 `.gitignore`는 작업 중 생성되는 캡처 이미지와 `output/` 디렉토리를 제외한다.

#### DOC-003

- 완료 내용
  - 업로드용 `README.md`를 작성했다.
  - 프로젝트 소개, 실행 방법, 주요 파일, 현재 방향을 정리했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/README.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
- 검증
  - 파일 생성 및 내용 확인 완료
- 인수인계 메모
  - 저장소 첫 화면에서 바로 실행 방법을 확인할 수 있는 최소 문서 수준이다.

#### DOC-008

- 완료 내용
  - 로컬 프로젝트를 Git 저장소로 초기화했다.
  - 원격 `https://github.com/outliner-coach/aquagarden_codex.git`를 연결하고 `main` 브랜치로 push했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/.git`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
- 검증
  - Git 커밋 생성 완료
  - `main -> main` push 성공
  - 원격 추적 브랜치 설정 완료
- 인수인계 메모
  - 현재 커밋 해시는 `903ffa2`다.

#### DOC-009

- 완료 내용
  - GitHub Pages 기본 경로에서 바로 앱이 열리도록 메인 파일명을 `index.html`로 변경했다.
  - 문서와 프로젝트 스킬에서 메인 엔트리 경로 참조를 `index.html`로 통일했다.
  - `.nojekyll` 파일을 추가해 GitHub Pages가 정적 루트의 `index.html`을 직접 서빙하도록 고정했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
  - `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/README.md`
  - `/Users/friends/ai/aquagarden_2026_codex/.nojekyll`
  - `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - `/Users/friends/ai/aquagarden_2026_codex/skills/aquagarden-project/SKILL.md`
- 검증
  - `node --check` 기준 모듈 스크립트 문법 검사 통과
  - 로컬 실행 URL을 `http://127.0.0.1:4173/index.html`로 업데이트
- 인수인계 메모
  - GitHub Pages가 활성화되면 저장소 루트 주소에서 자동으로 `index.html`을 서빙한다.

### 2026-02-22

#### APP-001

- 완료 내용
  - 브라우저만으로 실행 가능한 3D 디지털 수족관 앱의 초기 버전을 구현했다.
  - 단일 HTML 파일 안에 Three.js 기반 씬, 수조, 바위, 유목, 수초, 물고기, 기포, 조명 UI, 명언 패널을 구성했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 브라우저에서 로드 가능한 상태로 저장됨
- 인수인계 메모
  - 현재 구조는 단일 파일이므로 기능 추가 시 코드 탐색 비용이 크다. 큰 확장 전에는 구조 분리 여부를 먼저 판단할 것.

#### APP-002

- 완료 내용
  - 물고기 3종 이상, 자유 유영, 지느러미/꼬리 애니메이션, 수초 흔들림, 기포 상승, 조명 제어, 클릭 명언 표시를 구현했다.
- 변경 파일
  - `/Users/friends/ai/aquagarden_2026_codex/index.html`
- 검증
  - 시각 미리보기 이미지 생성
- 관련 파일
  - `/Users/friends/ai/aquagarden_2026_codex/aquarium-preview.png`
  - `/Users/friends/ai/aquagarden_2026_codex/aquarium-preview-final.png`
- 인수인계 메모
  - 기능은 동작하지만 관상용 미감 기준으로는 구도, 색 절제, 광원 연출이 아직 개선 여지가 크다.

---

## 다음 작업자를 위한 메모

- 현재 가장 자연스러운 다음 단계는 `심미성 개선`이다.
- 사용자 피드백 이후 우선순위는 `AQ-108`, `AQ-109`, `AQ-110` 후 `AQ-101` 순서로 바뀌었다.
- 조사 기반 판단은 `references/` 폴더 문서를 우선 참고한다.
- 큰 변경 전에는 `index.html`의 단일 파일 유지 여부를 먼저 판단한다.
- 시각 조정 작업은 가능하면 브라우저 확인과 캡처를 함께 남긴다.
- `AQ-101`은 1차 구도 패치가 들어가 있지만 현재는 사용자 피드백 때문에 보류 상태다.
