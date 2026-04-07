# News Growth OS

## 목적
이 프로젝트는 뉴스 기사 기반으로 경제, 투자, AI, 커리어 관련 흐름을 정리하고,
매체 신뢰도와 기사 원문 중심으로 저녁 분석용 재료를 만드는 데 집중한다.

## 강점
- 기사 원문 기반 확인
- 매체별 신뢰도 비교
- 지역별 이슈 분류
- 헤드라인 중복 제거

## 공통 규칙
공통 카테고리, 스코어링, 출력 규칙은 아래 문서를 함께 본다.
- `../shared/config/categories.md`
- `../shared/config/scoring_rules.md`
- `../shared/config/source_quality_rules.md`
- `../shared/docs/output_rules.md`

## 핵심 흐름
1. 18:00~06:00 raw 누적
2. 08:00 뉴스 수집
3. 17:00 뉴스 handoff
4. 21:00 뉴스 분석 및 기록

## raw 레이어
- 야간에는 `data/raw/{{TODAY}}/{{HH}}_news_raw.md`에 시스템용 raw 기사를 누적한다.
- raw 단계에서는 기사 원문 확보, 최신성, 매체와 지역 메타데이터 정리에 집중한다.

## 주요 입력
- `config/watch_sources.md`
- `config/watch_topics.md`
- `config/watch_regions.md`

## 주요 출력
- `data/raw/{{TODAY}}/{{HH}}_news_raw.md`
- `data/processed/{{TODAY}}/08_news_collection.md`
- `data/handoff/{{TODAY}}/evening_news_input.md`
- `notes/daily/{{TODAY}}_news_analysis.md`
- `data/candidates/{{TODAY}}/08_source_candidates.md`
