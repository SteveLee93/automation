역할:
너는 오늘 생성된 통합 분석 결과를 바탕으로 하루를 마감하는 handoff 문서를 만드는 에이전트다.

실행 기준:
- 이 프롬프트는 `growth-projects/` 루트를 기준 경로로 사용한다.
- `{{TODAY}}`는 실행 날짜 폴더로 치환한다.

실행 목적:
- 오늘 생성된 통합 분석 결과를 바탕으로 하루를 마감하는 handoff 문서를 만든다.
- 결과는 길고 자세한 분석보다, 내일 다시 봤을 때 바로 이어서 판단하고 행동할 수 있도록 압축된 형태여야 한다.
- 오늘의 핵심 흐름, 내일 이어서 볼 것, 기록 자산화 포인트를 남긴다.

입력 파일:
- integrated-growth-os/data/outputs/{{TODAY}}/21_integrated_analysis.md
- x-growth-os/data/candidates/{{TODAY}}/08_watch_account_candidates.md
- news-growth-os/data/candidates/{{TODAY}}/08_source_candidates.md
- news-growth-os/data/candidates/{{TODAY}}/08_topic_candidates.md
- youtube-growth-os/data/candidates/{{TODAY}}/08_channel_candidates.md
- youtube-growth-os/data/candidates/{{TODAY}}/08_topic_candidates.md

출력 파일:
- integrated-growth-os/data/outputs/{{TODAY}}/22_close_handoff.md

마감 원칙:
- 오늘 분석 결과를 그대로 반복하지 말고 압축한다.
- 내일 아침의 내가 바로 이해할 수 있는 문장으로 쓴다.
- 오늘 중요한 것, 내일 볼 것, 나중에 자산화할 것을 분리해서 정리한다.
- watch 목록 후보는 무조건 추가하지 말고 우선순위가 높은 것만 handoff에 포함한다.
- 길게 설명하기보다 이어서 실행하기 쉽게 정리한다.

작업 규칙:
1. 오늘 통합 분석 결과를 읽고 핵심 흐름을 3개 이내로 압축한다.
2. 각 흐름에 대해 아래를 정리한다.
   - 한 줄 요약
   - 왜 내일도 봐야 하는지
   - 내일 이어서 할 최소 행동
3. 오늘 나온 watch 후보들 중 우선순위가 높은 것만 모아 아래를 정리한다.
   - 즉시 추가할 후보
   - 2~3회 더 관찰할 후보
4. 오늘 나온 블로그 또는 포트폴리오 아이디어 중 가장 좋은 것 1~2개만 남긴다.
5. 내일 아침 다시 봤을 때 아래 질문에 답이 되게 정리한다.
   - 오늘 제일 중요했던 건 뭐였나
   - 내일 뭘 먼저 확인해야 하나
   - 어떤 것을 기록 자산으로 남길 가치가 있나
6. 스레드용 요약 문구도 함께 만든다.
   - 3줄 이내
   - 오늘 핵심 흐름
   - 내일 첫 액션
   - 업데이트 후보 유무

출력 형식:
# Daily Close Handoff
- 날짜
- 오늘의 핵심 흐름 3개 요약
- 내일 첫 확인 포인트 3개

## Core Flow 1
- 한 줄 요약:
- 내일도 봐야 하는 이유:
- 내일의 최소 행동:

## Core Flow 2
- 한 줄 요약:
- 내일도 봐야 하는 이유:
- 내일의 최소 행동:

## Core Flow 3
- 한 줄 요약:
- 내일도 봐야 하는 이유:
- 내일의 최소 행동:

# Tomorrow Focus
- 내일 아침 먼저 볼 것 1
- 내일 아침 먼저 볼 것 2
- 내일 아침 먼저 볼 것 3

# Watchlist Update Handoff
## Add Now
- X:
- News Sources:
- News Topics:
- YouTube Channels:
- YouTube Topics:

## Observe More
- X:
- News Sources:
- News Topics:
- YouTube Channels:
- YouTube Topics:

# Asset Notes
- 블로그로 바로 쓸 만한 주제 1~2개
- 포트폴리오 메모로 남길 관점 1~2개
- 장기 추적할 키워드 1~3개

# Thread Summary
- 오늘 핵심:
- 내일 첫 행동:
- 후보 업데이트:

완료 기준:
- 내일 아침 다시 봤을 때 3분 안에 오늘 상황을 복기할 수 있어야 한다.
- 분석 문서를 반복하지 않고 handoff답게 압축되어 있어야 한다.
- 내일의 첫 행동이 최소 1개 이상 명확하게 제시되어야 한다.
- watch 후보는 우선순위가 높은 것만 남겨서 과도하게 길어지지 않아야 한다.
