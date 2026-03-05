# aquagarden_codex

브라우저만으로 실행 가능한 `3D 디지털 수족관` 프로젝트입니다.

현재 구현 범위:

- Three.js 기반 3D 수조 씬
- 물고기 3종 이상과 자유 유영 애니메이션
- 수초 흔들림, 기포 상승, 조명 제어
- 조명 프리셋: `중성 낮`, `차분한 아침`, `몽환적 저녁`
- 오브젝트 클릭 시 명언 표시

## 실행

정적 서버로 실행합니다.

```bash
cd /Users/friends/ai/aquagarden_2026_codex
python3 -m http.server 4173
```

브라우저에서 아래 주소를 엽니다.

```text
http://127.0.0.1:4173/index.html
```

## 주요 파일

- `/Users/friends/ai/aquagarden_2026_codex/index.html`
  - 메인 앱 엔트리. HTML/CSS/JavaScript가 한 파일에 들어 있습니다.
- `/Users/friends/ai/aquagarden_2026_codex/AGENTS.md`
  - 프로젝트 운영 규칙
- `/Users/friends/ai/aquagarden_2026_codex/PLAN.md`
  - 앞으로의 작업 계획
- `/Users/friends/ai/aquagarden_2026_codex/PROGRESS.md`
  - 완료 기록과 인수인계 메모
- `/Users/friends/ai/aquagarden_2026_codex/references/`
  - 조사 요약과 레퍼런스 메모

## 현재 방향

현재는 다음 항목을 우선적으로 다듬고 있습니다.

- 물고기 형태와 유영의 현실감
- 유목과 바위, 수초의 심미성
- 감상용 조명과 분위기 제어
