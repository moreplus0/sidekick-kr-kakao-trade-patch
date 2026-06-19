# v2026.6.4-kr-kakao-20260619

Sidekick v2026.6.4 portable 기반 한국 Kakao 거래 API 2차 임시 패치 릴리스입니다.

## 포함 파일

- `Sidekick-KR-KakaoTrade-v2026.6.4-20260619.zip`
- `Sidekick-KR-KakaoTrade-v2026.6.4-20260619.zip.sha256.txt`

## 주요 변경

- 한국 POE/POE2 거래 웹/API 기본 URL을 Daum Games 도메인에서 Kakao Games 도메인으로 변경했습니다.
- 2026-06-19 이후 Kakao `trade2/fetch` 응답의 `item.explicitMods[]`가 문자열 대신 객체로 내려오는 변경에 대응했습니다.
- 변경 파일:
  - `src/Sidekick.Data/Languages/Implementations/GameLanguageKo.cs`
  - `src/Sidekick.Common/Converters/StringOrObjectListJsonConverter.cs`
  - `src/Sidekick.Apis.Poe.Trade/Trade/Models/ApiItem.cs`
- 회귀 테스트: `tests/Sidekick.Apis.Poe.Tests/Trade/ApiItemModListParsing.cs`
- 실제 diff는 GitHub 저장소의 `source-modification/Sidekick-KakaoTrade-20260619.patch`에 보관했습니다.
- README에 실제 Sidekick API 오류 화면 예시와 2026-06-19 fetch listings 오류 화면을 포함했습니다.
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

```text
FetchModObjectItem=경계하는 시야 / 에메랄드 반지
FetchExplicitModObject=[Accuracy|정확도] +143
RegressionTest=ApiItemModListParsing.DeserializesModsReturnedAsStringsOrObjects
```

`dotnet test -c Release --filter FullyQualifiedName~ApiItemModListParsing` 통과를 확인했습니다.

## ZIP SHA256

```text
40E760BAA53BD7F66C1AC926E9FB04085098CA70FB7C53F8E0783D156263C47F
```

## 주의

이 릴리스는 공식 Sidekick 배포본이 아닙니다. 한국 거래소 주소 이전과 2026-06-19 거래 API 응답 변경에 대응하기 위한 임시 패치판입니다.
