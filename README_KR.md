# Sidekick KR Kakao Trade Patch v2026.6.4

이 압축파일은 Sidekick v2026.6.4 portable에 한국 POE/POE2 거래 API 주소 패치와 2026-06-19 trade fetch 응답 스키마 변경 대응 패치를 적용한 비공식 배포본입니다.

ZIP 안에는 실행에 필요한 포터블 파일만 포함했습니다. 설명서, 스크린샷, 작업용 PowerShell 스크립트, 소스 diff는 GitHub 저장소와 릴리스 페이지에서 확인할 수 있습니다.

## 무엇이 바뀌었나

- 한국 거래 API 주소를 `poe.game.daum.net`에서 `poe.kakaogames.com`으로 변경했습니다.
- POE2 한국어 설정에서 `Sidekick failed to communicate with the trade API` / `Unauthorized`가 뜨는 문제를 우회합니다.
- 2026-06-19 이후 `explicitMods`가 문자열이 아닌 객체로 내려오는 trade fetch 응답도 읽을 수 있게 했습니다.
- 한국어 아이템 검색 기준으로 검증했습니다. 예: `진홍색 목걸이` 검색 및 한국어 결과 반환.
- 객체형 mod 응답도 검증했습니다. 예: `경계하는 시야 / 에메랄드 반지`의 `[Accuracy|정확도] +143` explicit mod.

## 실행 방법

1. 압축을 원하는 폴더에 풉니다.
2. 압축을 푼 폴더의 `Sidekick.exe`를 실행합니다.
3. POE/POE2를 관리자 권한으로 실행 중이면 Sidekick도 관리자 권한으로 뜰 수 있습니다.

## Sidekick 설정 권장값

- UI language: Korean
- Game language/parser: Korean
- League: POE2 현재 리그, 예: `Runes of Aldur`
- Force English trade results / Use invariant trade results: 꺼짐

## 업데이트 후 다시 오류가 나면

Sidekick 공식 업데이트가 `current\Sidekick.Data.dll`, `current\Sidekick.Apis.Poe.Trade.dll`, `current\Sidekick.Common.dll`을 덮어쓰면 패치가 사라질 수 있습니다.

그때는 Sidekick을 종료한 뒤 이 릴리스의 ZIP을 다시 받아 새 폴더에 압축 해제하고 `Sidekick.exe`를 실행하세요.

## ZIP 안에 들어 있는 파일

```text
.portable
Sidekick.exe
Update.exe
current\
packages\.betaId
```

## 주의

- 공식 Sidekick 배포본이 아닙니다.
- 원본 프로젝트: https://github.com/Sidekick-Poe/Sidekick
- 원본 라이선스는 MIT이며 라이선스 전문은 이 저장소의 `LICENSE`에서 확인할 수 있습니다.
- 이 패치는 한국 서비스 주소 이전에 따른 임시 수정입니다. 공식 Sidekick에서 같은 수정이 반영되면 공식 최신 버전을 쓰는 것이 좋습니다.

