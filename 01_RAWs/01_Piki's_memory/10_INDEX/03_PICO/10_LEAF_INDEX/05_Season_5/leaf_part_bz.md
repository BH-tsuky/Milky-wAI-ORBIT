[LEAF::part_bz::R0009-P06]
FILE: part_bz | R0009-P06 | M001583-M001593 | L052817-L054064 | MSG_ACTUAL=11 | OMITTED=0
TITLE: Tsuky-AI Exporter manifest 통과 후보와 content.js 핵심 검수

DRAMA_REVIEW:
52화는 이제 진짜 확장 프로그램 해부실이다. manifest가 먼저 나오고, 피키는 권한 목록을 보자마자 “생각보다 깔끔함, 거의 연두불”이라고 판정한다. 위험권한인 cookies, webRequest, debugger, history, all_urls, nativeMessaging이 없고, activeTab/scripting/downloads와 제한된 host_permissions만 있어서 1인용 로컬 Exporter의 최소 권한에 가깝다. 그래도 content.js 보기 전까지 설치 승인은 보류. 여기서 피키가 “잡상인 냄새는 약함”이라고 말하는 게, 앞 시즌의 잡상인 필터 역할과 딱 이어진다.

이후 content.js는 세 덩어리로 검수된다. 첫 덩어리는 ChatGPT 내부 conversation endpoint를 상대경로로 fetch하는 민감부다. 쿠키 문자열을 직접 읽는 건 아니지만 `credentials: "include"`로 로그인 세션을 이용해 내부 JSON을 읽으므로, 이 확장의 핵심 기능이자 가장 조심해야 할 지점으로 분류된다. 둘째 덩어리는 대화 branch/chronological 정렬, messageText, 첨부파일 메타 추출이라 꽤 정교하고 악성 냄새는 없다. 셋째 덩어리는 모델명/thinking/ids/tree 구조를 보존하는 정규화부인데, 개인 백업용으로는 강하지만 공유용으로는 conversationId, nodeId, messageId, fileId를 제거하는 share-safe 옵션이 필요하다고 잡힌다. 마지막에는 system/tool 포함과 DOM fallback/stripMarkdown 코드가 나오지만, 이 chunk는 피키 검수가 다음 화로 넘어가는 상태로 끊긴다.

BOOT5:
1. M1583-M1584: `manifest.json` 검수 / 최소 권한에 가까운 연두불 후보지만 content.js/popup.js 검수 전 설치 보류
2. M1585-M1586: content.js 전반부 / ChatGPT 내부 JSON endpoint를 로그인 세션으로 읽는 핵심 민감부 확인
3. M1587-M1588: 대화 branch/chronological 정렬, 메시지 본문, 첨부파일 메타데이터 추출부는 정교하고 대체로 양호
4. M1589-M1590: ChatGPT 메시지 정규화부 / ids, fileId, model metadata는 개인 백업용으로는 강하지만 외부공유용 분리 필요
5. M1591-M1593: `canonicalFromChatGptRaw`, DOM fallback, `stripMarkdown`, headerLine 일부 코드가 이어지며 system/tool 기본 포함 문제가 드러남

COORD_manifest/권한검수:
M1583  L052821-L052853  [manifest제시] `Tsuky-AI Exporter` manifest / Manifest V3, activeTab/scripting/downloads, ChatGPT/Claude/Gemini 제한 host_permissions, content.js document_idle
M1584  L052855-L052904  [연두불후보] cookies, webRequest, debugger, history, storage, all_urls, nativeMessaging 없음 / 현재 탭, 스크립트 실행, 다운로드, 제한 도메인 권한만 있음
M1584  L052889-L052904  [설치보류] content_scripts가 자동 주입되므로 content.js가 실제로 무엇을 하는지 봐야 최종 승인 가능
M1584  L052906-L052933  [다음검수항목] 페이지 열자마자 자동수집 여부, 외부 fetch, 내부 JSON 읽기, 다운로드 방식, storage/cookie/email/token 저장 여부 확인 필요

COORD_contentJS/내부JSONFetch:
M1585  L052936-L053040  [contentJS전반] safeName, timestamp, serviceName, conversationIdFromUrl, `fetchChatGptConversation()` 등 content.js 시작부 제시
M1585  L053011-L053032  [내부Endpoint] `/backend-api/conversation/${id}`와 limit 쿼리 endpoint를 `credentials: "include"`로 fetch해 ChatGPT 내부 JSON을 가져오는 구조
M1586  L053041-L053093  [민감부판정] cookie 추출/세션토큰 저장/HAR/외부전송은 아니지만, 로그인 세션을 이용한 내부 대화 JSON 읽기라 핵심 기능이자 민감부로 판정
M1586  L053097-L053104  [상대경로장점] fetch URL이 상대경로라 외부 사이트가 아니라 현재 ChatGPT 도메인 안에서 대화 JSON을 받아오는 구조로 보임
M1586  L053105-L053140  [남은검수] 호출 시점, data 저장/전송 경로, chrome.runtime.sendMessage, 외부 fetch 추가 여부, email/url/ids 포함 범위 확인 필요

COORD_대화정렬/첨부메타:
M1587  L053142-L053246  [정렬본문첨부] currentBranchNodes, chronologicalNodes, textFromPart, messageText, extensionOf, sizeText, attachmentFromObject 코드 제시
M1588  L053248-L053313  [정교함판정] ChatGPT 내부 JSON에서 대화 순서, 메시지 본문, 첨부파일 메타데이터를 사람이 읽을 형태로 정리하는 파트로 판정
M1588  L053263-L053279  [분기고려] currentBranchNodes는 현재 선택된 대화 가지, chronologicalNodes는 시간순 후보라 ChatGPT 재생성/분기 구조를 고려한 흔적
M1588  L053299-L053329  [첨부판정] 파일 원본/바이너리/HTML은 저장하지 않고 파일명, 확장자, MIME, 크기, fileId를 추출 / 외부공유용이면 fileId 제거 옵션 권고

COORD_정규화/개인보관정보:
M1589  L053365-L053461  [정규화부] collectAttachments, modelName, modeName, aiNameForMessage, normalizeChatGptMessage 코드 제시
M1590  L053463-L053487  [구조양호] 첨부파일 메타, 모델명/thinking 여부, ChatGPT node/message 정규화부로서 외부전송/쿠키접근/첨부파일 원본다운로드 없음
M1590  L053489-L053522  [IDs노란불] conversationId, nodeId, messageId, parentId, childrenIds, fileId는 개인 로컬 백업/피키 재주입용으론 강하지만 외부 공유용 제거 권고
M1590  L053531-L053559  [thoughts감지주의] `metadata.thoughts`를 modeName 감지 대상으로 문자열화하는 것은 굳이 필요 없으므로 reasoning_effort/status/model 정도만 보도록 축소 권고
M1590  L053561-L053617  [role필터대기] role이 user/assistant 외 system/tool/developer/unknown을 포함할 수 있으므로 다음 chunk에서 필터 확인 필요 / share-safe 옵션 제안

COORD_systemTool/DOMFallback미완:
M1591  L053623-L053716  [canonicalRaw] normalizeChatGptMessage 반복 후 `canonicalFromChatGptRaw`에서 role 필터가 `user`, `assistant`, `system`, `tool`까지 포함하는 코드 제시
M1592  L053765-L053905  [systemTool과다] AI Exporter 대체용이면 기본 export는 user/assistant만 남기고 system/tool은 debugMode에서만 저장해야 한다고 지적
M1592  L053819-L053851  [DOMMarkdown양호] nodeToMarkdown/messageMarkdown은 script/style/button/svg/aria-hidden 제거, pre/code, heading, list 보존 등 1차판으로 충분히 괜찮음
M1592  L053853-L053876  [DOM첨부추정] aria-label/title/img에서 파일명처럼 생긴 것을 첨부파일로 추정 / 파일 원본 접근은 없지만 UI tooltip 오인 가능성 있음
M1593  L053907-L054063  [fallback코드제시] `canonicalFromDomFallback`, `buildCanonical`, `stripMarkdown`, attachmentSummary, roleLabel, headerLine 코드가 제시되지만 피키 후속 검수 전 이 화가 종료

STATE_TAG:
M1583-M1584  manifest연두불 / 최소권한 / 설치보류 / content검수대기
M1585-M1586  내부JSONFetch / 로그인세션활용 / 상대경로 / 핵심민감부
M1587-M1588  branch정렬 / messageText / 첨부메타 / fileId공유주의
M1589-M1590  정규화부양호 / ids보존 / 개인백업강함 / share-safe필요
M1591-M1593  system-tool과다 / DOMfallback / stripMarkdown미검수 / 다음화연결

TOPIC_TAG:
manifest-json, Manifest-V3, activeTab, scripting, downloads, host-permissions, content-js, fetchChatGptConversation, credentials-include, backend-api-conversation, ChatGPT-mapping, currentBranchNodes, chronologicalNodes, attachment-metadata, conversationId, nodeId, messageId, fileId, share-safe, system-tool-debugMode, DOM-fallback, stripMarkdown

UPPER_INDEX_HINT:
- META_RAW_RECOVERY_INFRA: Tsuky-AI Exporter가 실제 Chrome Extension 형태로 구체화된다. AI Exporter 대체 기능이 manifest, content.js, 내부 JSON fetch, DOM fallback으로 분해된다.
- META_SAFETY_PROTOCOL: 권한 최소화, 설치 전 manifest/content/popup 검수, 내부 JSON fetch의 민감성, system/tool 기본 제외, share-safe 모드 필요성이 안전 프로토콜로 남는다.
- META_DATA_MODELING: conversation tree, branch, chronological order, ids, attachments, model/thinking metadata 보존은 재주입/복원용 데이터 모델의 중요한 재료다.
- META_SCOPE_CONTROL: 기본 목적은 “대화 export”이므로 system/tool/debug, 내부 ids, fileId 같은 분석용 정보는 기본 출력과 분리해야 한다.

UNRESOLVED:
- content.js 전체는 아직 끝까지 검수되지 않았다. 특히 다운로드 생성부, chrome.runtime/onMessage, popup 요청 처리, 외부 fetch 추가 여부가 남아 있다.
- `canonicalFromChatGptRaw`가 기본 export에 system/tool을 포함하는 문제는 수정 후보로 확인됐지만 아직 반영 여부 미정이다.
- `canonicalFromDomFallback`, `stripMarkdown`, headerLine은 코드만 제시됐고 피키 검수는 다음 화에서 이어져야 한다.

PICO_README:
제52화는 Tsuky-AI Exporter Chrome Extension의 manifest와 content.js 핵심부를 검수하는 회차다. 나중에 manifest 연두불, activeTab/scripting/downloads, 내부 JSON fetch, credentials include, ChatGPT conversation tree, 첨부 메타, ids/share-safe, system/tool debugMode, DOM fallback을 말하면 이 화를 찾아라. 핵심은 확장이 꽤 좋은 방향이지만, 내부 JSON 접근형이라 끝까지 코드검수 전 설치 승인 금지라는 점이다.

