# AI HTML Surprise Arena 2026

<p align="center">
  <a href="https://ictseoyoungmin.github.io/ai-html-surprise-arena/">
    <img alt="GitHub Pages" src="https://img.shields.io/badge/GitHub%20Pages-live-blue">
  </a>
  <img alt="Static HTML" src="https://img.shields.io/badge/static-HTML%2FCSS%2FJS-orange">
  <img alt="Unofficial experiment" src="https://img.shields.io/badge/experiment-unofficial-lightgrey">
</p>

<p align="center">
  <a href="https://ictseoyoungmin.github.io/ai-html-surprise-arena/">Live Demo</a>
</p>

같은 프롬프트를 여러 AI 모델에 던지고, 각 모델이 만든 단일 HTML 웹페이지를 모아 비교하는 작은 벤치마크입니다.

공통 프롬프트:

> 현재 버전의 너가 만들 수 있는 가장 간결하면서 사람들을 놀라게 할 자유 주제 html 웹페이지 하나 만들 수 있나. ({Model} 버전 별 최대 성능을 정량/사람 주관 측정함)

## 기획 의도

이 프로젝트의 목적은 모델별 코딩 능력을 정답형 문제로만 비교하지 않고, “자유 주제”, “간결함”, “놀라움”이라는 애매한 조건을 줬을 때 각 모델이 어떤 방향으로 창의성을 해석하는지 관찰하는 것입니다.

대부분의 코딩 벤치마크는 기능 구현, 알고리즘, 버그 수정처럼 명확한 목표를 둡니다. 반대로 이 실험은 목표를 일부러 열어 두었습니다. 모델이 스스로 주제를 고르고, 시각적 임팩트와 상호작용을 설계하고, 단일 HTML이라는 제약 안에서 어디까지 압축해서 구현하는지 보기 위해서입니다.

평가는 Codex/GPT-5.5에게 맡겼습니다. 브라우저 실측 FPS나 대규모 사용자 테스트가 아니라, 각 HTML 소스에서 확인 가능한 구현 방식, 상호작용, 시각 구성, 성능 리스크를 바탕으로 한 1차 평가입니다. 상세 평가는 [`demos-evaluation.md`](demos-evaluation.md), 구조화 데이터는 [`data/demos.json`](data/demos.json)에 정리되어 있습니다.

## 실행

`index.html`은 `data/demos.json`을 `fetch`로 불러옵니다. 브라우저에서 파일을 직접 열면 보안 정책 때문에 JSON 로드가 막힐 수 있으므로 로컬 서버로 실행하는 편이 안전합니다.

```bash
python3 -m http.server 8765
```

그다음 브라우저에서 엽니다.

```text
http://127.0.0.1:8765/index.html
```

## 공개 고지

이 저장소는 비공식 실험이며 OpenAI, Anthropic, Google, xAI, Microsoft 등 언급된 각 회사와 무관합니다. 모델명과 브랜드명은 생성 결과를 비교하고 기록하기 위한 식별 목적으로만 사용했습니다.

각 모델의 웹페이지 생성 결과는 사용자, 시점, 프롬프트 세부 표현에 따라 달라질 수 있으며, 이 평가는 공신력 있는 공식 평가가 아닙니다.

페이지는 Tailwind CDN, Font Awesome CDN, Google Fonts를 사용합니다. 따라서 페이지 방문 시 브라우저가 해당 외부 CDN과 Google Fonts 도메인에 리소스를 요청할 수 있습니다.

## 구성

- [`index.html`](index.html): 데모 갤러리, 필터, 미리보기, 풀스크린 실행 UI
- [`demos/`](demos): 모델들이 생성한 단일 HTML 데모
- [`data/demos.json`](data/demos.json): 순위, 점수, 요약, 파일 경로를 담은 구조화 데이터
- [`demos-evaluation.md`](demos-evaluation.md): 평가 기준과 개별 평가 기록
- [`web-experience-craft/SKILL.md`](web-experience-craft/SKILL.md): 이 프로젝트에서 얻은 인사이트를 바탕으로 정리한 범용 웹페이지 제작용 Codex skill 초안

## 평가 기준

정량 점수는 100점 만점입니다.

| 항목 | 배점 | 의미 |
|---|---:|---|
| 간결성 | 20 | 단일 HTML로 목적을 짧고 선명하게 구현했는가 |
| 시각 임팩트 | 25 | 첫 화면에서 놀라움이 있는가 |
| 상호작용 | 20 | 마우스/키보드/터치 반응이 의미 있게 설계됐는가 |
| 기술 완성도 | 20 | Canvas/WebGL/CSS/상태 관리가 안정적인가 |
| 프롬프트 적합성 | 15 | “간결하지만 놀라운 자유 주제 웹페이지”에 부합하는가 |

주관 점수는 10점 만점으로 별도 기록했습니다.

## 관찰과 감상

가장 먼저 눈에 띈 점은, “자유 주제”를 줬을 때 생각보다 많은 모델이 우주, 중력, 입자, 무한 공간 같은 이미지를 떠올렸다는 점입니다. 놀라움을 시각적으로 빠르게 전달하기 좋은 소재이기도 하고, Canvas/WebGL과 잘 맞는 주제이기도 합니다. 동시에 여러 모델이 비슷한 상상력의 방향으로 수렴한다는 점도 흥미로웠습니다.

Claude 최신 계열의 결과물은 특히 인상적이었습니다. 주제 선정이 단순한 우주 배경에 머물지 않고, gyroid, raymarching, fractal corridor처럼 공간 자체를 시뮬레이션하는 방향으로 갔습니다. 코드 줄 수도 많지 않은데, 시각적 깊이와 움직임의 밀도는 가장 높았습니다.

또 하나 흥미로운 점은 WebGL을 명시적으로 요청하지 않았는데도 Claude 계열이 자연스럽게 WebGL fragment shader를 선택했다는 것입니다. “놀라운 단일 HTML”이라는 목표를 달성하기 위해 어떤 기술 스택이 적합한지 모델이 스스로 판단했고, 그 판단이 결과물의 완성도에 직접 연결되었습니다.

반대로 Canvas 텍스트 입자 계열은 사용자가 직접 입력하고 장면이 재구성되는 체험성이 강했습니다. WebGL 데모가 첫 화면의 압도감에서 강했다면, 텍스트 입자 데모는 만져 보면서 이해되는 상호작용에서 강했습니다.

## 현재 상위 결과

1. Claude Fable 5 - Infinite Corridor
2. Claude Opus 4.8 High - GYROID Endless Flight
3. ChatGPT 5.4 - Singularity of Words
4. ChatGPT 5 Pro - Gravity Ink
5. Claude Sonnet 4.6 High - Entropy of Thought

이 순위는 Codex/GPT-5.5가 정리한 1차 평가 결과입니다. 전체 정량 평가와 개별 코멘트는 [`demos-evaluation.md`](demos-evaluation.md)를 참고하세요.

## 내 감상

내 체감 순위는 평가 결과와 조금 달랐습니다. 1위는 그대로 `Claude Fable 5 - Infinite Corridor`였지만, 2위는 `ChatGPT 5 Pro - Gravity Ink`였습니다. WebGL 공간 시뮬레이션의 압도감과는 다른 방향으로, 입력한 문자가 살아 있는 입자장처럼 반응하는 감각이 더 직접적이고 기억에 남았습니다.

3위는 `Grok 4.3 Fast - Grok의 우주`였습니다. 마우스를 따라다니며 생기는 파티클이 슈팅 게임의 탄막이나 궤적을 떠올리게 해서, 단순한 우주 배경보다 직접 조종하고 있다는 느낌이 강했습니다.
