# 모드 런처 (Mod Launcher)

morulab에서 만든 Windows 앱과 Claude Code 모드를 한 창에서 설치하고 업데이트하는 Windows 앱이에요.

- 앱마다 설치된 버전과 실행 여부를 보여 주고, 새 버전이 나오면 **업데이트** 버튼이 떠요. 누르면 설치 파일을 받아 조용히 설치해요. 켜져 있던 앱은 닫았다가 다시 열어요.
- 아직 없는 앱은 **설치** 버튼 하나로 깔아요.
- Claude Code 모드는 설치·제거하고 켜고 끌 수 있어요.

## 설치

1. [Releases](https://github.com/morulab-taesoo/mod-launcher-releases/releases/latest)에서 `ModLauncher-Setup-<버전>.exe`를 받아 실행하고 **설치**를 눌러요. 관리자 권한은 필요 없어요.
   - 서명되지 않은 프로그램이라 Windows가 "PC 보호" 창을 띄울 수 있어요. **추가 정보 → 실행**을 누르세요.
2. 설치가 끝나면 런처가 열리고, 시작 메뉴와 바탕 화면에 **모드 런처**가 생겨요.

- 64비트 Windows에서 돌아요. 모드를 다루려면 Claude Code가 설치돼 있어야 해요.

## 쓰는 법

창 위쪽 툴바:

| 툴바 | 하는 일 |
|---|---|
| 새로 고침 (`F5`) | 설치 상태를 다시 읽고, 새 버전도 30분을 기다리지 않고 바로 확인해요 |
| 전체 업데이트 · N | 업데이트가 있는 앱·모드가 있을 때만 떠요. 한 번 묻고 차례로 모두 업데이트해요 |
| 정렬 | 이름 (가–하) · 최근 릴리스순 · 종류별. 고른 정렬은 다음에 켤 때도 그대로예요 |
| 모드·앱 찾기 | 이름·설명에 든 글자로 목록을 좁혀요 |
| 격자·목록 | 카드를 격자로 볼지 한 줄씩 볼지 바꿔요. 이것도 기억해요 |
| 설정(⚙, 제목 줄) | `claude.exe` 경로, 받은 설치 파일 폴더 열기, 설치·켜기·끄기 명령의 로그 |

목록의 카드마다 지금 상태에 맞는 버튼이 떠요.

| 카드 | 버튼 |
|---|---|
| 설치하지 않은 앱 | **설치** |
| 설치한 앱 | **열기**, 새 버전이 있으면 **업데이트**. **…** 메뉴에 종료·다시 설치·설치 폴더 열기·Windows 시작 시 실행(켬·끔)·릴리스 노트 보기·제거 |
| 모드 | **설치**, 설치했으면 **켜기**/**끄기**, 새 버전이 있으면 **업데이트**. **…** 메뉴에 업데이트 확인·설치 폴더 열기·제거 |

모드를 설치하거나 켜고 끈 뒤에는 열려 있는 Claude Code 세션에서 `/reload-plugins`를 하면 반영돼요.

### 런처에서 관리하는 것

| 이름 | 하는 일 | 받는 곳 |
|---|---|---|
| 로컬 검색 | 내 PC 문서(한글·워드·PDF 등)를 뜻으로 찾아요. Claude 도구로도 써요. | [local-search-releases](https://github.com/morulab-taesoo/local-search-releases) |
| 화면 번역 | 캡처한 화면의 글자를 읽어 제자리에 번역해요. Claude 도구로도 써요. | [image-translate-releases](https://github.com/morulab-taesoo/image-translate-releases) |
| VoiceNote | 녹음을 이 PC의 GPU·NPU로 받아 적고, 화자를 나누고, 회의록으로 정리해요. | [voicenote-releases](https://github.com/morulab-taesoo/voicenote-releases) |
| turn-tip (모드) | Claude Code의 턴이 끝날 때 확인하거나 직접 해야 할 일을 입력창 위 띠에 한 줄로 띄워요. | [turn-tip](https://github.com/morulab-taesoo/turn-tip) |
| 세션 진행 대시보드 | Claude 세션마다 지금 단계·걸린/예상 시간·백그라운드 작업·답을 기다리는 세션을 미니 창으로 보여 줘요. | [session-board-releases](https://github.com/morulab-taesoo/session-board-releases) |
| 세션 진행 대시보드 훅 (모드) | 작업 목록이 실제보다 뒤처지지 않게 붙잡고, 예상 시간을 넘기면 중간 점검·재계산을 하게 해요. 대시보드를 먼저 설치하세요. | [session-board-releases](https://github.com/morulab-taesoo/session-board-releases) |

목록은 이 저장소의 [`catalog.json`](catalog.json)이에요. 런처를 켤 때마다 읽어서, 새 앱이 추가되면 런처를 다시 깔지 않아도 보여요.

## 업데이트

런처에 새 버전이 나오면 창 오른쪽 아래 상태 줄에 **업데이트 V<버전> ↑** 버튼이 떠요. 누르면 설치 파일을 받아 실행하고 런처 창을 닫아요. 설치가 끝나면 새 버전이 열려요.

**0.1.8 이하에서 업데이트가 멈출 때:** 그 버전들은 런처에서 연 앱(세션 진행 대시보드·화면 번역 등)이 런처 파일을 쥐게 해서, 설치 중에 "모든 응용 프로그램을 자동으로 닫지 못했습니다" 창이 뜨거나 업데이트가 끝나도 버전이 그대로일 수 있어요. 0.2.1 부터는 설치 파일이 그런 앱을 끄고 설치해요. 그래도 멈추면 트레이에서 그 앱들을 끈 뒤 **재시도**를 누르거나, [릴리스](https://github.com/morulab-taesoo/mod-launcher-releases/releases/latest)에서 설치 파일을 받아 직접 실행하세요.

## 지우기

Windows 설정 → 앱에서 **모드 런처**를 제거해요. 런처로 설치한 앱과 모드는 그대로 남아요.

## 어떻게 동작하나요

- 새 버전은 각 앱의 공개 릴리스 저장소에서 확인해요 (GitHub, 로그인 없이).
- 설치 여부와 위치는 Windows에 등록된 설치 정보에서 찾고, 모드는 `claude plugin` 명령으로 다뤄요.
- 받은 설치 파일과 기록은 `%LOCALAPPDATA%\ModLauncher`에 둬요.

## 알려진 한계

- GitHub는 로그인 없이 시간당 60번까지만 물어볼 수 있어서, 새 버전은 30분에 한 번만 확인해요. 바로 확인하려면 툴바의 새로 고침 단추나 `F5`를 누르세요. 한도가 차면 풀릴 때까지 지난번 확인 결과를 보여 줘요.
