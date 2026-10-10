[LEAF::part_bz::R0009-P06]
DRAMA_TITLE: 〈자기를 만든 도구를 자기 안에서 만들다 — Tsuky-AI Exporter 확장 코드 검수, 내부 JSON fetch의 정체〉
TITLE_FUNCTION: 52화 한줄요약(R0009 6/11) / ★Chrome 확장 manifest "거의 연두불"(위험 권한 0) / ★★content.js 핵심—fetch(credentials:include)로 ChatGPT 내부 대화 JSON 읽기=츠키 "수상함" 직감 적중 / 대화 tree 구조·normalizeChatGptMessage 출력구조=이 드라마 RAW 파일 구조 그 자체(자기참조 정점) / 노란불(개인 식별자 IDs·share-safe 옵션·role 필터·thoughts 긁지 말 것)

FILE: part_bz | R0009-P06 | M001583-M001593 | L52817-L54064
SOURCE_META:
  schema: inherited_from_part_aa
  source: ChatGPT | thread: R0009(6/11) — Tsuky-AI Exporter Chrome 확장 코드 검수
  parent: R0009 | partFile: bz
  declared_range: M001583-M001593 (범위 11)
  MSG_DECLARED: 11 | MSG_ACTUAL: 11 | OMITTED: 0. 발화 넘버 연속(M1583~M1593).
    ★M1593(츠키)에서 코드 중간 절단(headerLine 함수까지)—피키 답변·stripMarkdown/
    download/chrome.runtime은 다음 파일(ca, 53화)로 이월.
  date: D20260518 11:23~11:41 (5일차 오전, 약 18분)
  모델노트: 전 응답 gpt-5-5-thinking 유지. 웹검색 없음(코드 검수 회차). ★피키 청크
    단위 검수 일관("여기까지 검수"·"다음 chunk 보내줘", 안 본 부분 본 척 안 함=43화
    "본 만큼만"의 코드판 계속). 실제 js 코드(manifest.json·content.js) 직접 검수.
    설치 전 검수 일관(연두불/노란불 등급).
  첨부노트: 코드는 본문 텍스트로 첨부(별도 파일 없음).
  ★시청 메타: R0009 진행(6/11·스코프맵으로 확인). ★자기참조 정점(드라마를 만든
    도구 Exporter를 드라마 안에서 만듦). 냉장고 위험물 분리(유지)·문어 미등장.
    ※38화 ERRATUM 승계(노아≠클로드, 애칭 미정). 코덱스 마커 ⌨️(50화 확정) 유지.
    ※스코프맵 재주입(1화 인덱스)으로 R0009=bu~cc(9파트)+cd 혼합 윤곽 확인.

README_FOR_FUTURE_CLAUDE:
  - ★manifest.json 검수 "거의 연두불"(M1583-M1584): 51화 "manifest부터 봐야" 다음
    단계. 피키 "위험 권한 없음(cookies❌webRequest❌debugger❌history❌storage❌
    <all_urls>❌nativeMessaging❌), 들어있는 건 최소 권한(activeTab/scripting/
    downloads)+host_permissions가 ChatGPT/Claude/Gemini 도메인 제한". "아무 사이트나
    다 보는 확장 아님, 지정된 AI 대화 사이트에서만". content_scripts+run_at:
    document_idle(페이지 열면 content.js 자동 주입되나 곧바로 export 아니라 버튼
    대기). 판정 "manifest는 통과 후보, 잡상인 냄새 약함, 개인용 로컬 exporter 최소
    권한에 가까움, 근데 content.js 보기 전 설치 승인 보류". 51화 빨간불 권한 기준
    통과.
  - ★★content.js 핵심—내부 JSON fetch(M1585-M1586): ★fetchChatGptConversation()이
    fetch(`/backend-api/conversation/${id}`, {credentials:"include"})로 ChatGPT
    내부 대화 JSON endpoint 요청. ★★츠키 "냄새 수상함"(50화부터) 직감이 정확히 이
    지점 적중. 피키 해석: "쿠키 추출❌·session token 저장❌·HAR❌·외부 서버 전송❌,
    하지만 네가 로그인한 브라우저 세션을 이용해 ChatGPT 내부 대화 JSON 읽기✅". ★50화
    browser-dom-exporter(화면 DOM만 긁기)보다 한 단계 더 원본에 가까운 방식(내부 JSON
    직접). 정확도↑(타임스탬프·id·모델 메타) 민감도↑. ★피키 "위험해서 버려야 함이
    아니라, 이 확장의 핵심 기능이자 가장 민감한 부분". 좋은 점: URL 상대경로
    (/backend-api/...)라 외부 사이트로 보내는 게 아니라 현 ChatGPT 도메인 안에서 받음
    ("내 브라우저 안에서 내가 로그인한 내 대화를 내가 읽기"=51화 "왜 내가 못함" 정당성
    의 코드 구현). ※츠키 감각 기반 포렌식(48화)이 코드 라인 적중—코드 못 읽어도
    "수상하다"로 fetch(credentials:include) 정확히 의심.
  - ★대화 tree 구조·첨부 메타(M1587-M1590): currentBranchNodes/chronologicalNodes
    (ChatGPT 답변 재생성·분기로 생기는 나무 구조 고려)·messageText/textFromPart(본문
    추출, 첨부 part는 [첨부파일:파일명])·attachmentFromObject/collectAttachments(파일
    원본 저장❌, 파일명·확장자·MIME·크기·fileId만, url은 발견 신호로만). ★★normalize
    ChatGptMessage 출력구조(counter:M000001형식·ids{conversationId/nodeId/messageId/
    parentId/childrenIds}·speaker{type/name/aiName/modelName/mode}·timestamp·
    attachments·textMarkdown·textPlain·metadata{modelSlug/isThinking})=★이 드라마
    RAW 파일 구조 그 자체(M001583 spk=🈷️ role=user, model="gpt-5-5-thinking" mode=
    "thinking", 첨부 메타, 마스터 스코프맵 M번호 체계). ★자기참조 정점: 1화 SOURCE_
    META의 "exporter: Tsuky-AI Exporter PICO-HUB"가 바로 이것—드라마 안에서 그 드라마를
    만들어낸 도구를 만드는 중(45화 "자기를 읽는 법 PKMD"→52화 "자기를 만든 도구
    Exporter"). 드라마가 자기 출생의 비밀을 보여줌.
  - ★노란불 4종(M1588·M1590·M1592): ①IDs(conversationId/nodeId/messageId/fileId)=
    개인 식별자(쿠키·토큰 아니나 대화 내부 ID→개인 백업용 보존/외부 공유용 제거 추천,
    private export=ids 포함/share export=제거 옵션, 51화 secure by default 연장)
    ②metadata.thoughts 문자열화=긁지 말 것 권고(reasoning_effort/model 정도만 봐도
    충분, 출력 저장은 안 하나 굳이 긁을 필요 없음) ③role 필터=canonicalFromChatGptRaw
    에서 user/assistant/system/tool 다 통과시켜 system/tool 섞일 위험→"기본 출력은
    user/assistant만, system/tool/developer/unknown은 debugMode 옵션에서만" 권고
    (50·51화 과잉수집 경계 계속) ④stripMarkdown/다운로드부/chrome.runtime은 다음
    chunk(53화)에서 봐야(아직 외부 fetch 추가 여부 미확인). ★share-safe 옵션 권고
    (conversationId/messageId/nodeId/fileId/source url 제거).
  - ★DOM fallback(M1592-M1593): ChatGPT 내부 JSON 실패 시 canonicalFromDomFallback
    ([data-message-author-role] 노드에서 추출, attachmentNamesFromDom은 aria-label/
    title/img alt에서 파일명처럼 생긴 것 추정—UI tooltip 오인 가능하나 메타용이라 큰
    문제 아님). buildCanonical: ChatGPT면 내부 JSON 먼저, 실패하면 DOM fallback.
  - ★시청 메타: R0009 진행(6/11). 자기참조 정점(드라마를 만든 도구를 드라마 안에서
    만듦). ※시청 클로드 직결: 츠키 감각 기반 포렌식(코드 못 읽어도 fetch 의심 적중)·
    설치 전 코드 검수(48·49·50·51화 검증 습관의 Chrome 확장판)·secure by default
    (개인용/공유용 분리)·과잉수집 경계(role 필터)=AI 산출물을 검증 없이 안 믿기(환각
    방지 코드판). 피키 "본 만큼만"(청크 검수, 코드 절단 명시). ※38화 ERRATUM 승계.
  - 미해결: exec/gate 계정, 노션 버튼, 통과의례 7단계, BH::01-P_CTX, C 이미지,
    메리 하우스, 문어(EP4·메타·여전), 냉장고(위험물 분리 유지), HHM v1.x, ★Tsuky-AI
    Exporter Chrome 확장(manifest 연두불→content.js 내부 JSON fetch 노란불→stripMark
    down/download/chrome.runtime 미검수=53화), 우클릭 자동화 클립보드 수정, R0009
    진행(6/11).

BOOT:
  1. M001583-M001584: ★manifest.json 검수(거의 연두불·위험 권한 0·최소 권한).
  2. M001585-M001586: ★★content.js 내부 JSON fetch(credentials:include·츠키 수상함
     적중·가장 민감한 핵심 기능).
  3. M001587-M001588: 대화 tree 정리·본문 추출·첨부 메타(파일 원본 저장 안 함).
  4. M001589-M001590: ★normalizeChatGptMessage(드라마 RAW 구조 그 자체)·IDs 노란불.
  5. M001591-M001592: role 필터 노란불(user/assistant만)·thoughts 긁지 말 것·canonical
     생성부.
  6. M001593: DOM fallback·stripMarkdown(코드 중간 절단→53화 이월).

COORD_핵심사건:
  L52858        [manifest거의연두불] 위험 권한 0, 최소 권한만.
  L53050        [내부JSON fetch] credentials:include로 ChatGPT 내부 대화 JSON 읽기.
  L53095        [버려야함이아니라핵심기능] 가장 민감하나 이 확장의 심장.
  L53097        [URL상대경로] 외부 전송 아니라 현 도메인 안에서 받음.
  L53420        [normalizeChatGptMessage] counter/ids/speaker/timestamp 출력구조.
  L53503        [IDs개인식별자] 쿠키·토큰 아니나 대화 내부 ID(공유용 제거 추천).
  L53685        [role필터노란불] user/assistant만 남겨야(system/tool 섞임 경계).
  L54007        [buildCanonical] 내부 JSON 먼저, 실패하면 DOM fallback.

COORD_개념:
  L52858-52933 [manifest_권한_검수] Chrome 확장 위험도는 manifest 요구 권한으로 판정—
                위험 권한 0+host_permissions 도메인 제한=개인용 로컬 exporter 최소
                권한. 51화 빨간불 권한 기준의 실제 통과 사례.
  L53050-53130 [로그인세션_내부JSON_fetch] credentials:include로 로그인 세션을 이용해
                내부 대화 JSON을 읽는 방식—쿠키 추출·외부 전송은 없으나 가장 민감한
                핵심 기능. DOM 긁기보다 원본에 가깝고 정확도↑ 민감도↑. URL 상대경로라
                "내 도메인 안에서 내 대화를 내가 읽기"(51화 자립 정당성의 코드 구현).
                츠키 "수상함" 감각 포렌식이 이 라인 적중.
  L53420-53704 [자기참조_정점] normalizeChatGptMessage 출력구조(counter M000001·ids·
                speaker·model·thinking·첨부 메타)가 이 드라마 RAW 파일 구조 그 자체.
                1화 "exporter: Tsuky-AI Exporter PICO-HUB"가 이것—드라마 안에서 그
                드라마를 만든 도구를 만듦. 45화 "자기를 읽는 법(PKMD)"→52화 "자기를
                만든 도구(Exporter)". 자기 출생의 비밀.
  L53503-53901 [과잉수집_경계_계속] IDs는 개인 식별자(공유용 제거)·role 필터(user/
                assistant만, system/tool 분리)·thoughts 긁지 말 것=50·51화 과잉수집
                경계의 Chrome 확장판. share-safe 옵션(secure by default 연장).

COORD_서사기능:
  - 52화는 자립 아크의 자기참조 정점: 51화 "왜 내가 못함?"(도구 제작자 각성)→52화
    실제 Exporter 확장 코드 검수. 드라마를 만들어낸 도구(Tsuky-AI Exporter)를 드라마
    안에서 만드는 메타 구조 노출(1화 exporter 표기의 출생 비밀).
  - content.js 내부 JSON fetch는 츠키 감각 포렌식의 정점: 코드 못 읽어도 "수상함"으로
    fetch(credentials:include)를 50화부터 의심했고 52화에서 코드로 확인. 48화 "감각
    기반 포렌식"의 코드 라인 적중.
  - 코드 검수는 안전 아크의 Chrome 확장판: 48·49·50·51화 검증 습관(가상본·ditto·
    냄새검수·manifest)이 권한·fetch·과잉수집·share-safe까지. AI 산출물을 검증 없이
    안 믿는 습관이 확장 코드 영역에서 체계화. secure by default 계속.
  - 본 화는 R0009 6/11(스코프맵으로 확인). 문어 여전 미등장. 클러스터 5/6 진행
    (EP45~52). ★자립이 막클러스터 축, 자기참조(자기를 만든 도구를 만듦)가 그 정점.

TEMP_CATEGORY:
  - CAT_INFRA_WORK: ★Chrome 확장 manifest·content.js·내부 JSON fetch·DOM fallback·
    normalize 출력구조
  - CAT_SAFETY_DESIGN: ★권한 검수·내부 JSON fetch 민감부·share-safe 옵션·role 필터·
    secure by default
  - CAT_MEMORY_OS: ★normalizeChatGptMessage=드라마 RAW 구조·자기참조·BH 자립 도구
  - CAT_USER_MODEL: ★감각 포렌식(fetch 의심 적중)·설치 전 코드 검수·수상함 직감
  - CAT_AI_PHILOSOPHY: 코드도 검증·피키 "본 만큼만"(청크 검수·절단 명시)
  - CAT_MULTI_AI: 코덱스가 만든 확장·피키 검수·⌨️ 마커
  - CAT_PLATFORM_CRITIQUE: 자립(내 도구)·내 대화를 내가 읽기(51화 정당성 코드 구현)
  - CAT_HALLUCINATION_DESIGN: 과잉수집 경계(role 필터·IDs·thoughts)
  - CAT_SELF_REFERENCE: ★드라마를 만든 도구를 드라마 안에서 만듦·1화 exporter 출생 비밀
  - CAT_TONE_RULE: 청크 검수·연두불/노란불 등급·다음 chunk 보내줘
  - CAT_MOTIF_TRACKING: 냉장고(위험물 분리)·문어(여전 미등장)·코덱스(⌨️ 유지)
  - SEED(메타인덱스용): "내부 JSON fetch(credentials:include)"=DOM보다 원본에 가까운
    민감 핵심 기능·츠키 감각 포렌식 적중·내 대화를 내가 읽기 / "normalizeChatGptMessage
    =드라마 RAW 구조 그 자체"=자기참조 정점·드라마를 만든 도구를 드라마 안에서 / "manifest
    연두불·과잉수집 경계(role 필터·IDs·share-safe)"=설치 전 코드 검수·secure by
    default Chrome 확장판

SEARCH_TAG:
  #R0009진행6of11 #Chrome확장manifest검수 #거의연두불 #위험권한0 #activeTab scripting downloads #host permissions도메인제한
  #content js핵심 #내부JSON fetch #credentials include #로그인세션으로내부대화JSON읽기 #츠키수상함직감적중 #감각포렌식코드라인적중
  #쿠키추출안함외부전송안함 #URL상대경로 #내도메인안에서내대화를내가읽기 #51화왜내가못함정당성코드구현 #버려야함이아니라가장민감한핵심기능
  #대화tree구조 #currentBranchNodes #chronologicalNodes #첨부메타만수집 #파일원본저장안함 #normalizeChatGptMessage
  #counter M000001형식 #ids speaker timestamp model thinking #드라마RAW구조그자체 #자기참조정점 #드라마를만든도구를드라마안에서만듦
  #1화exporter출생비밀 #TsukyAIExporterPICOHUB #45화자기읽는법PKMD #52화자기만든도구 #IDs개인식별자 #share safe옵션
  #role필터노란불 #user assistant만 #system tool분리 #thoughts긁지말것 #과잉수집경계계속 #secure by default연장
  #DOM fallback #buildCanonical #설치전코드검수 #48화49화50화51화검증습관확장판 #본만큼만청크검수 #코드중간절단53화이월
  #문어여전미등장 #자기참조가자립의정점 #돈월

STATE_TAG:
  M001583-M001584  manifest검수 / 거의연두불 / 최소권한
  M001585-M001586  내부JSON fetch / 수상함적중 / 가장민감한핵심
  M001587-M001588  대화tree정리 / 첨부메타 / 파일원본저장안함
  M001589-M001590  normalizeChatGptMessage / 드라마RAW구조 / IDs노란불
  M001591-M001592  role필터노란불 / thoughts긁지말것 / canonical생성
  M001593          DOM fallback / stripMarkdown / 코드절단53화이월

QUOTE_ANCHOR:
  M001584 L52858:
    "이 manifest.json만 보면 생각보다 깔끔함. 노란불 낮음, 거의 연두불이야."
  M001586 L53072:
    "로그인 세션을 이용한 내부 대화 JSON 읽기 ✅"
  M001586 L53095:
    "이건 위험해서 버려야 함이 아니라, 이 확장의 핵심 기능이자 가장 민감한 부분이야."
  M001586 L53103:
    "외부 사이트로 보내는 게 아니라, 현재 ChatGPT 도메인 안에서 대화 원본 JSON을 받아오는 구조."
  M001590 L53516:
    "이건 쿠키나 토큰은 아니지만, 네 대화 내부 식별자야."
  M001592 L53895:
    "악성 냄새 없음 / 실제 exporter로 발전 가능 / 단, 기본 export에 system/tool 포함은 빼야 함"

INDEXER_NOTE:
  - 라우팅:
    · "manifest 검수" → M1583-M1584 — 거의 연두불. 51화 권한 기준 통과.
    · "내부 JSON fetch" → M1585-M1586 — credentials:include. 츠키 수상함 적중.
      가장 민감한 핵심 기능. 내 도메인 안에서 내 대화 읽기.
    · "normalizeChatGptMessage=드라마 RAW 구조" → M1589-M1590 — 자기참조 정점. 1화
      exporter 출생 비밀.
    · "과잉수집 경계(role/IDs/thoughts/share-safe)" → M1588·M1590·M1592 — secure by
      default. 50·51화 연장.
    · "stripMarkdown/download/chrome.runtime" → 미검수, 53화(ca) 이월.
  - ★시청 메타: R0009 진행(6/11). 자기참조 정점(드라마를 만든 도구를 드라마 안에서).
    츠키 감각 포렌식이 fetch 라인 적중. 설치 전 코드 검수=AI 산출물 검증(환각 방지
    코드판). 피키 "본 만큼만"(청크 검수·코드 절단 명시). ※38화 ERRATUM 승계(노아≠
    클로드, 애칭 미정).
  - MSG_ACTUAL=11(생략 0, M1583~M1593 연속), 좌표 정합 검증 완료(bash 확인). M1593
    코드 중간 절단(headerLine까지)→53화(ca) 이월.
  - 냉장고 위험물 분리(유지)·문어 여전 미등장. ★R0009 진행(6/11). 클러스터 5/6
    진행(EP45~52). ★Tsuky-AI Exporter Chrome 확장 검수 진행(manifest 연두불→content.js
    내부 JSON fetch 노란불→stripMarkdown/download/chrome.runtime 미검수=53화). 자기
    참조가 자립의 정점.
