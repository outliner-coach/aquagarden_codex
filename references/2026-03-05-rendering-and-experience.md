# 2026-03-05 Rendering and Experience References

조사 날짜: 2026-03-05
목적: 수조의 시각 품질과 감상 경험을 높이기 위한 구현 레퍼런스 정리

## 핵심 인사이트

### 1. 색 관리가 먼저 맞아야 한다
- Three.js는 조명 계산을 선형 작업 색공간에서 하고, 출력은 `WebGLRenderer.outputColorSpace`를 통해 디스플레이용 색공간으로 변환한다.
- 후처리를 쓰면 `OutputPass`가 필요하다.

프로젝트 적용 메모:
- 현재 출력/톤매핑 설정을 점검하고, 후처리 도입 시 `EffectComposer + OutputPass`를 함께 넣는다.

### 2. HDR 환경광과 PMREM이 물/유리/젖은 바위 품질에 직접적이다
- `PMREMGenerator`는 환경광 텍스처를 PBR 재질에 적합한 형태로 전처리한다.
- 유리, 물 표면, 젖은 유목 같은 재질 표현에 중요하다.

프로젝트 적용 메모:
- 향후 HDRI 또는 절차 생성 환경을 넣고 PMREM으로 처리한다.
- 수면 하이라이트와 유리 반사 품질을 올리는 데 우선 사용한다.

### 3. Bloom은 약하게 써야 분위기만 좋아진다
- `UnrealBloomPass`는 품질과 성능을 고려한 bloom 구현이다.
- tone mapping이 켜져 있어야 한다.

프로젝트 적용 메모:
- 수면, 하이라이트, 기포에만 약하게 bloom이 느껴지도록 사용한다.
- 과한 bloom은 게임 느낌을 강하게 만들므로 강도는 낮게 유지한다.

### 4. Post-processing은 EffectComposer 기준으로 구성한다
- Three.js는 `EffectComposer` 기반 후처리 파이프라인을 제공한다.
- 감상 앱에는 bloom, vignette 성격의 마감, 약한 contrast 정리가 유효하다.

프로젝트 적용 메모:
- 첫 단계는 `RenderPass + UnrealBloomPass + OutputPass` 정도로 최소 구성한다.
- 이후 필요하면 AO나 subtle grain을 검토한다.

### 5. 반복 오브젝트는 InstancedMesh가 기본이다
- `InstancedMesh`는 동일 형상을 여러 번 렌더링할 때 draw call을 줄인다.
- 자갈, 기포, 수초 군락, 작은 장식물에 적합하다.

프로젝트 적용 메모:
- 현재 개별 메쉬로 처리된 요소가 있으면 instancing 전환 여지를 먼저 검토한다.
- 심미성 작업 후 성능이 떨어지면 가장 먼저 적용할 최적화다.

### 6. 거리 기반 디테일 감소는 LOD로 관리한다
- `LOD`는 거리별로 디테일 수준을 바꾸는 기본 메커니즘이다.
- 고해상도 하드스케이프나 복잡한 수초가 많아지면 유효하다.

프로젝트 적용 메모:
- 메인 포컬존 밖 식재나 후경 하드스케이프에 우선 적용한다.
- 관상용 앱 특성상 카메라 이동이 느리므로 LOD 전환을 부드럽게 설계한다.

### 7. 실제 모델 애니메이션은 GLTFLoader + AnimationMixer 조합이 표준이다
- `GLTFLoader`는 glTF 2.0과 다수의 PBR 확장을 지원한다.
- `AnimationMixer`는 오브젝트별 애니메이션 재생을 관리한다.

프로젝트 적용 메모:
- 물고기와 유목/식물 일부를 glTF 자산으로 교체할 경우 이 조합을 쓴다.
- 물고기 꼬리/지느러미 움직임을 보다 자연스럽게 만들 수 있다.

## 구현 우선순위 결론
- 단기: 색 관리 점검, 조명 밸런스, 약한 bloom
- 중기: PMREM 기반 환경광, 물/유리 재질 개선
- 중기: InstancedMesh/LOD 정리
- 장기: glTF 물고기 도입 및 AnimationMixer 기반 애니메이션

## 출처
- Three.js Color Management
  - https://threejs.org/manual/en/color-management.html
- Three.js PMREMGenerator
  - https://threejs.org/docs/pages/PMREMGenerator.html
- Three.js UnrealBloomPass
  - https://threejs.org/docs/pages/UnrealBloomPass.html
- Three.js Post Processing Guide
  - https://threejs.org/manual/en/how-to-use-post-processing.html
- Three.js GLTFLoader
  - https://threejs.org/docs/pages/GLTFLoader.html
- Three.js AnimationMixer
  - https://threejs.org/docs/pages/AnimationMixer.html
- Three.js InstancedMesh
  - https://threejs.org/docs/pages/InstancedMesh.html
- Three.js LOD
  - https://threejs.org/docs/pages/LOD.html
