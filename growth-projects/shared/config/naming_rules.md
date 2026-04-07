# naming_rules.md

## 날짜
- 날짜는 `YYYY-MM-DD` 형식을 사용한다.
- 시간 슬롯이 필요한 raw 파일은 `HH` 24시간 두 자리 형식을 사용한다.

## 수집 결과
- X 프로젝트 기본 수집: `08_collection.md`
- 뉴스 프로젝트 기본 수집: `08_news_collection.md`
- YouTube 프로젝트 기본 수집: `08_youtube_collection.md`
- X 클러스터 결과: `12_clusters.md`
- 통합 클러스터 결과: `12_integrated_clusters.md`
- 저녁 handoff: `evening_input.md` 또는 소스가 드러나는 이름

## raw 수집 결과
- X raw: `HH_collection_raw.md`
- 뉴스 raw: `HH_news_raw.md`
- YouTube raw: `HH_youtube_raw.md`
- raw 수집 로그: `HH_raw_collection_log.md`

## 분석 결과
- 일일 분석: `YYYY-MM-DD_analysis.md`
- 소스 구분이 필요하면 `YYYY-MM-DD_news_analysis.md`처럼 접미사를 붙인다.
- 오전 통합 분석: `12_integrated_analysis_am.md`
- 오전 압축 handoff: `12_close_handoff_am.md`
- 일일 통합 분석: `21_integrated_analysis.md`
- 하루 마감 handoff: `22_close_handoff.md`

## 후보 결과
- X 계정 후보: `08_watch_account_candidates.md`
- 뉴스 소스 후보: `08_source_candidates.md`
- 뉴스 주제 후보: `08_topic_candidates.md`
- YouTube 채널 후보: `08_channel_candidates.md`
- YouTube 주제 후보: `08_topic_candidates.md`

## 원칙
- 같은 폴더 안에서는 파일명만 보고 역할이 드러나야 한다.
- 소스가 다르면 파일명 또는 상위 폴더에서 구분 가능해야 한다.
- 시스템용 raw 산출물과 사용자용 분석 산출물은 파일명만 봐도 구분 가능해야 한다.
