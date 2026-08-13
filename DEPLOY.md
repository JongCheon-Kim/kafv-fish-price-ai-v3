# v3 배포 순서

## 1. Cloudflare Worker 먼저 업데이트
현재 Worker에 이 폴더의 `worker.js` 전체를 붙여넣고 Deploy 합니다.
기존 Secret은 삭제하거나 다시 입력하지 않습니다.

배포 후 확인:
- `/health` 의 `version` = `0.5`
- `availableRoutes` 에 `/api/search` 존재
- `/routes` 의 `smartSearchTargets` 확인

기존 19개 Route는 그대로 유지하므로 기존 v1/v2 앱과 호환되도록 설계했습니다.

## 2. GitHub 새 저장소 생성
저장소명: `kafv-fish-price-ai-v3`

GitHub Pages 실행파일:
- `index.html`
- `sw.js`
- `manifest.json`
- `kafv-fish-price-ai-icon-192.png`
- `kafv-fish-price-ai-icon-512.png`

문서/백업파일:
- `worker.js`
- `README.md`
- `QA_REPORT.md`
- `TEST_MATRIX.md`

## 3. GitHub Pages 활성화
Settings → Pages → Deploy from a branch → `main` / `(root)`

예상 주소:
`https://jongcheon-kim.github.io/kafv-fish-price-ai-v3/`

## 4. 배포 확인
화면 상단에서 `v0.16 · API 정상` 확인 후 어종별 검색을 비교합니다.
