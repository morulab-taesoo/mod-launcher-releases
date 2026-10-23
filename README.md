# 모드 런처 (Mod Launcher)

morulab에서 만든 Windows 프로그램과 Claude Code 모드를 한 창에서 설치하고 업데이트하는 런처예요.

- 설치된 프로그램은 버전과 실행 여부를 보여 주고, 새 버전이 나오면 **업데이트** 버튼이 떠요. 누르면 설치 파일을 받아 조용히 설치해요. 켜져 있던 프로그램은 닫았다가 다시 열어요.
- 아직 없는 프로그램은 **설치** 버튼 하나로 깔 수 있어요.
- Claude Code 모드는 켜고 끄거나 설치·제거할 수 있어요 (Claude Code가 설치돼 있어야 해요).

## 설치

1. [Releases](https://github.com/morulab-taesoo/mod-launcher-releases/releases)에서 `ModLauncher-Setup-<버전>.exe`를 받아 실행하고 **설치**를 누르면 돼요. 관리자 권한은 필요 없어요.
   - 서명되지 않은 프로그램이라 Windows가 "PC 보호" 창을 띄울 수 있어요. **추가 정보 → 실행**을 누르세요.
2. 시작 메뉴의 **모드 런처**로 열어요. 런처도 새 버전이 나오면 자기 카드에서 업데이트해요.
- 지우려면 Windows 설정 → 앱에서 **모드 런처**를 제거해요.

## 런처에서 관리하는 프로그램

| 프로그램 | 하는 일 | 설치 파일 |
|---|---|---|
| 로컬 검색 | 내 PC 문서(한글·워드·PDF 등)를 뜻으로 찾아요. Claude 도구로도 써요. | [local-search-releases](https://github.com/morulab-taesoo/local-search-releases/releases) |
| 화면 번역 | 캡처한 화면의 글자를 읽어 제자리에 번역해요. Claude 도구로도 써요. | [image-translate-releases](https://github.com/morulab-taesoo/image-translate-releases/releases) |

목록은 이 저장소의 [`catalog.json`](catalog.json)이에요. 런처가 켤 때마다 읽어서, 새 프로그램이 추가되면 런처를 다시 깔지 않아도 보여요.

## 어떻게 동작하나요

- 새 버전은 각 프로그램의 공개 릴리스 저장소에서 확인해요 (GitHub, 로그인 없이).
- 설치 여부와 위치는 Windows에 등록된 설치 정보에서 찾아요.
- 받은 설치 파일과 기록은 `%LOCALAPPDATA%\ModLauncher`에 두고, 설치가 끝나면 설치 파일은 지워요.
