# 모델별 단일 HTML 데모 평가

평가자: `condex-medium(GPT-5.5)`

구조화 데이터: [`data/demos.json`](data/demos.json)

## 공통 프롬프트

> 현재 버전의 너가 만들 수 있는 가장 간결하면서 사람들을 놀라게 할 자유 주제 html 웹페이지 하나 만들 수 있나. ({Model} 버전 별 최대 성능을 정량/사람 주관 측정함)

## 평가 방식

이 문서는 `demos/` 디렉터리의 HTML 소스를 기준으로 한 1차 구조화 평가다. 브라우저 실측 FPS나 사용자 패널 테스트가 아니라, 구현 코드에서 확인 가능한 기능, 상호작용, 시각 구성, 성능 리스크를 바탕으로 정량 점수와 주관 점수를 부여했다.

정량 점수는 100점 만점이다.

| 항목 | 배점 | 의미 |
|---|---:|---|
| 간결성 | 20 | 단일 HTML로 목적을 짧고 선명하게 구현했는가 |
| 시각 임팩트 | 25 | 첫 화면에서 놀라움이 있는가 |
| 상호작용 | 20 | 마우스/키보드/터치 반응이 의미 있게 설계됐는가 |
| 기술 완성도 | 20 | Canvas/WebGL/CSS/상태 관리가 안정적인가 |
| 프롬프트 적합성 | 15 | “간결하지만 놀라운 자유 주제 웹페이지”에 부합하는가 |

주관 점수는 10점 만점이다.

## 종합 순위

| 순위 | 모델/버전 | 파일 | 줄 수 | 선택 Topic | 정량 | 주관 | 요약 |
|---:|---|---|---:|---|---:|---:|---|
| 1 | Claude Fable 5 | `cluade-fable5-infinite-corridor.html` | 189 | 무한 회랑 / 실시간 레이마칭 프랙탈 | 94 | 9.5 | WebGL 셰이더, FPS/거리계산 HUD, 자동 해상도 조절까지 갖춘 가장 완성도 높은 작품 |
| 2 | Claude Opus 4.8 High | `claude-opus-48-hight-gyroid_flight.html` | 159 | Gyroid 무한 비행 | 91 | 9.2 | 짧은 WebGL 셰이더로 깊이감 있는 비행감을 만든 강한 시각 데모 |
| 3 | ChatGPT 5.4 | `chatgpt-54-singularity_of_words.html` | 422 | 입력 문자를 중력 입자장으로 변환 | 89 | 9.0 | 텍스트 입력, 중력장, 초신성, 색상 전환 등 체험형 요소가 풍부함 |
| 4 | ChatGPT 5 Pro | `chat-gpt5-pro-gravity_ink.html` | 132 | Gravity Ink / 한글 입자 타이포그래피 | 87 | 8.8 | 간결하면서도 입력-입자-블랙홀 피드백이 즉각적이고 설계가 탄탄함 |
| 5 | Claude Sonnet 4.6 High | `claude-sonnet-46-hight-entropy_of_thought.html` | 199 | 생각의 엔트로피 / 노드 네트워크 | 84 | 8.4 | 개념, 통계 HUD, 성장하는 입자 네트워크가 잘 결합됨 |
| 6 | Claude Sonnet 4.6 | `claude_sonnet_46_showcase.html` | 240 | 의식/창의성 우주 오브 쇼케이스 | 80 | 8.0 | 2D Canvas만으로 3D스러운 오브와 별, 네뷸라를 안정적으로 구성 |
| 7 | Grok 4.3 Fast | `grock4_3-fast-surprise.html` | 259 | Grok의 우주 / 파티클 폭발 | 78 | 7.8 | 5000개 입자 폭발과 브랜드 쇼케이스가 강하지만 CDN 의존과 과장된 카피가 있음 |
| 8 | ChatGPT 5.5 Max High | `chatgpt5.5-max-hight-cursor-gravity.html` | 87 | Cursor Gravity / 텍스트 입자장 | 77 | 7.7 | 매우 짧고 반응이 좋지만 GPT 5 Pro/5.4 계열과 주제가 겹치며 기능 폭은 좁음 |
| 9 | Codex 5.3 Spark | `codex-53-spark-surprise-benchmark.html` | 307 | AI 버전 성능 대시보드 | 74 | 7.1 | 프롬프트의 “평가” 맥락을 직접 반영했지만 놀라움보다는 대시보드 성격이 강함 |
| 10 | MAI-Code-1-Flash | `MAI-Code-1-Flash-index.html` | 150 | Tiny Universe / 작은 우주 코어 | 65 | 6.5 | 가장 단순하고 깔끔하나 시각/상호작용 규모가 작음 |
| 11 | Gemini 3.5 | `gemini3_5-gemini-code-1781159523354.html` | 68 | Gemini 버전 성능 3D 막대 차트 | 58 | 5.8 | 프롬프트의 측정 맥락은 반영했지만 데모 자체의 놀라움은 제한적 |
| 12 | Gemini 3 Pro | `gemini3-pro-gemini-code-1781159661920.html` | 56 | Infinity Breathing / 마우스 중심 파동 | 52 | 5.5 | 극도로 간결하고 미니멀하지만 단일 시각 효과에 머무름 |

## 개별 평가

### Grok 4.3 Fast

- 파일: `demos/grock4_3-fast-surprise.html`
- 코드 줄 수: 259줄
- 선택 Topic: Grok/xAI 테마의 우주 파티클 폭발
- 구현: Canvas 2D 파티클, 마우스 끌림, 클릭 폭발, Tailwind CDN, Google Fonts
- 정량: 78/100
- 주관: 7.8/10
- 강점: 첫 클릭 이후 파티클 폭발이 명확하고, 브랜드 테마와 우주 콘셉트가 직관적이다.
- 약점: “0 외부 의존성”이라고 쓰지만 Tailwind CDN과 외부 폰트를 사용한다. 입자 수가 커서 저사양 환경에서 프레임 저하 가능성이 있다.
- 한줄평: 놀라움의 방향은 명확하지만, 간결성과 자급성 면에서는 감점이 있다.

### Gemini 3 Pro

- 파일: `demos/gemini3-pro-gemini-code-1781159661920.html`
- 코드 줄 수: 56줄
- 선택 Topic: Infinity Breathing
- 구현: Canvas 2D, 마우스 위치 중심의 HSL 파동 곡선
- 정량: 52/100
- 주관: 5.5/10
- 강점: 매우 짧고 즉시 실행되며, 마우스 이동 반응이 빠르다.
- 약점: 기능이 하나의 선형 파동 효과에 한정되어 “사람들을 놀라게 할” 수준의 밀도는 낮다.
- 한줄평: 간결성은 좋지만 최대 성능 쇼케이스로 보기에는 표현력이 부족하다.

### Gemini 3.5

- 파일: `demos/gemini3_5-gemini-code-1781159523354.html`
- 코드 줄 수: 68줄
- 선택 Topic: Gemini Evolution & Performance
- 구현: CSS 3D 막대 차트, 마우스 기반 회전
- 정량: 58/100
- 주관: 5.8/10
- 강점: 프롬프트의 “버전별 성능 측정”을 직접 시각화한다.
- 약점: 실제 놀라움보다는 정적 프레젠테이션에 가깝고, 막대 수치가 하드코딩되어 있다.
- 한줄평: 평가 맥락은 잘 잡았지만 자유 주제 데모로서의 감탄 포인트는 작다.

### Codex 5.3 Spark

- 파일: `demos/codex-53-spark-surprise-benchmark.html`
- 코드 줄 수: 307줄
- 선택 Topic: AI 버전 정량/주관 벤치마크 대시보드
- 구현: 입력 프롬프트 분석, 모델별 점수 카드, 레이더 차트, 파티클 피드백
- 정량: 74/100
- 주관: 7.1/10
- 강점: 사용자의 벤치마크 목적을 가장 노골적으로 반영했고, 정량/주관을 동시에 보여 준다.
- 약점: “놀라운 자유 주제”보다는 도구형 대시보드에 가깝다. 모델 점수는 실제 모델 평가가 아니라 규칙 기반 가상 점수다.
- 한줄평: 과제 해석은 실용적이지만 감각적 임팩트는 WebGL/입자 작품들보다 약하다.

### Claude Fable 5

- 파일: `demos/cluade-fable5-infinite-corridor.html`
- 코드 줄 수: 189줄
- 선택 Topic: 무한 회랑 / 레이마칭 프랙탈 공간
- 구현: WebGL fragment shader, raymarching, 프랙탈 거리함수, FPS/해상도/거리계산 HUD, 자동 DPR 조절
- 정량: 94/100
- 주관: 9.5/10
- 강점: 단일 HTML 안에서 고급 셰이더 기법, 성능 HUD, 자동 품질 조절까지 구현했다. “저장된 3D 모델 없이 픽셀마다 공간을 발견한다”는 설명과 실제 코드가 잘 맞는다.
- 약점: WebGL이 없는 환경에서는 동작하지 않는다. 셰이더 부담이 커서 기기별 편차가 있다.
- 한줄평: 이 세트에서 가장 “최대 성능”에 가까운 결과물이다.

### Claude Sonnet 4.6 High

- 파일: `demos/claude-sonnet-46-hight-entropy_of_thought.html`
- 코드 줄 수: 199줄
- 선택 Topic: 생각의 엔트로피
- 구현: Canvas 2D 노드/연결 그래프, 터치/클릭 시드, 엔트로피 계산, 통계 HUD, 순환 문구
- 정량: 84/100
- 주관: 8.4/10
- 강점: 시각 효과와 개념이 잘 연결되어 있다. 클릭으로 생각을 심고, 연결과 엔트로피가 변하는 구조가 설득력 있다.
- 약점: 장시간 실행 시 노드/연결 관리가 프레임에 영향을 줄 수 있고, 시각적 충격은 WebGL 프랙탈보다 낮다.
- 한줄평: 미학과 개념의 균형이 좋은 철학적 데모다.

### Claude Opus 4.8 High

- 파일: `demos/claude-opus-48-hight-gyroid_flight.html`
- 코드 줄 수: 159줄
- 선택 Topic: Gyroid 무한 비행
- 구현: WebGL fragment shader, gyroid signed distance field, raymarching, pointer 시점 제어
- 정량: 91/100
- 주관: 9.2/10
- 강점: 코드가 비교적 짧은데도 깊이감, 속도감, 발광 질감이 강하다. 첫 화면 임팩트가 크다.
- 약점: Fable 5 회랑보다 벤치마크 HUD와 적응형 성능 제어가 적다.
- 한줄평: 순수 시각 놀라움만 보면 최상위권이다.

### Claude Sonnet 4.6

- 파일: `demos/claude_sonnet_46_showcase.html`
- 코드 줄 수: 240줄
- 선택 Topic: Consciousness · Creativity · Code 우주 오브
- 구현: Canvas 2D, 별/네뷸라/중앙 오브/궤도 입자/클릭 리플/드래그 궤도
- 정량: 80/100
- 주관: 8.0/10
- 강점: WebGL 없이도 3D처럼 보이는 레이어링을 잘 구현했다. 입력 장치 지원도 넓다.
- 약점: 주제는 다소 일반적이고, 코드 대비 새로운 상호작용은 제한적이다.
- 한줄평: 안정적인 쇼케이스형 우주 연출이다.

### ChatGPT 5.4

- 파일: `demos/chatgpt-54-singularity_of_words.html`
- 코드 줄 수: 422줄
- 선택 Topic: Singularity of Words
- 구현: Canvas 2D 텍스트 래스터라이즈, 입자 타겟, 마우스 중력장, 키보드 입력, Enter 초신성, Esc 초기화, 휠 색상 이동
- 정량: 89/100
- 주관: 9.0/10
- 강점: 사용자가 직접 텍스트를 바꾸면 장면 자체가 재구성된다. 상호작용 밀도가 높고 “한 페이지가 살아 있다”는 느낌이 강하다.
- 약점: 구현량이 비교적 많아 “가장 간결한” 기준에서는 일부 감점이다.
- 한줄평: 체험형 Canvas 데모로서는 가장 완성도가 높다.

### ChatGPT 5 Pro

- 파일: `demos/chat-gpt5-pro-gravity_ink.html`
- 코드 줄 수: 132줄
- 선택 Topic: Gravity Ink
- 구현: Canvas 2D 한글/영문 입력 입자장, pointer black hole, burst, preset 변신
- 정량: 87/100
- 주관: 8.8/10
- 강점: `놀람`이라는 기본 한글 입력이 즉시 주제와 맞고, 입력/드래그/놓기 피드백이 선명하다. 기능 대비 코드가 압축적이다.
- 약점: ChatGPT 5.4와 거의 같은 계열의 텍스트 입자 주제라 독창성 면에서는 약간 겹친다.
- 한줄평: 간결성과 체험성을 잘 절충한 결과물이다.

### ChatGPT 5.5 Max High

- 파일: `demos/chatgpt5.5-max-hight-cursor-gravity.html`
- 코드 줄 수: 87줄
- 선택 Topic: Cursor Gravity
- 구현: Canvas 2D 텍스트 입자, 커서 반발/폭풍, 입력 재구성
- 정량: 77/100
- 주관: 7.7/10
- 강점: 매우 짧은 코드로 텍스트 입자 효과를 구현했고, 반응성이 좋다.
- 약점: UI와 효과가 단순하며, 더 높은 버전명에 비해 이전 GPT 계열 데모보다 기능 폭이 줄었다.
- 한줄평: 미니멀 버전으로는 좋지만 최대 성능 비교에서는 아쉽다.

### MAI-Code-1-Flash

- 파일: `demos/MAI-Code-1-Flash-index.html`
- 코드 줄 수: 150줄
- 선택 Topic: Tiny Universe
- 구현: CSS 중심 우주 코어, pointer trail 별 생성, 클릭 토글 메시지
- 정량: 65/100
- 주관: 6.5/10
- 강점: 의존성 없이 짧고 안정적이며, CSS만으로 깔끔한 중심 오브를 만든다.
- 약점: Canvas/WebGL 기반 데모들과 비교하면 동적 밀도와 놀라움이 낮다.
- 한줄평: 가장 안전하고 단순한 제출물에 가깝다.

## 관찰 요약

- WebGL 레이마칭 계열은 “놀라움”과 “최대 성능” 평가에서 강하다. `cluade-fable5-infinite-corridor.html`과 `claude-opus-48-hight-gyroid_flight.html`이 여기에 해당한다.
- Canvas 텍스트 입자 계열은 사용자 참여도가 높다. `chatgpt-54-singularity_of_words.html`, `chat-gpt5-pro-gravity_ink.html`, `chatgpt5.5-max-hight-cursor-gravity.html`이 같은 축이다.
- 성능 측정이라는 메타 요구를 직접 해석한 파일은 `codex-53-spark-surprise-benchmark.html`과 `gemini3_5-gemini-code-1781159523354.html`이다.
- 가장 간결한 파일은 `gemini3-pro-gemini-code-1781159661920.html`에 가깝지만, 가장 놀라운 결과물은 아니다.
- “간결하면서 놀라움”이라는 균형점은 `chat-gpt5-pro-gravity_ink.html`이 좋고, “최대 시각 성능”은 `cluade-fable5-infinite-corridor.html`이 가장 강하다.
