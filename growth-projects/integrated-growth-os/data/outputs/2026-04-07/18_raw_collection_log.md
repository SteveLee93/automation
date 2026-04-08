# 18 Raw Collection Log

- 실행 시각: 2026-04-07 18:10:11 +09:00
- 초기 실행 여부: 아니오
- 재실행 여부: 아니오
- X raw 수집 개수: 6
- News raw 수집 개수: 6
- YouTube raw 수집 개수: 5
- 누락 입력 파일 여부: 없음
- 수집 중 특이사항: X는 late-day 신규 direct 원문이 약해 기존 5일 window 내 직접 포스트 재확인 비중이 높았다. News는 TechCrunch 최신 기사 비중이 높았고, YouTube는 Bloomberg 계열 설명형 콘텐츠 편중이 이어졌다.
- 다음 분석(아침/점심/저녁)에 활용 가능 여부: 예. `11_*`, `13_*` raw와 함께 late-day 레이어로 바로 사용할 수 있다.

## Source Notes

- X: @OpenAI, @Google, @Reuters, @business 같은 direct anchor는 그대로 유효했고, late-day에는 신규 원문보다 기존 5일 내 직접 포스트 재확인이 더 안정적이었다.
- News: TechCrunch가 AI 정책, AI 자금 흐름, 지정학-데이터센터 리스크를 연속으로 제공했고, Yonhap가 한국 에너지 조달 대응을 지역 관점으로 보강했다.
- YouTube: exact watch channel 신규 업로드는 제한적이었고, Bloomberg Tech·Odd Lots·FICC Focus·Big Take 같은 장문형 설명 소스가 late-day 공백을 메웠다.
