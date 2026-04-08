# PROJECT_OPERATING_GUIDE

- 마지막 업데이트: 2026-04-08 15:02:23 +09:00

## 프로젝트 목적

- 이 저장소는 `growth-projects/` 아래에서 X, 뉴스, YouTube를 각각 수집하고, 이를 하나의 최종 판단 문서로 합치는 일일 성장 분석 워크스페이스다.
- 역할 분리는 고정한다: X는 빠른 신호, 뉴스는 사실 확인, YouTube는 설명 맥락, 통합 문서는 최종 판단과 다음 행동 정리다.
- 저녁 결과물의 목표는 `오늘 무엇이 중요했는지`, `무엇이 교차 확인됐는지`, `내일 무엇을 먼저 해야 하는지`를 3분 안에 복기 가능하게 만드는 것이다.

## 폴더 구조 요약

- `growth-projects/shared/`: 공통 규칙, 템플릿, 명명 규칙, 품질 기준
- `growth-projects/x-growth-os/`: X 수집, watch account 관리, X 전용 프롬프트
- `growth-projects/news-growth-os/`: 뉴스 수집, watch source/topic 관리, 뉴스 전용 프롬프트
- `growth-projects/youtube-growth-os/`: YouTube 수집, watch channel/topic 관리, YouTube 전용 프롬프트
- `growth-projects/integrated-growth-os/`: 오전 분석, 점심 delta, 저녁 최종 분석, handoff
- 루트 문서: `PROJECT_OPERATING_GUIDE.md`, `CHANGELOG.md`, `Plan.md`

## 자주 수정하는 파일 경로

- 소스 수집 결과
- `growth-projects/x-growth-os/data/processed/<DATE>/08_collection.md`
- `growth-projects/news-growth-os/data/processed/<DATE>/08_news_collection.md`
- `growth-projects/youtube-growth-os/data/processed/<DATE>/08_youtube_collection.md`
- 통합 결과
- `growth-projects/integrated-growth-os/data/outputs/<DATE>/12_integrated_analysis_am.md`
- `growth-projects/integrated-growth-os/data/outputs/<DATE>/13_integrated_analysis_delta.md`
- `growth-projects/integrated-growth-os/data/outputs/<DATE>/21_integrated_analysis.md`
- `growth-projects/integrated-growth-os/data/outputs/<DATE>/22_close_handoff.md`
- 후보 / 감시 반영 후보
- `growth-projects/x-growth-os/data/candidates/<DATE>/08_watch_account_candidates.md`
- `growth-projects/news-growth-os/data/candidates/<DATE>/08_source_candidates.md`
- `growth-projects/news-growth-os/data/candidates/<DATE>/08_topic_candidates.md`
- `growth-projects/youtube-growth-os/data/candidates/<DATE>/08_channel_candidates.md`
- `growth-projects/youtube-growth-os/data/candidates/<DATE>/08_topic_candidates.md`
- snapshot 호환 파일
- `growth-projects/x-growth-os/data/candidates/<DATE>_watch_account_candidates.md`
- `growth-projects/news-growth-os/data/candidates/<DATE>_source_candidates.md`
- `growth-projects/news-growth-os/data/candidates/<DATE>_topic_candidates.md`
- `growth-projects/youtube-growth-os/data/candidates/<DATE>_channel_candidates.md`
- `growth-projects/youtube-growth-os/data/candidates/<DATE>_topic_candidates.md`
- watch 설정
- `growth-projects/x-growth-os/config/watch_accounts.md`
- `growth-projects/news-growth-os/config/watch_sources.md`
- `growth-projects/news-growth-os/config/watch_topics.md`
- `growth-projects/youtube-growth-os/config/watch_channels.md`
- `growth-projects/youtube-growth-os/config/watch_topics.md`

## 가장 먼저 보는 결과 파일 경로

- 1순위: `growth-projects/integrated-growth-os/data/outputs/<DATE>/21_integrated_analysis.md`
- 2순위: `growth-projects/integrated-growth-os/data/outputs/<DATE>/22_close_handoff.md`
- 3순위: 소스별 `08_*` collection 3종
- 4순위: 당일 `08_*` candidate 5종과 루트 snapshot candidate 5종

## watch 반영 방법

1. 당일 `08_*` candidate 문서와 루트 snapshot candidate 문서 중 더 최신인 쪽을 먼저 본다.
2. 오늘자 candidate 문서가 없으면 raw / processed와 handoff의 `Add Now` / `Observe More`를 임시 기준으로 쓴다.
3. `Add Now` 항목만 해당 watch config에 직접 반영한다.
4. `Observe More` 항목은 2~3회 반복 등장 전까지 config에 넣지 않는다.
5. 특정 소스가 약하면 config를 늘리기 전에 먼저 Diagnostics의 공백 원인을 확인한다.
6. watch config를 바꾼 날에는 다음 collection에서 반영률과 편중 경고를 다시 확인한다.

## 자동화 구조

- 소스 수집 단계
- `growth-projects/x-growth-os/prompts/company_08_collection.md`
- `growth-projects/news-growth-os/prompts/company_08_news_collection.md`
- `growth-projects/youtube-growth-os/prompts/company_08_youtube_collection.md`
- 통합 단계
- 오전 기준선: `growth-projects/integrated-growth-os/prompts/home_12_integrated_analysis_am.md`
- 오전 handoff: `growth-projects/integrated-growth-os/prompts/home_12_close_handoff_am.md`
- 점심 delta: `growth-projects/integrated-growth-os/data/outputs/<DATE>/13_*`
- 저녁 결론: `growth-projects/integrated-growth-os/prompts/home_21_integrated_analysis.md`
- 저녁 handoff: `growth-projects/integrated-growth-os/prompts/home_22_close_handoff.md`
- 운영 보조
- 루트 운영 문서: `PROJECT_OPERATING_GUIDE.md`, `CHANGELOG.md`, `Plan.md`

## 아침 / 점심 / 저녁 결과 활용 방법

- 아침
- `11_*_raw.md`와 소스별 `08_*` collection을 읽고 `12_integrated_analysis_am.md`로 기준선을 만든다.
- 오전 handoff는 점심 전에 다시 볼 주제와 즉시 추가 가치가 있는 watch 후보만 남긴다.
- 점심
- `13_*_raw.md`와 `13_*_delta.md`를 이용해 오전 대비 무엇이 강해졌는지, 무엇이 아직 관찰 단계인지 분리한다.
- 점심 문서는 새 사실보다 `강도 변화`와 `추가 확인 포인트`를 남기는 데 집중한다.
- 저녁
- 먼저 오늘자 `data/raw/<DATE>/`의 누적 raw를 확인하고, 없거나 얇으면 전날 저녁 `18/20/22` raw까지 함께 읽어 누적 흐름을 복원한다.
- 저녁에는 `08_*`, `12_*`, `13_*`, raw, candidate를 다시 모아 `21_integrated_analysis.md`와 `22_close_handoff.md`를 만든다.
- late-day raw가 없으면 그 사실을 `08_*`, `21_*`, `22_*`, Diagnostics에 명시하고 재수집보다 최종 재정렬에 집중한다.
- 루트 candidate snapshot 입력이 비어 있으면 같은 날짜의 `08_*` candidate 문서에서 요약 snapshot을 만들거나, 그것도 없으면 handoff에서 직접 판정으로만 정리한다.
- 저녁에는 루트 문서 3종과 git 반영까지 함께 끝내는 것을 기본 흐름으로 둔다.

## 기본 사용 흐름

1. 소스별 `08_*` collection과 `08_*` candidate를 먼저 확인한다.
2. 오늘자 raw가 부족하면 전날 저녁 `18/20/22` raw를 품질 보강용으로 함께 읽는다.
3. 루트 candidate snapshot이 비어 있으면 같은 날짜 `08_*` candidate에서 상위 snapshot을 만들고, 그것도 없으면 handoff의 직접 판정으로 대체한다.
4. 오전 `12_*`와 점심 `13_*`를 읽고 중요도 상승 흐름을 비교한다.
5. 저녁 `21_integrated_analysis.md`에서 최종 핵심 흐름 3~5개와 추가 확인 포인트를 정리한다.
6. `22_close_handoff.md`에서 내일 첫 행동, 오늘 바로 반영할 watch, 선택 가능한 행동을 압축한다.
7. 루트 문서 3종을 갱신한 뒤 `git status -> commit -> push` 순서로 마무리한다.
