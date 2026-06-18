# v2026.6.4-kr-kakao-20260618

Sidekick v2026.6.4 portable 기반 한국 Kakao 거래 API 임시 패치 릴리스입니다.

## 포함 파일

- `Sidekick-KR-KakaoTrade-v2026.6.4-20260618.zip`
- `Sidekick-KR-KakaoTrade-v2026.6.4-20260618.zip.sha256.txt`

## 주요 변경

- 한국 POE/POE2 거래 웹/API 기본 URL을 Daum Games 도메인에서 Kakao Games 도메인으로 변경했습니다.
- 변경 파일: `src/Sidekick.Data/Languages/Implementations/GameLanguageKo.cs`
- 실제 diff는 GitHub 저장소의 `source-modification/Sidekick-KakaoTrade.patch`에 보관했습니다.
- README에 실제 Sidekick API 오류 화면 예시와 문제 증상 설명을 포함했습니다.
- ZIP 파일은 실행에 필요한 포터블 파일만 남기고 설명서, 스크린샷, 작업용 `.ps1`, 소스 diff, 빌드 정보 파일은 제외했습니다.

## 검증

```text
LanguageParser=ko
LanguageUi=ko
LeagueId=poe2.Runes of Aldur
UseInvariantTradeResults=False
ParsedItem=진홍색 목걸이
DefinitionTradeType=진홍색 목걸이
SearchTotal=10000
```

fetch 결과에서 `진홍색 목걸이 - 환희`, `진홍색 목걸이 - 돌풍` 등 한국어 아이템명이 반환되는 것을 확인했습니다.

## ZIP SHA256

```text
ADF759289ED2DE92BD5152C894E00233A580C3AD68B550DCF9F03AF61AC4BF53
```

## 주의

이 릴리스는 공식 Sidekick 배포본이 아닙니다. 한국 거래소 주소 이전에 대응하기 위한 임시 패치판입니다.
