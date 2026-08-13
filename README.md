# KAFV 수산물 가격정보 AI v3

검색확장형 실전 버전입니다.

## 버전
- GitHub/PWA: v0.16
- Cloudflare Worker: v0.5
- 저장소 권장명: `kafv-fish-price-ai-v3`

## 핵심 변경
- 품목만 필수 선택
- 유통단계·품종/상태·등급·지역·시장은 `전체(자동)`로 넓게 검색 가능
- 정확조건 0건 시 Worker `/api/search`가 품목코드를 고정한 채 조건을 단계적으로 완화
- 자동확대가 발생하면 결과에 완화조건/날짜확대를 표시
- 어기·비어기는 검색차단 조건으로 사용하지 않고 해석정보로만 사용
- 단위·규격/단위크기는 선택조건에서 제외하고 실제 API 응답값으로 표시
- 가격 API와 경매 API의 코드체계는 분리 유지

## 구조
GitHub Pages/PWA → Cloudflare Worker v0.5 → Cloudflare Secret → aT 공공데이터 API

`worker.js`에는 API Key가 없습니다. 실제 Key는 기존 Cloudflare Secret을 그대로 사용합니다.
