# Sidekick KR Kakao Trade Patch 설명문

## GitHub 공개 배포 정보

- GitHub 저장소: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch
- 공유용 설명문: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/blob/main/%EA%B3%B5%EC%9C%A0%EC%9A%A9_%EC%84%A4%EB%AA%85%EB%AC%B8.md
- 게시판용 HTML: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/blob/main/%EA%B3%B5%EC%9C%A0%EC%9A%A9_%EA%B2%8C%EC%8B%9C%ED%8C%90_HTML.html
- 게시판용 HTML 원문 복사: https://raw.githubusercontent.com/moreplus0/sidekick-kr-kakao-trade-patch/main/%EA%B3%B5%EC%9C%A0%EC%9A%A9_%EA%B2%8C%EC%8B%9C%ED%8C%90_HTML.html
- 새 버전 알림글 HTML: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/blob/main/%EA%B2%8C%EC%8B%9C%ED%8C%90_%EC%83%88%EB%B2%84%EC%A0%84_%EC%95%8C%EB%A6%BC_20260621.html
- 오류 스크린샷 저장 위치: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/tree/main/assets/screenshots
- 릴리스 페이지: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/releases/tag/v2026.6.5-kr-kakao-20260621
- 바로 다운로드: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/releases/download/v2026.6.5-kr-kakao-20260621/Sidekick-KR-KakaoTrade-v2026.6.5-20260621.zip
- 체크섬 파일: https://github.com/moreplus0/sidekick-kr-kakao-trade-patch/releases/download/v2026.6.5-kr-kakao-20260621/Sidekick-KR-KakaoTrade-v2026.6.5-20260621.zip.sha256.txt

> 이 배포본은 공식 Sidekick 배포본이 아니라, 한국 POE/POE2 거래소 주소 이전 문제를 임시로 해결하기 위한 비공식 패치판입니다.
> 다운로드 ZIP에는 실행에 필요한 포터블 파일만 포함했습니다. 설명, 스크린샷, 체크섬, 패치 diff는 이 GitHub 저장소와 릴리스 페이지에서 확인할 수 있습니다.

## 한 줄 소개

이 프로그램은 공식 Sidekick v2026.6.5 portable에 한국 POE/POE2 거래소 Kakao Games 주소 패치를 적용한 비공식 임시 배포본입니다.

공식 Sidekick v2026.6.5에는 2026-06-19 이후 바뀐 거래 API 응답 구조 대응이 들어갔습니다. 다만 한국어 거래소 기본 주소는 아직 `poe.game.daum.net`으로 남아 있어, 한국어 POE2 설정에서는 공식 6.5로 업데이트해도 거래 API 오류가 반복될 수 있습니다. 이 배포본은 공식 6.5의 수정 사항은 그대로 유지하고, 한국 거래소 주소만 `poe.kakaogames.com`으로 바꾼 버전입니다.

## 문제 증상

한국어 POE2 환경에서 Sidekick 가격 검색을 실행하면 아래와 같은 API 오류 화면이 나올 수 있습니다.

![Sidekick API 통신 실패 오류](https://raw.githubusercontent.com/moreplus0/sidekick-kr-kakao-trade-patch/main/assets/screenshots/sidekick-api-communication-failed.png)

이미지 직접 보기: https://raw.githubusercontent.com/moreplus0/sidekick-kr-kakao-trade-patch/main/assets/screenshots/sidekick-api-communication-failed.png

또는 거래 API 인증 관련 안내가 표시되면서 검색 결과가 나오지 않을 수 있습니다.

![Sidekick 거래 API 인증 오류](https://raw.githubusercontent.com/moreplus0/sidekick-kr-kakao-trade-patch/main/assets/screenshots/sidekick-trade-api-auth-required.png)

이미지 직접 보기: https://raw.githubusercontent.com/moreplus0/sidekick-kr-kakao-trade-patch/main/assets/screenshots/sidekick-trade-api-auth-required.png

2026-06-19 전후로는 검색 API는 통과하지만 매물 목록을 가져오는 단계에서 아래처럼 오류가 날 수도 있었습니다. 이 부분은 공식 Sidekick v2026.6.5에서 수정됐고, 이번 배포본에도 공식 수정이 포함되어 있습니다.

![Sidekick fetch listings 오류](https://raw.githubusercontent.com/moreplus0/sidekick-kr-kakao-trade-patch/main/assets/screenshots/sidekick-fetch-listings-mod-object-error.png)

이미지 직접 보기: https://raw.githubusercontent.com/moreplus0/sidekick-kr-kakao-trade-patch/main/assets/screenshots/sidekick-fetch-listings-mod-object-error.png

대표적인 증상은 다음과 같습니다.

- `Sidekick failed to communicate with the API.`
- `Sidekick failed to communicate with the trade API.`
- `The trade website requires authentication, which Sidekick does not support currently.`
- `Sidekick could not fetch the listings from the trade API.`
- 검색 화면 우측에 `No results found`가 같이 표시됨
- Sidekick을 삭제 후 재설치하거나 캐시를 초기화해도 한국어 가격 검색 오류가 반복됨
- 영어 강제 검색으로는 일부 우회가 가능해 보일 수 있지만, 한국어 아이템 비교/검색 흐름에서는 실패함

## 만든 계기

최근 한국 POE/POE2 서비스의 내부 거래소 주소가 기존 `poe.game.daum.net`에서 `poe.kakaogames.com`으로 바뀌었습니다.

Sidekick v2026.6.5 기준으로도 한국어 거래 API 주소가 아직 Daum Games 주소로 남아 있어, 한국어 POE2 설정에서 아이템 가격 검색을 하면 다음과 같은 오류가 발생할 수 있습니다.

```text
Sidekick failed to communicate with the trade API.
The trade website requires authentication, which Sidekick does not support currently.
```

공식 Sidekick v2026.6.5는 “new API response changes” 대응 릴리스라서 fetch 응답 구조 문제는 해결됐지만, 한국 Kakao Games 거래소 주소 변경은 아직 반영되지 않았습니다. 당장 한국어 환경에서 가격 검색을 써야 하는 사람들이 있어, 공식 6.5를 기반으로 URL 패치만 다시 얹은 임시 배포본을 만들었습니다.

## 어떤 부분을 패치했나

Sidekick 소스의 한국어 게임 언어 설정 파일인 `GameLanguageKo.cs`에서 거래소 기본 주소를 바꿨습니다.

기존 주소:

```text
https://poe.game.daum.net/trade/
https://poe.game.daum.net/api/trade/
https://poe.game.daum.net/trade2/
https://poe.game.daum.net/api/trade2/
```

변경 주소:

```text
https://poe.kakaogames.com/trade/
https://poe.kakaogames.com/api/trade/
https://poe.kakaogames.com/trade2/
https://poe.kakaogames.com/api/trade2/
```

이번 20260621 배포에서는 공식 Sidekick v2026.6.5의 DLL들을 그대로 사용하고, 위 주소 변경이 들어간 `current\Sidekick.Data.dll`만 교체했습니다.

## 한국어 검색 검증 내용

영어 강제 검색이 아니라 한국어 결과가 실제로 내려오는 경로를 확인했습니다.

검증 결과:

```text
OfficialSidekick=Sidekick v2026.6.5
SourceTag=v2026.6.5
Build=dotnet build Sidekick.Data.csproj -c Release
BuildWarnings=0
BuildErrors=0
ContainsKakaoUrl=True
ContainsDaumUrl=False
```

Kakao POE2 거래 API fetch 검증:

```text
Endpoint=https://poe.kakaogames.com/api/trade2/fetch/4c1ac02a3a8363fbd69f215815242985c037d9e04056f60ae2745768dce9b646?query=WvynwMlzHm
Status=200
ItemName=경계하는 시야
BaseType=에메랄드 반지
League=Runes of Aldur
ExplicitModDescription=[Accuracy|정확도] +143
```

즉, 한국어 아이템명과 한국어 옵션이 Kakao 거래 API에서 정상 반환되는 것을 확인했습니다.

## 사용 방법

1. ZIP 파일을 원하는 폴더에 압축 해제합니다.
2. 압축을 푼 폴더의 `Sidekick.exe`를 실행합니다.
3. Sidekick 설정에서 게임 언어와 UI 언어를 Korean으로 맞춥니다.
4. 리그를 현재 POE2 리그로 선택합니다.
5. 영어 강제 검색 옵션은 꺼두는 것을 권장합니다.
6. POE2에서 아이템 위에 마우스를 올리고 Sidekick 가격 검색 단축키를 사용합니다.

기본 가격 검색 단축키는 Sidekick 기본값 기준 `Ctrl+D`입니다.

## ZIP 구성 정책

공유용 ZIP은 실행에 직접 필요한 파일만 남긴 최소 포터블 구성입니다.

```text
.portable
Sidekick.exe
Update.exe
current\
```

그래서 ZIP 안에는 설명서, 스크린샷, 작업용 PowerShell 스크립트, 소스 diff, 빌드 정보 파일을 넣지 않았습니다. 관련 설명은 이 저장소 README와 릴리스 노트에만 남겨두었습니다.

## 공식 업데이트 후 다시 안 되면

Sidekick 공식 업데이트가 실행되면 패치된 `Sidekick.Data.dll`이 공식 파일로 덮어써질 수 있습니다.

그 경우 다시 한국어 거래 API 오류가 날 수 있습니다. 이때는 Sidekick을 종료하고 이 릴리스의 ZIP을 다시 받아 새 폴더에 압축 해제한 뒤 `Sidekick.exe`를 실행하세요.

## 주의사항

- 이 파일은 공식 Sidekick 배포본이 아닙니다.
- 원본 Sidekick은 MIT 라이선스 프로젝트입니다.
- 원본 프로젝트 주소: https://github.com/Sidekick-Poe/Sidekick
- 공식 Sidekick v2026.6.5 릴리스: https://github.com/Sidekick-Poe/Sidekick/releases/tag/v2026.6.5
- 이 패치는 한국 POE/POE2 거래소 주소 이전에 대응하기 위한 임시 수정입니다.
- 공식 Sidekick에서 Kakao 주소 패치가 반영되면 공식 최신 버전을 사용하는 것이 가장 좋습니다.
- 사용 중 문제가 생기면 압축을 새 폴더에 다시 풀고 `Sidekick.exe`로 실행해 보세요.

## 포함 파일 요약

```text
.portable
  Velopack 포터블 실행 표식입니다.

Sidekick.exe
  포터블 루트 실행 파일입니다.

Update.exe
  Sidekick 포터블 런처/업데이트 구성에 필요한 실행 파일입니다.

current\
  실제 Sidekick 앱 파일과 Kakao 거래 API 주소가 적용된 current\Sidekick.Data.dll이 들어 있습니다.
```

## 요약

이 배포본은 공식 Sidekick v2026.6.5에 아직 반영되지 않은 한국 Kakao 거래소 주소 문제를 임시로 복구하기 위한 패치판입니다. 공식 6.5의 API 응답 구조 수정은 유지했고, 한국어 아이템명과 한국어 옵션이 Kakao 거래 API에서 반환되는 것까지 확인했습니다.
