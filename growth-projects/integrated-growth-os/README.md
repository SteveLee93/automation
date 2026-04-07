# Integrated Growth OS

## 목적
이 프로젝트는 X 기반 수집 결과, 뉴스 기사 기반 수집 결과, YouTube 기반 설명형 콘텐츠를 함께 읽고,
같은 사건, 같은 논점, 같은 흐름을 하나의 통합 cluster로 묶어
저녁 분석용 종합 브리핑 재료를 만드는 데 집중한다.

## 실행 기준
- 이 프로젝트의 통합 프롬프트는 `growth-projects/` 루트를 기준 경로로 삼는다.
- 즉, 입력과 출력 경로는 `shared/...`, `x-growth-os/...`, `news-growth-os/...`, `integrated-growth-os/...`처럼 루트 상대 경로로 해석한다.

## 공통 규칙
- `../shared/AGENTS.md`
- `../shared/config/categories.md`
- `../shared/config/scoring_rules.md`
- `../shared/docs/output_rules.md`

## 주요 입력
- `x-growth-os/data/processed/{{TODAY}}/08_collection.md`
- `news-growth-os/data/processed/{{TODAY}}/08_news_collection.md`
- `youtube-growth-os/data/processed/{{TODAY}}/08_youtube_collection.md`

## 주요 출력
- `integrated-growth-os/data/outputs/{{TODAY}}/12_integrated_clusters.md`
- `integrated-growth-os/data/outputs/{{TODAY}}/12_integrated_analysis_am.md`
- `integrated-growth-os/data/outputs/{{TODAY}}/12_close_handoff_am.md`
- `integrated-growth-os/data/outputs/{{TODAY}}/21_integrated_analysis.md`
- `integrated-growth-os/data/outputs/{{TODAY}}/22_close_handoff.md`

## 핵심 역할
- X에서 감지된 빠른 반응과 관점을 모은다.
- 뉴스 기사에서 확인된 사실과 원문을 붙인다.
- YouTube에서 설명 깊이와 학습 가치가 높은 해설을 붙인다.
- 셋을 교차 확인해 Cross-confirmed, X-only signal, News-only signal, YouTube-only signal로 나눈다.

## 추천 흐름
1. 오전 수집 결과를 바탕으로 `12_integrated_analysis_am.md`를 만든다.
2. 점심 전 다시 볼 핵심만 `12_close_handoff_am.md`에 압축한다.
3. 하루를 마감할 때 `21_integrated_analysis.md`와 `22_close_handoff.md`로 이어간다.
4. 자동화에서는 `prompts/company_12_morning_pipeline.md` 하나로 오전 수집부터 오전 handoff까지 묶을 수 있다.
