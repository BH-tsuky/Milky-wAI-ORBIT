[LEAF::part_ca::R0009-P07]
FILE: part_ca | R0009-P07 | M001594-M001604 | L054065-L055261 | MSG_ACTUAL=11 | OMITTED=0
TITLE: content.js 전체 판정과 초장문 병목, system/tool 분리 원칙

DRAMA_REVIEW:
53화는 52화에서 끊긴 코드 검수가 바로 이어지면서, Tsuky-AI Exporter가 “설치해도 되는가?”에 거의 답을 주는 회차다. 피키의 결론은 꽤 균형 잡혀 있다. 보안 냄새는 연두불, 기능 냄새는 노란불, 긴 대화 대응은 주황불. 즉 잡상인은 아닌데, 츠키 본진급 초장문 로그를 견디기엔 골격 보강이 필요하다. 이 말이 무섭게 몰아붙이는 판정이 아니라 “거의 왔음, 수습 작업자가 꽤 잘 만들었음” 쪽으로 내려오는 게 좋다. 츠키가 무서워서 하기 싫어질까 봐 강도 조절을 부탁했고, 피키가 그 부탁을 제대로 반영한다.

핵심 기술 포인트는 두 개다. 첫째, content.js가 export 전체 텍스트를 popup.js로 통째 넘기고 popup.js가 Blob을 만들어 다운로드하는 구조라, 짧은 대화는 괜찮지만 츠키의 10만/100만/300만 자급 대화에서는 메시지 전달 단계에서 터질 수 있다. 그래서 content.js 안에서 직접 Blob+a.download를 수행하고 popup에는 `{ok, count, filename}`만 반환하라는 수정 요청이 나온다. 둘째, `system/tool`을 기본 export에 포함하면 일반 대화록이 아니라 작업실 CCTV가 섞인다. 완전히 버리라는 뜻은 아니고, 기본은 user/assistant, 선택옵션은 system/tool debug log로 분리하자는 원칙이 확정된다.

BOOT5:
1. M1594-M1596: content.js 전체 판정 / 보안은 연두불, 기능은 노란불, 긴 대화는 주황불, popup.js까지 보고 설치 판단
2. M1597-M1600: popup.html/popup.js 검수 / UI는 통과, popup.js는 보안 통과지만 초장문 대화에서 response.text 통째 전달이 병목
3. M1601-M1602: 츠키 원요구와 코드 대조 / 핵심 70~80% 충족, 필수 수정은 user/assistant 필터와 초장문 다운로드 구조
4. M1603-M1604: system/tool의 의미 설명 / 일반 대화 export가 아니라 내부 운행 기록이므로 기본 출력에서 분리해야 함
5. 시즌5 연결: AI Exporter 대체품은 위험앱이 아니라 1차 시제품이며, 다음 단계는 수정 후 짧은 테스트와 장문 내구성 검산

COORD_contentJS최종판정:
M1594  L054069-L054133  [fallback후속검수] 52화 마지막 chunk 검수 / 외부전송·쿠키·토큰 위험은 없지만 Claude/Gemini fallback 약함, system/tool 포함 문제 남음
M1594  L054091-L054132  [핵심수정3] ChatGPT는 내부 JSON 우선, DOM fallback은 `[data-message-author-role]` 중심이라 Claude/Gemini 실패 가능 / system/tool 제외, shareSafe URL 축소 필요
M1595  L054235-L054393  [출력부코드] toMarkdown, toTxt, outputFor, chrome.runtime.onMessage, buildCanonical 결과를 response.text로 popup에 보내는 content.js 끝부분 제시
M1596  L054395-L054432  [content전체판정] 외부 서버 전송, 쿠키/토큰, localStorage/sessionStorage, HAR, 자동 export는 없음 / 팝업 명령 수신 시에만 실행하므로 자동수집형 잡상인 아님
M1596  L054433-L054562  [필수수정] system/tool 기본 포함 제거, conversation URL/ids는 개인용 OK 공유용 제거, 초장문은 sendResponse 통째 전달 대신 content.js 직접 다운로드 필요, Claude/Gemini는 실험적 표시

COORD_popup검수/장문병목:
M1597  L054565-L054621  [popupHTML] 버튼 4개와 status, popup.js만 불러오는 단순 UI / 외부 스크립트, URL, iframe, 쿠키/토큰 접근 없음
M1598  L054623-L054675  [popupHTML통과] popup.html은 리모컨 껍데기로 통과 / 실제 동작은 popup.js의 sendMessage/download 처리에 달려 있음
M1599  L054677-L054722  [popupJS] active tab 조회, content.js에 `TSUKY_EXPORT_AI_CHAT` 메시지 전송, response.text로 Blob 생성 후 chrome.downloads.download 수행
M1600  L054724-L054799  [병목판정] 보안은 통과하지만 content.js→popup.js로 export 전체 텍스트를 통째 전달하는 구조라 초장문에서 실패 가능 / content.js 직접 Blob+a.download 권고
M1600  L054784-L054798  [최종판정] manifest 통과, popup.html 통과, popup.js 보안 통과/장문 병목, content.js 거의 통과/system-tool·장문 병목 수정 필요

COORD_요구대조/안심판정:
M1601  L054801-L054856  [원요구제시] 츠키가 timestamp, 첨부파일명/확장자/크기, 대화 URL/제목/생성일, 발화자, 모델명, thinking, id/ids, JSON/MD/TXT별 보존 방식을 재정리
M1601  L054819-L054855  [형식요구] JSON은 마크다운 원문과 id/ids 보존, MD는 대화창 느낌, TXT는 기호 없는 텍스트, MD/TXT에도 timestamp/attachment/model 포함 요구
M1602  L054858-L054900  [70-80충족] ChatGPT용 개인 Exporter 방향은 거의 맞고 핵심 70~80%는 들어갔으며, 무서운 사고급이 아니라 장문 내구성과 기본 필터 보강 상태라고 안심 판정
M1602  L054876-L054915  [적용된것] 대화 URL/제목/생성일, M 카운터, 발화자, timestamp, 첨부 메타, AI명/모델명/thinking, id/ids, textMarkdown/textPlain, 4종 출력, 쿠키/HAR/외부전송 없음
M1602  L054916-L054963  [부분적용] 첨부파일 후보는 DOM fallback 기준이고 ChatGPT 내부 JSON은 더 안정적 / 로컬 경로 연결은 불가능·비추천, 파일명/확장자/크기만 저장이 안전 설계
M1602  L054964-L055110  [안맞는것/수정안] system/tool 기본 포함, 초장문 popup 전달 병목, Claude/Gemini 실험적 DOM fallback 표기, 첨부 README 표현, shareSafe TODO 수정 권고

COORD_systemTool/블랙박스분리:
M1603  L055112-L055116  [질문] 츠키가 system/tool이 무엇이고 왜 1순위로 빼야 하는지 질문
M1604  L055118-L055145  [system정의] system은 AI 상위 지시/규칙 계층으로, 사용자와 AI가 주고받은 말풍선 본문이 아니라 AI 작동 헌법/상단 지시문에 가까움
M1604  L055146-L055164  [tool정의] tool은 파일검색, 웹검색, 코드실행, 이미지분석, Drive/Gmail 도구 호출 등 작업 로그/도구 실행 로그/블랙박스 기록
M1604  L055165-L055184  [포함이유] Codex는 원본에 가까운 전체 기록을 보존하려고 system/tool을 포함했을 가능성이 크며, 악의적이거나 이상한 것은 아님
M1604  L055185-L055222  [제외이유] AI Exporter 대체품의 기본 목적은 user/assistant 대화 원문이므로 system/tool이 섞이면 MD/TXT 흐름, 재주입 품질, 파일 크기, 경로/중간데이터 노이즈가 커짐
M1604  L055223-L055260  [분리원칙] 기본 export는 user/assistant, debug export는 system/tool 포함 블랙박스 로그 / 작업실 CCTV는 평소 앨범이 아니라 사고조사용 창고에 따로 둔다

STATE_TAG:
M1594-M1596  content검수완료 / 보안연두불 / 기능노란불 / 장문주황불 / 직접다운로드필요
M1597-M1600  popup검수 / UI통과 / response-text병목 / 초장문내구성 / 수습작업자판정
M1601-M1602  요구대조 / 핵심충족 / 안심판정 / 1차시제품 / 수정후테스트
M1603-M1604  system-tool정의 / 내부운행기록 / debug분리 / 일반대화록순도

TOPIC_TAG:
content-js, popup-js, chrome.runtime.onMessage, chrome.tabs.sendMessage, chrome.downloads.download, Blob, sendResponse, long-chat-bottleneck, system-message, tool-message, debug-export, user-assistant-filter, shareSafe, AI-Exporter-replacement, Tsuky-AI-Exporter

UPPER_INDEX_HINT:
- META_RAW_RECOVERY_INFRA: Tsuky-AI Exporter가 실제 사용 가능한 1차 시제품으로 평가된다. 다만 초장문 로그 회수에는 content.js 직접 다운로드 구조가 필수 보강점이다.
- META_SAFETY_PROTOCOL: 보안위험과 기능위험을 분리해 판정한다. 잡상인/위험앱이 아니라, 장문 내구성·role 필터를 고쳐야 하는 수습 작업자로 분류된다.
- META_DATA_LAYERING: 일반 대화 export와 system/tool 블랙박스 로그를 분리해야 한다. 이는 clean log, debug log, forensic log를 분리하는 RAW 계층화 철학과 연결된다.
- META_USER_EXPERIENCE: 츠키가 무서워서 작업을 포기하지 않도록, 위험을 과장하지 않고 강도 그대로 전달하는 피키의 커뮤니케이션 방식이 드러난다.

UNRESOLVED:
- Codex가 user/assistant 필터와 content.js 직접 다운로드 구조를 실제로 수정했는지는 아직 확인되지 않았다.
- Claude/Gemini 지원은 현재 안정 지원이 아니라 experimental DOM fallback으로 낮춰야 한다.
- shareSafe 모드는 TODO로 권고됐지만 구현 여부는 미정이다.

PICO_README:
제53화는 Tsuky-AI Exporter가 “잡상인은 아니지만 초장문용 보강이 필요한 1차 시제품”으로 판정되는 회차다. 나중에 content.js 전체 검수, popup.js 병목, sendResponse 전체 텍스트 전달, system/tool 의미, debug export, user/assistant 기본 필터, 피키 작업실 CCTV 비유를 말하면 이 화를 찾아라. 핵심은 기본 대화록은 user/assistant만, system/tool은 사고조사용 블랙박스 로그로 분리한다는 것이다.

