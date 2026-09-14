# banners-v1

운영 월이 바뀌거나 시즌 이벤트가 시작될 때 대시보드(플레이 화면) 위쪽에 표시하는 배너 패널입니다.

## 출처

`banners/`의 원본 PNG 29개는 한 장의 콜라주 시트에서 잘려 나온 조각이라, 각 파일 하단에
다음 패널의 윗부분이 몇 픽셀 붙어 있었습니다. `manifest.json`의 `seamRow`가 그 이음선의
행 번호이고, 배포본은 그 위까지만 잘라 쓴 WebP입니다. 원본 PNG는 `banners/`에 그대로
남아 있고 이 게임 번들에는 포함되지 않습니다.

## 구성

- 파일: `<key>.webp` (28개). 원본을 폭 760px로 정규화하고 높이는 이음선까지 남깁니다.
- `manifest.json`: `base_url`(`/assets/banners-v1/`)과 `assets[]`(`key`, `file`, `label`,
  `width`, `height`, `bytes`, `source`, `sourceSha256`, `seamRow`).
- 전체 용량 약 630KB. PNG 원본 합계 약 6.4MB에서 줄였습니다.

## 표시 규칙

`src/ui/banner-view.ts`가 `annualStage`/`annualMonth`/`career.phase`를 읽어 어떤 배너를
보여줄지 정합니다. 닫으면 `localStorage`의 `legacy9-banner-seen-v1`에 그 배너 키를
기록해 다시 뜨지 않습니다. 게임 저장(League/Career)은 건드리지 않습니다.

경기확률·성장·정산·일정·AI 계산은 이 에셋과 무관합니다. 표시 전용입니다.
