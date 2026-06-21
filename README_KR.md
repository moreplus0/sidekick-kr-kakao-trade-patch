# Sidekick KR Kakao Trade Patch v2026.6.5

이 압축파일은 공식 Sidekick v2026.6.5 portable을 기반으로, 한국 POE/POE2 거래 API 주소만 Kakao Games 주소로 바꾼 비공식 임시 배포본입니다.

공식 v2026.6.5에는 2026-06-19 이후 바뀐 거래 API 응답 구조 대응이 들어갔지만, 한국어 거래소 주소는 아직 `poe.game.daum.net`으로 남아 있습니다. 그래서 공식 Sidekick을 업데이트해도 한국어 POE2 거래 검색에서 API 오류가 반복될 수 있습니다.

## 다운로드

- 릴리스 페이지: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/releases/tag/v2026.6.5-kr-kakao-20260621
- ZIP 다운로드: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/releases/download/v2026.6.5-kr-kakao-20260621/Sidekick-KR-KakaoTrade-v2026.6.5-20260621.zip
- SHA256: `33500AA23A06051CC490C6C55E6AD11628AF35850FC4D2C3CD001DF17F12FA7E`

## 무엇이 바뀌었나

- 기반 버전을 공식 Sidekick v2026.6.5 portable로 올렸습니다.
- 공식 v2026.6.5의 trade fetch 응답 구조 변경 대응을 그대로 포함합니다.
- 한국 거래 API 주소를 `poe.game.daum.net`에서 `poe.kakaogames.com`으로 변경했습니다.
- 변경 DLL은 `current\Sidekick.Data.dll`입니다.
- 한국어 아이템 fetch 검증: `경계하는 시야 / 에메랄드 반지`, `[Accuracy|정확도] +143`.

## 실행 방법

1. ZIP 파일을 원하는 폴더에 압축 해제합니다.
2. 압축을 푼 폴더의 `Sidekick.exe`를 실행합니다.
3. Sidekick 설정에서 UI 언어와 게임 언어를 Korean으로 맞춥니다.
4. 리그를 현재 POE2 리그로 선택합니다.
5. 영어 강제 검색 옵션은 꺼두는 것을 권장합니다.

## ZIP 구성

다운로드 ZIP에는 실행에 필요한 포터블 파일만 포함했습니다.

```text
.portable
Sidekick.exe
Update.exe
current\
```

설명서, 스크린샷, 작업용 PowerShell 스크립트, 소스 diff, 빌드 정보 파일은 ZIP 안에 넣지 않았습니다. 관련 자료는 GitHub 저장소와 릴리스 페이지에서 확인할 수 있습니다.

## 주의

- 공식 Sidekick 배포본이 아닙니다.
- 원본 프로젝트: https://github.com/Sidekick-Poe/Sidekick
- 원본 라이선스는 MIT이며 라이선스 전문은 이 저장소의 `LICENSE`에서 확인할 수 있습니다.
- 공식 Sidekick에서 한국 Kakao 거래소 주소 패치가 반영되면 공식 최신 버전을 사용하는 것이 가장 좋습니다.
- 공식 업데이트 후 다시 API 오류가 나면 이 릴리스의 ZIP을 새 폴더에 압축 해제해서 실행하세요.
