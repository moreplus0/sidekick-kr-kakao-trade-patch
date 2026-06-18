# v2026.6.4-kr-kakao-20260618

Sidekick v2026.6.4 portable 기반 한국 Kakao 거래 API 임시 패치 릴리스입니다.

## 포함 파일

- `Sidekick-KR-KakaoTrade-v2026.6.4-20260618.zip`
- `Sidekick-KR-KakaoTrade-v2026.6.4-20260618.zip.sha256.txt`

## 주요 변경

- 한국 POE/POE2 거래 웹/API 기본 URL을 Daum Games 도메인에서 Kakao Games 도메인으로 변경했습니다.
- 변경 파일: `src/Sidekick.Data/Languages/Implementations/GameLanguageKo.cs`
- 실제 diff는 `source-modification/Sidekick-KakaoTrade.patch`에 포함했습니다.

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
F824C1DCD9A556DBF04DF6DF861364747FFF2A8D9D498C0B4C155DB6BF55193B
```

## 주의

이 릴리스는 공식 Sidekick 배포본이 아닙니다. 한국 거래소 주소 이전에 대응하기 위한 임시 패치판입니다.
