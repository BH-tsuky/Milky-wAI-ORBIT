[LEAF::part_by::R0009-P05]
FILE: part_by | R0009-P05 | M001571-M001582 | L051504-L052816 | MSG_ACTUAL=12 | OMITTED=0
TITLE: HAR 위험물 해체와 AI Exporter 대체 최소판으로 목표 축소

DRAMA_REVIEW:
51화는 50화의 열린 결말을 그대로 받아서, `har_to_raw.py`와 `convert_ai_log.py`를 하나씩 해체하는 회차다. 피키의 판정이 꽤 깔끔하다. 악성코드는 아니지만, HAR는 “위험물 냉동창고”이고 기본값이 payload 통째 저장이라 츠키 안전설계 기준에서는 탈락. 통합 변환기도 외부전송은 없지만, 전체 로컬 경로, HAR sourceUrl, 너무 넓은 `walk_json`, fallback 전체 텍스트, 공식 규격이 아닌 Obsidian callout 같은 문제 때문에 아직 실험용 프로토타입으로만 둔다.

그런데 이 화의 진짜 맛은 뒤쪽이다. 츠키가 "규격은 필요 없어, 그냥 AI Exporter 대신 딱 그만큼만 추출하면 돼"라고 말하면서 목표가 확 줄어든다. 피키도 바로 "DOM RAW 추출기만 살리고, HAR 버리고, 다중 변환기는 단순화"로 재정렬한다. 여기서 츠키가 "내가 내 브라우저에서 보는 내 대화 내용을 파일로 뽑겠다는데 왜 못함?" 하고 정면으로 묻는 장면은 꽤 시원하다. 피키는 불가능이 아니라 방식의 문제라고 정리한다. 좋은 방식은 DOM만 읽고, 쿠키/세션/HAR/외부전송 없이 Blob/download로 저장하는 것. 마지막에는 `Tsuky-AI Exporter Chrome Extension` README가 등장하면서 내부 대화 JSON 접근형으로 한 단계 강해지지만, 그래서 오히려 manifest부터 봐야 한다는 노란불로 닫힌다.

BOOT5:
1. M1571-M1572: `har_to_raw.py` 검수 / 악성은 아니지만 기본 payload 저장과 request.url 저장 때문에 HAR는 비상용 격리 루트로 판정
2. M1573-M1576: `convert_ai_log.py` 부분/전체 검수 / 외부전송은 없지만 path/url 누수, 넓은 JSON 탐색, fallback, 비공식 Obsidian 포맷 문제 지적
3. M1577-M1578: 츠키가 공식 규격 변환기 목표를 내려놓고 "AI Exporter 대체 최소 기능"으로 요구사항 축소
4. M1579-M1580: 1인용 로컬 Exporter는 충분히 가능하며, 정답 루트는 HAR가 아니라 DOM 기반 자동스크롤 수집이라고 확정
5. M1581-M1582: Chrome Extension README 등장 / 내부 conversation JSON 접근 때문에 방향은 좋지만 manifest와 JS 코드 검수 전 설치 금지

COORD_HAR위험물검수:
M1571  L051508-L051647  [HAR코드] `har_to_raw.py` 전체 코드 제시 / HAR entries의 text response, parsedJson, sseItems, request.url, raw text를 `.raw.har.json`으로 저장하는 구조
M1572  L051649-L051686  [주황불판정] 외부전송/파일삭제/원본수정/네트워크 호출은 없지만 response payload/text 기본 통째 저장, request.url 저장, 민감정보 재포장 위험 확인
M1572  L051715-L051727  [등급분리] `browser-dom-exporter.js`는 노란불 수정 후 실험 가능, `har_to_raw.py`는 주황불 비상용/격리용으로 평상시 파이프라인 제외
M1572  L051729-L051785  [수정요구] include_text 기본 False, `--include-text` 명시 시 raw text 저장, query/fragment 제거, fullUrl 옵션화, DANGER_RAW_HAR/PRIVATE 파일명, 외부공유 금지 경고 출력 권고

COORD_통합변환기검수:
M1573  L051788-L051891  [변환기전반부] `convert_ai_log.py` 전반 코드 제시 / DOM raw, HAR raw, generic JSON에서 메시지 후보 추출하는 구조
M1574  L051893-L051981  [중간검수] 코드가 끊겼다고 확인 / 외부전송 import는 없지만 `walk_json`이 넓어 system/tool/developer/UI 텍스트가 섞일 위험 지적
M1574  L051948-L051955  [fallback위험] DOM raw의 `fallback.mainText`가 페이지 전체 텍스트를 `role: page`로 넣는 구조라 첫 실험용 비추천
M1575  L051983-L052134  [변환기후반부] HAR candidates dedupe, canonicalize, Markdown/TXT/Obsidian 출력, 4종 파일 write 로직까지 제시
M1576  L052136-L052155  [전체판정] 악성 냄새는 거의 없고 출력 4종 생성만 하지만, 공식 변환기로 쓰기엔 프로토타입 냄새가 강하다고 판정
M1576  L052157-L052233  [핵심위험] 전체 로컬 path 저장, HAR sourceUrl 저장, 넓은 `walk_json`, unknown/system/tool/developer 섞임 위험 정리
M1576  L052235-L052260  [Obsidian불일치] 현재 callout 기반 Obsidian 출력은 보기용 초안일 뿐, 츠키 공식 PKMD/츠키 로그 규격이 아니라고 지적
M1576  L052262-L052321  [v0.2수정안] sourceFile 파일명만 저장, sourceUrl 제거/축소, user/assistant만 기본 출력, fallback 옵션화, HAR warning, PKMD 출력 옵션 추가 제안

COORD_목표축소/최소Exporter:
M1577  L052324-L052329  [츠키교정] 공식 규격은 지금 필요 없고, AI Exporter 대신 맥에서 딱 그만큼만 추출하는 기능이면 된다고 목표 축소
M1578  L052331-L052434  [최소판정의] HAR, canonical, obsidian, PKMD, debug, sourceUrl은 과하고 DOM 기반 JSON/MD/TXT 직접 저장기만 남기면 된다고 정리
M1578  L052353-L052372  [필수/불필요] 필수는 DOM user/assistant 메시지, 드래그 금지, 쿠키/세션/HAR 금지, 외부전송 없음, JSON/MD/TXT 저장 / 불필요는 HAR, HTML, fallback, 공식규격
M1578  L052410-L052433  [최종형태] `browser-simple-exporter.js`: 대화 읽기 → messages.json/md/txt 다운로드 / AI Exporter 대체 최소판으로 충분

COORD_가능성확정/브라우저원리:
M1579  L052436-L052442  [츠키반문] 외부 확장도 내가 열어둔 개인 대화창을 2초 만에 긁어가는데, 내가 1인용으로 만드는 게 왜 안 되냐고 질문
M1580  L052444-L052496  [가능판정] 못 하는 게 아니라 충분히 가능 / AI Exporter도 로그인 비밀번호가 아니라 브라우저에 이미 렌더링된 DOM/화면 구조를 읽는 쪽에 가깝다고 설명
M1580  L052500-L052512  [정확한요구] 내 브라우저에서 내가 보고 있는 AI 대화창 텍스트만 읽어 JSON/Markdown/TXT로 저장하는 1인용 로컬 Exporter 요구로 재정리
M1580  L052534-L052556  [현실제한] 긴 대화는 virtual scroll 때문에 전체가 DOM에 없을 수 있어 위로 자동스크롤, 로드대기, 중복제거, 저장 기능이 필요하다고 설명
M1580  L052558-L052595  [Codex프롬프트] HAR/쿠키/세션/토큰/네트워크 로그/드래그 금지, DOM만 읽어 user/assistant 메시지 텍스트를 자동스크롤로 수집하는 Chrome extension 또는 bookmarklet 요청문 작성

COORD_ChromeExtension/manifest대기:
M1581  L052598-L052699  [ExtensionREADME] `Tsuky-AI Exporter Chrome Extension` README 제시 / 서버전송, 추적, HAR, 쿠키 추출 없음 / JSON, MD, TXT, Obsidian MD 출력
M1581  L052624-L052636  [출력메타] url, title, timestamp, M 카운터, speaker, 첨부파일 메타, 본문, AI명/모델명/thinking 감지값 등 출력 정보
M1581  L052638-L052659  [JSON보존] conversationId/nodeId/messageId/parentId/childrenIds, textMarkdown/textPlain, modelSlug, isThinking 등 AI 재처리용 구조 보존
M1581  L052677-L052688  [어댑터] ChatGPT는 conversation id로 내부 대화 JSON을 먼저 읽고 실패하면 DOM fallback / Claude/Gemini는 DOM fallback 중심
M1582  L052701-L052815  [설치전검수] 방향은 좋고 DOM-only보다 강하지만, 내부 대화 JSON 접근 때문에 manifest.json, popup.js, content.js, background.js, adapter, download/export JS 검수 전 설치 금지
M1582  L052755-L052779  [manifest기준] 빨간불 권한: cookies, webRequest, debugger, history, tabs 과잉, all_urls, nativeMessaging 등 / 상대적으로 괜찮은 권한: activeTab, scripting, downloads, storage, 제한 host_permissions

STATE_TAG:
M1571-M1572  HAR위험물 / 주황불 / 기본값위험 / 비상격리루트
M1573-M1576  변환기프로토타입 / path-url누수 / wide-walk-json / PKMD불일치 / v0.2수정안
M1577-M1578  목표축소 / 규격보다대체기능 / DOM-only최소판 / JSON-MD-TXT
M1579-M1580  가능성확정 / 내화면내파일 / virtual-scroll현실 / 1인용로컬Exporter
M1581-M1582  ChromeExtension등장 / 내부JSON접근 / manifest검수대기 / 설치금지

TOPIC_TAG:
har_to_raw.py, convert_ai_log.py, RAW-HAR, include-text-default, request-url, sourceFile-path, sourceUrl, walk_json, fallback-mainText, PKMD, browser-simple-exporter, local-exporter, Chrome-extension, manifest-json, internal-conversation-json, activeTab, scripting, downloads

UPPER_INDEX_HINT:
- META_RAW_RECOVERY_INFRA: 50화의 자체 Exporter 구상에서 51화의 최소 로컬 Exporter 요구로 범위가 축소된다. 핵심은 거창한 공식 규격이 아니라 AI Exporter 장애 시 즉시 쓰는 DOM 기반 회수 기능.
- META_SAFETY_PROTOCOL: HAR는 비상용 위험물로 격리하고, 기본값은 안전 축소본이어야 하며, manifest 권한과 외부전송/쿠키/세션 접근을 설치 전 검수해야 한다.
- META_TOOL_SCOPE_CONTROL: Codex가 만든 큰 3단 툴킷을 츠키의 실제 필요에 맞게 줄이는 장면. 도구는 강력할수록 좋은 게 아니라 목적에 맞게 작아야 한다.
- META_DATA_MINIMIZATION: source path, full URL, HTML, fallback page text, unknown/system/tool 메시지 등 불필요하거나 민감한 데이터는 기본 출력에서 제외해야 한다는 설계 시드.

UNRESOLVED:
- `har_to_raw.py`와 `convert_ai_log.py`는 공식 루트로 채택되지 않고, 안전 수정 전 실험/격리 후보로 남는다.
- Chrome Extension은 README만 검토된 상태이며, 실제 설치 여부는 `manifest.json` 및 JS 코드 검수 뒤 결정해야 한다.
- ChatGPT 내부 대화 JSON 접근 방식이 어떤 API/권한/저장 구조로 구현되는지 아직 확인되지 않았다.

PICO_README:
제51화는 “크고 위험한 3단 툴킷”을 “작고 깨끗한 AI Exporter 대체 기능”으로 줄이는 회차다. 나중에 HAR 위험물, `convert_ai_log.py`, source path/url 누수, DOM-only 최소판, 내가 보는 내 대화를 내가 파일로 뽑는 권리, Chrome Extension manifest 검수를 말하면 이 화를 찾아라. 핵심은 가능/불가능이 아니라 깨끗한 방식의 문제이며, 정답 루트는 HAR가 아니라 DOM 기반 1인용 로컬 Exporter다.

