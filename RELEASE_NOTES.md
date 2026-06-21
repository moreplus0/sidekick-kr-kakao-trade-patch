# v2026.6.5-kr-kakao-20260621

Sidekick v2026.6.5 portable 기반 한국 Kakao 거래 API 임시 패치 릴리스입니다.

## 포함 파일

- `Sidekick-KR-KakaoTrade-v2026.6.5-20260621.zip`
- `Sidekick-KR-KakaoTrade-v2026.6.5-20260621.zip.sha256.txt`

## 주요 변경

- 기반 버전을 공식 Sidekick v2026.6.5 portable로 업데이트했습니다.
- 공식 v2026.6.5의 2026-06-19 trade API 응답 구조 변경 대응을 그대로 포함합니다.
- 한국 POE/POE2 거래 웹/API 기본 URL을 Daum Games 도메인에서 Kakao Games 도메인으로 변경했습니다.
- 이번 릴리스에서 직접 수정한 파일:
  - `src/Sidekick.Data/Languages/Implementations/GameLanguageKo.cs`
- 실제 diff는 GitHub 저장소의 `source-modification/Sidekick-KakaoTrade-20260621.patch`에 보관했습니다.
- ZIP 파일은 실행에 필요한 포터블 파일만 남기고 설명서, 스크린샷, 작업용 `.ps1`, 소스 diff, 빌드 정보 파일은 제외했습니다.

## 검증

```text
OfficialSidekick=Sidekick v2026.6.5
SourceTag=v2026.6.5
SourceCommit=0870b25c3ac178c4e29c1405f906b61e1bb63dea
Build=dotnet build Sidekick.Data.csproj -c Release
BuildWarnings=0
BuildErrors=0
```

```text
PatchedDll=current\Sidekick.Data.dll
ContainsKakaoUrl=True
ContainsDaumUrl=False
PatchedDllSha256=13DF4B8DB3660AE3E2FE7D7EB207674836279EB1252C0CB270AB200FC5B0F53A
```

Kakao POE2 거래 API fetch 응답에서 한국어 아이템과 한국어 옵션이 반환되는 것을 확인했습니다.

```text
Endpoint=https://poe.kakaogames.com/api/trade2/fetch/4c1ac02a3a8363fbd69f215815242985c037d9e04056f60ae2745768dce9b646?query=WvynwMlzHm
Status=200
ItemName=경계하는 시야
BaseType=에메랄드 반지
League=Runes of Aldur
ExplicitModDescription=[Accuracy|정확도] +143
```

## ZIP SHA256

```text
33500AA23A06051CC490C6C55E6AD11628AF35850FC4D2C3CD001DF17F12FA7E
```

## 주의

이 릴리스는 공식 Sidekick 배포본이 아닙니다. 공식 v2026.6.5의 API 응답 구조 수정 위에 한국 Kakao 거래소 URL 패치만 추가한 임시 배포본입니다.
