# YouTube Growth OS

## 목적
이 프로젝트는 YouTube 기반 경제, 투자, AI, 커리어 관련 영상을 수집하고,
설명 깊이와 학습 가치가 높은 콘텐츠를 저녁 분석용 재료로 정리하는 데 집중한다.

## 강점
- 긴 설명형 콘텐츠의 맥락 확보
- 채널 단위 신뢰도 관리
- 영상 형식별 품질 구분
- 학습, 블로그, 포트폴리오로 이어질 주제 발굴

## 공통 규칙
공통 카테고리, 스코어링, 출력 규칙은 아래 문서를 함께 본다.
- `../shared/config/categories.md`
- `../shared/config/scoring_rules.md`
- `../shared/config/source_quality_rules.md`
- `../shared/docs/output_rules.md`

## 핵심 흐름
1. 18:00~06:00 raw 누적
2. 08:00 YouTube 수집
3. 17:00 YouTube handoff
4. 21:00 YouTube 분석 및 기록

## raw 레이어
- 야간에는 `data/raw/{{TODAY}}/{{HH}}_youtube_raw.md`에 시스템용 raw 영상을 누적한다.
- raw 단계에서는 제목보다 설명란, 형식, 최신성, 채널 신뢰도 메타데이터 확보를 우선한다.

## 주요 입력
- `config/watch_channels.md`
- `config/watch_topics.md`
- `config/watch_regions.md`
- `config/watch_formats.md`

## 주요 출력
- `data/raw/{{TODAY}}/{{HH}}_youtube_raw.md`
- `data/processed/{{TODAY}}/08_youtube_collection.md`
- `data/handoff/{{TODAY}}/evening_youtube_input.md`
- `notes/daily/{{TODAY}}_youtube_analysis.md`
- `data/candidates/{{TODAY}}/08_channel_candidates.md`
- `data/candidates/{{TODAY}}/08_topic_candidates.md`
