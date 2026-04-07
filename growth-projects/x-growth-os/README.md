# X Growth OS

## 목적
이 프로젝트는 X 기반 신호를 빠르게 수집하고,
업계 사람들의 관점과 흐름을 저녁 분석용 재료로 정리하는 데 집중한다.

## 강점
- 빠른 반응과 현장감
- 계정 기반 큐레이션
- AI, 경제, 투자, 커리어 흐름 감지

## 공통 규칙
공통 카테고리, 스코어링, 출력 규칙은 아래 문서를 함께 본다.
- `../shared/config/categories.md`
- `../shared/config/scoring_rules.md`
- `../shared/docs/output_rules.md`

## 핵심 흐름
1. 18:00~06:00 raw 누적
2. 08:00 수집
3. 12:00 주제 묶기
4. 17:00 저녁용 handoff 만들기
5. 21:00 집에서 분석 및 기록

## raw 레이어
- 야간에는 `data/raw/{{TODAY}}/{{HH}}_collection_raw.md`에 시스템용 raw 재료를 누적한다.
- raw 단계에서는 깊은 해석보다 원문 확보, 최신성, 수집 경로 기록을 우선한다.

## 주요 입력
- `config/watch_accounts.md`
- `config/watch_keywords.md`

## 주요 출력
- `data/raw/{{TODAY}}/{{HH}}_collection_raw.md`
- `data/processed/{{TODAY}}/08_collection.md`
- `data/processed/{{TODAY}}/12_clusters.md`
- `data/handoff/{{TODAY}}/evening_input.md`
- `notes/daily/{{TODAY}}_analysis.md`
- `data/candidates/{{TODAY}}/08_watch_account_candidates.md`
