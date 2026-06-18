# Sidekick KR Kakao Trade Patch v2026.6.4

이 압축파일은 Sidekick v2026.6.4 portable에 한국 POE/POE2 거래 API 주소 패치를 적용한 비공식 배포본입니다.

## 무엇이 바뀌었나

- 한국 거래 API 주소를 `poe.game.daum.net`에서 `poe.kakaogames.com`으로 변경했습니다.
- POE2 한국어 설정에서 `Sidekick failed to communicate with the trade API` / `Unauthorized`가 뜨는 문제를 우회합니다.
- 한국어 아이템 검색 기준으로 검증했습니다. 예: `진홍색 목걸이` 검색 및 한국어 결과 반환.

## 실행 방법

1. 압축을 원하는 폴더에 풉니다.
2. `Start-Sidekick-Clean.cmd`를 실행합니다.
3. POE/POE2를 관리자 권한으로 실행 중이면 Sidekick도 관리자 권한으로 뜰 수 있습니다.

## Sidekick 설정 권장값

- UI language: Korean
- Game language/parser: Korean
- League: POE2 현재 리그, 예: `Runes of Aldur`
- Force English trade results / Use invariant trade results: 꺼짐

## 업데이트 후 다시 오류가 나면

Sidekick 공식 업데이트가 `current\Sidekick.Data.dll`을 덮어쓰면 패치가 사라질 수 있습니다.

그때는 Sidekick을 종료한 뒤 `Apply-Sidekick-KakaoTradePatch.ps1`을 PowerShell로 실행하세요.

## WebView2 재실행 오류가 있으면

`0x8007139F` 또는 WebView2 관련 오류가 반복되면 `Start-Sidekick-Clean.cmd`로 실행하세요.
계속 반복되면 `Install-Sidekick-Guard.ps1`을 한 번 실행하면 WebView2 DPI 호환성 잔여값을 자동 정리합니다.

## 주의

- 공식 Sidekick 배포본이 아닙니다.
- 원본 프로젝트: https://github.com/Sidekick-Poe/Sidekick
- 원본 라이선스는 MIT이며 `LICENSE.txt`에 포함했습니다.
- 이 패치는 한국 서비스 주소 이전에 따른 임시 수정입니다. 공식 Sidekick에서 같은 수정이 반영되면 공식 최신 버전을 쓰는 것이 좋습니다.
