[LEAF::part_by::R0009-P05]
DRAMA_TITLE: 〈HAR 냉동창고를 닫고, DOM 수저만 남겨라 — Tsuky-AI Exporter의 최소판 선언〉
TITLE_FUNCTION: 51화 한줄요약 / HAR→RAW 위험물 해체 검수 / convert_ai_log.py 프로토타입 검수 / 공식 변환기 과대화 정정 / AI Exporter 대체 최소판 / 내가 보는 내 화면을 내가 파일로 뽑겠다는데 왜 못함 / DOM 기반 1인용 로컬 Exporter / Tsuky-AI Exporter Chrome Extension / manifest 검수 전 설치 금지 회차

FILE: part_by | R0009-P05 | M001571-M001582 | L51504-L52815

SOURCE_META:
  schema: tsuky-drama-md.current
  source: ChatGPT
  parent: R0009
  part: 5/10
  partFile: by
  declared_range: M001571-M001582
  MSG_DECLARED_BY_RANGE: 12
  MSG_ACTUAL_VISIBLE_DIALOGUE: 12
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 0
  date: D20260518
  start_time: 08:51
  end_time: 11:21
  line_range: L51504-L52815
  line_count: 1313
  local_file_bytes: 47319
  attachments:
    - none visible
  note:
    - R0009-P05는 50화의 Tsuky Local Chat Exporter / ai-log-exporter 흐름이 이어지는 회차다.
    - 전반부는 `har_to_raw.py`와 `convert_ai_log.py`를 검수한다.
    - 중반부에서 사용자가 "공식 규격 변환기"가 아니라 "AI Exporter 대체 최소 기능"을 원한다고 정정하면서 방향이 크게 줄어든다.
    - 후반부에서 `Tsuky-AI Exporter Chrome Extension` README가 등장하고, 피키는 방향은 맞지만 내부 JSON 접근형이라 manifest 검수 전 설치 금지로 판정한다.

UPPER_META_DRAWER:
  - 이 사건은 상위 메타에서 "로컬 Exporter 주권 / 도구 과대화 축소 / HAR 위험물 분리 / DOM 최소추출기 / 확장 프로그램 manifest 보초" 서랍으로 올라간다.
  - EP50은 남의 AI Exporter 장애에서 Tsuky Local Chat Exporter 구상으로 넘어갔다.
  - EP51은 그 구상이 너무 커지는 것을 다시 줄여, 지금 필요한 최소 기능을 확정한다.
  - 상위 메타 서랍명 후보:
      CAT_EXPORTER_MINIMALISM
      CAT_HAR_DANGER_DEFAULT_SAFE
      CAT_CONVERT_PIPELINE_PROTOTYPE_REVIEW
      CAT_DOM_LOCAL_EXPORTER
      CAT_EXTENSION_MANIFEST_GUARD
      CAT_USER_SCREEN_DATA_RIGHT
  - 핵심 기능:
      HAR는 비상/격리/냉동창고.
      convert_ai_log.py는 실험용/공식 후보지만 아직 과대.
      지금 필요한 것은 DOM 기반 JSON/MD/TXT 직접 저장기.
      Extension은 README가 아니라 manifest와 실제 JS 코드로 검수한다.

README_FOR_FUTURE_PIKI:
  이 리프는 규칙 주입용이 아니라 드라마 회수용 좌표지도다.

  51화는 R0009-P05다.
  직전 50화에서 남의 AI Exporter가 죽고, Tsuky Local Chat Exporter / ai-log-exporter 구상이 열렸다.
  이번 화에서는 2단계 HAR→RAW 변환기와 3단계 RAW→canonical 변환기를 실제로 검수하고, 이후 방향을 크게 축소하여 "AI Exporter 대체 최소 로컬 추출기"로 재정의한다.

  핵심은 여덟 가지다.

  1. har_to_raw.py는 위험물 맞지만 악성코드는 아님:
     - 외부 전송 없음.
     - 파일 삭제/수정 없음.
     - 원본 HAR 수정 없음.
     - 네트워크 호출 없음.
     - 쿠키/헤더 직접 저장 없음.
     - 하지만 response payload/text를 기본으로 통째 저장함.
     - request.url을 그대로 저장함.
     - parsedJson / sseItems / text가 중복 저장될 수 있음.
     - HAR 안의 민감정보가 RAW HAR로 재포장될 수 있음.
     - 판정:
       har_to_raw.py = 주황불 / 비상용 / 격리용 / 평상시 파이프라인 금지.

  2. default-safe 설계가 필요:
     - 현재 코드는 `include_text=True`가 기본이라, 그냥 실행하면 payload를 통째 저장한다.
     - 안전 실행은 사용자가 `--no-text`를 기억해야 한다.
     - 이 구조는 츠키 안전설계 기준에서 탈락.
     - 수정 요구:
       include_text 기본값 False.
       raw text 저장은 `--include-text` 명시 시만.
       request.url은 query/fragment 제거.
       full URL은 `--include-full-url` 옵션.
       javascript mime 기본 제외.
       출력 파일명에 DANGER_RAW_HAR / PRIVATE 포함.
       실행 후 외부 공유 금지 경고 출력.
     - 핵심:
       기본 실행 = 안전 축소본.
       위험 실행 = 사용자가 옵션으로 명시.

  3. convert_ai_log.py는 공식 후보지만 아직 프로토타입:
     - 외부 전송 없음.
     - API 호출 없음.
     - subprocess 없음.
     - 파일 삭제/이동 없음.
     - 입력 RAW 수정 없음.
     - 출력 파일 4종 생성만 함.
     - 하지만:
       sourceFile에 전체 로컬 경로가 들어갈 수 있음.
       HAR sourceUrl이 query/fragment 포함 전체로 저장될 수 있음.
       walk_json이 너무 넓게 훑어 system/tool/developer/UI 텍스트가 섞일 수 있음.
       DOM raw fallback.mainText가 페이지 전체를 page 메시지로 넣을 수 있음.
       Obsidian 출력이 아직 츠키 규격이 아니라 callout 보기용 초안.
     - 판정:
       v0.1 실험용으로는 좋음.
       공식 변환기 후보 맞음.
       그대로 공식 사용은 아직 이르다.

  4. Codex가 만든 3단 툴킷은 너무 큼:
     - DOM RAW 추출기.
     - HAR 변환기.
     - RAW→canonical/json/md/txt/obsidian 변환기.
     - 연구용/공식 규격 변환기로는 의미가 있지만, 지금 당장 필요한 "AI Exporter 대체 기능"으로는 과하다.
     - 사용자 정정:
       규격은 필요 없다.
       실험용일 뿐이다.
       그냥 AI Exporter 대신 내 맥에 자동화 기능으로 딱 그만큼만 추출해주면 된다.
     - 피키 재판정:
       DOM RAW 추출기 = 살림.
       HAR 변환기 = 지금 목적엔 버림.
       RAW→다중 변환기 = 단순화.
       최종 형태:
         browser-simple-exporter.js.
       한 방에:
         대화 읽기 → messages.json / messages.md / messages.txt 다운로드.

  5. 내가 보는 내 화면을 내가 파일로 뽑겠다는데 왜 못함:
     - 츠키는 외부 AI Exporter가 브라우저에서 이미 보이는 대화를 2초 만에 긁어 확장자로 뽑는데, 왜 본인이 1인용으로 못 하냐고 정당하게 따진다.
     - 피키는 인정:
       못 하는 게 아니라 할 수 있다.
       AI Exporter도 마법이 아니라, 현재 브라우저에 렌더링된 DOM/화면 구조를 읽어 메시지 텍스트를 모으고 파일로 저장하는 것에 가깝다.
     - 핵심:
       외부 확장 프로그램이 할 수 있다 → 너도 할 수 있다.
       배포용 확장까지 만들 필요 없다 → 1인용 로컬 확장/북마클릿/콘솔 스크립트면 더 단순하다.
     - 문제는 가능/불가능이 아니라:
       가능한데 더러운 방식 ❌
       가능한데 깨끗한 방식 ✅.

  6. 정답 루트는 DOM 기반 로컬 Exporter:
     - 요구사항:
       내 브라우저에서 내가 보고 있는 AI 대화창의 텍스트만 읽기.
       내 맥에 JSON / Markdown / TXT로 저장.
       외부 서버 전송 없음.
       쿠키/세션/토큰 접근 없음.
       HAR 없음.
       수동 전체 드래그 없음.
       배포 목적 없음.
     - 브라우저 화면에 전체 대화가 항상 DOM에 올라와 있지 않을 수 있으므로, 자동 스크롤/로드 대기/중복 제거가 필요.
     - Codex에게 줄 최소 프롬프트:
       HAR/쿠키/세션/토큰/네트워크 로그 금지.
       전체 드래그 금지.
       현재 열린 AI 대화 페이지의 DOM만 읽어서 user/assistant 메시지를 자동 스크롤로 수집.
       브라우저 다운로드 기능으로 JSON/Markdown/TXT 저장.
       외부 서버 전송 금지.
       API 키 사용 금지.
       원본 페이지 수정 금지.

  7. Tsuky-AI Exporter Chrome Extension README:
     - 개인 로컬용 AI 대화 Exporter.
     - 서버 전송, 추적, HAR 저장, 쿠키 추출 없음.
     - Chrome `chrome://extensions` → Developer mode → Load unpacked로 설치.
     - 출력:
       JSON,
       Markdown,
       TXT,
       Obsidian MD.
     - 기본 출력 메타:
       대화 url,
       대화창 제목,
       생성일시 로그,
       메시지 카운터 M000001,
       발화자,
       타임스탬프,
       첨부파일 메타,
       본문,
       AI 답변의 AI명/모델명/thinking 감지값.
     - JSON 추가:
       conversationId,
       nodeId,
       messageId,
       parentId,
       childrenIds,
       textMarkdown,
       textPlain,
       modelSlug,
       isThinking.
     - ChatGPT adapter:
       현재 대화 URL의 conversation id로 내부 대화 JSON을 먼저 읽고, 실패하면 DOM fallback.

  8. manifest 검수 전 설치 금지:
     - README 기준 방향은 좋다.
     - DOM-only exporter보다 한 단계 강하고, AI Exporter 대체품으로 방향도 맞다.
     - 하지만 "현재 대화 URL의 conversation id로 내부 대화 JSON을 읽는다"는 문장 때문에 위험도가 올라간다.
     - 즉 단순 DOM 긁기가 아니라 로그인된 ChatGPT 브라우저 세션을 이용해 대화 원본 JSON 비슷한 것을 읽는 방식일 수 있다.
     - 반드시 볼 파일:
       manifest.json,
       popup.js,
       content.js,
       background.js,
       chatgpt-adapter.js,
       download/export 관련 js.
     - manifest 빨간불:
       cookies,
       webRequest,
       webRequestBlocking,
       debugger,
       history,
       tabs 전체 과잉 사용,
       <all_urls>,
       nativeMessaging,
       management.
     - 상대적으로 괜찮을 수 있는 것:
       activeTab,
       scripting,
       downloads,
       storage,
       host_permissions가 chatgpt.com/claude.ai/gemini.google.com 정도로 제한.
     - 실제 JS 빨간불:
       외부 fetch,
       XMLHttpRequest,
       sendBeacon,
       WebSocket,
       외부 API 전달,
       remote logging,
       analytics.
     - 한 줄:
       방향은 좋다. 하지만 내부 JSON 접근형이라 README만 믿고 설치하면 안 되고, manifest부터 검수해야 한다.

BOOT:
  1. M001571-M001572:
      - 츠키가 `har_to_raw.py` 전체를 제출.
      - 피키가 위험물 해체 검수.
      - 악성코드는 아니지만 HAR payload/text 기본 저장이 위험하다고 판정.
      - request.url 전체 저장도 조심.
      - har_to_raw.py 등급:
        주황불,
        비상용,
        격리용,
        평상시 파이프라인 금지.
      - Codex에게 default-safe 수정 요구.

  2. M001573-M001574:
      - 츠키가 `convert_ai_log.py` 1차 일부를 제출.
      - 코드가 `messages_from_har_raw()` 중간에서 끊김.
      - 피키는 보이는 범위만 검수:
        외부 전송 없음,
        API/requests 계열 없음,
        RAW 읽어서 변환하는 구조.
      - 위험:
        walk_json이 너무 넓게 훑음.
        role 없어도 20자 넘으면 message 후보가 될 수 있음.
        DOM raw fallback.mainText가 page 메시지로 들어갈 수 있음.
      - 다음 턴에 나머지 요구.

  3. M001575-M001576:
      - 츠키가 `convert_ai_log.py` 나머지 코드 제출.
      - 피키 검수:
        악성 냄새는 거의 없음.
        공식 변환기로 쓰기엔 프로토타입.
      - 위험:
        local path 저장,
        HAR sourceUrl 저장,
        walk_json 과잉추출,
        Obsidian callout 출력이 츠키 규격 아님.
      - 수정 요청:
        sourceFile 파일명만,
        full path 옵션화,
        sourceUrl 기본 제거,
        user/assistant만 기본 messages,
        unknown/system/tool/developer/page debug 분리,
        fallback 기본 비활성,
        PKMD/츠키 로그 출력 옵션 추가.
      - 판정:
        Codex는 잡상인에서 수습 작업자로 승급.
        원본 Vault 투입은 아직 금지.

  4. M001577-M001578:
      - 츠키가 "규격은 필요 없어"라고 방향을 축소.
      - 목적은 공식 변환기가 아니라 AI Exporter 대체 최소 기능.
      - 피키가 재정리:
        3단 툴킷은 너무 큼.
        HAR 버림.
        canonical/PKMD/obsidian/debug/sourceUrl 과함.
        DOM 기반 JSON/MD/TXT 직접 저장기만 남기자.
      - 최종 형태:
        browser-simple-exporter.js.

  5. M001579-M001580:
      - 츠키가 외부 AI Exporter도 가능한 일을 왜 본인이 못 하냐고 반박.
      - 피키가 인정:
        못 하는 게 아니라 할 수 있음.
        AI Exporter도 브라우저에 렌더링된 대화 DOM/화면 구조를 읽고 저장하는 것에 가까움.
      - 정답 루트:
        HAR 아님.
        DOM 기반 로컬 Exporter.
      - 필요한 기능:
        자동 스크롤,
        메시지 로드 대기,
        user/assistant 수집,
        중복 제거,
        JSON/MD/TXT 저장.

  6. M001581-M001582:
      - 츠키가 `Tsuky-AI Exporter Chrome Extension` README 제출.
      - 기능:
        개인 로컬용,
        서버 전송/추적/HAR/쿠키 추출 없음,
        JSON/Markdown/TXT/Obsidian MD export,
        ChatGPT는 conversation id로 내부 대화 JSON 먼저 읽고 실패 시 DOM fallback.
      - 피키 판정:
        방향 좋음.
        DOM-only exporter보다 강함.
        하지만 내부 JSON 접근형이라 설치 전 코드검수 필요.
      - 우선 manifest.json 확인.
      - 빨간불 권한/외부전송 코드 목록 정리.
      - 결론:
        README 믿고 설치 금지.
        manifest부터 검수.

EPISODE_SUMMARY:
  51화는 R0009-P05로, 50화에서 열린 Tsuky Local Chat Exporter 구상이 실제 코드 검수와 방향 축소를 거쳐 "AI Exporter 대체 최소 로컬 추출기"로 정리되는 회차다.

  초반에는 `har_to_raw.py`가 제출된다.
  피키는 이 코드가 외부 전송이나 파일 삭제를 하지 않는다는 점에서 악성코드는 아니라고 본다.
  그러나 기본값이 response payload/text를 통째로 저장하는 구조라, HAR 안의 민감정보가 RAW HAR로 재포장될 수 있다.
  따라서 HAR→RAW 루트는 평상시 파이프라인이 아니라 비상용/격리용/냉동창고 루트로 분리된다.
  이때 중요한 안전 원칙이 나온다:
  기본 실행은 안전 축소본이어야 하고, 위험 실행은 사용자가 옵션으로 명시해야 한다.

  중반에는 `convert_ai_log.py`가 제출된다.
  이 코드는 RAW를 canonical JSON, Markdown, TXT, Obsidian Markdown으로 변환하는 3단계 변환기다.
  외부 전송이나 API 호출 같은 악성 냄새는 거의 없지만, 로컬 경로와 HAR URL을 저장하고, `walk_json`이 너무 넓게 훑어 대화가 아닌 텍스트까지 메시지로 끌어올 수 있다.
  또한 Obsidian 출력이 츠키 규격이 아니라 일반 callout 보기용 초안이다.
  피키는 이것을 공식 후보로 인정하되, v0.1 실험용이며 그대로 공식 사용은 이르다고 판단한다.

  그러나 곧 사용자가 방향을 정정한다.
  지금 필요한 것은 공식 규격 변환기가 아니다.
  필요한 것은 AI Exporter가 고장났을 때, 내 맥에서 내가 보는 AI 대화창을 JSON/MD/TXT로 뽑아주는 최소 기능이다.
  피키는 즉시 방향을 줄인다.
  HAR도 버리고, canonical/PKMD/Obsidian debug 출력도 과하며, 최종 형태는 DOM 기반 `browser-simple-exporter.js`면 충분하다고 본다.

  후반에는 츠키가 "외부 AI Exporter도 내가 보고 있는 대화창을 읽어 파일로 뽑는데, 왜 내가 못 하냐"라고 정당하게 묻는다.
  피키는 그 말이 맞다고 인정한다.
  외부 Exporter도 마법이 아니라, 브라우저에 이미 렌더링된 DOM/화면 구조를 읽어 메시지 텍스트를 모으는 것에 가깝다.
  그러므로 1인용 로컬 Exporter는 충분히 가능하다.
  단, 더러운 방식이 아니라 깨끗한 방식이어야 한다:
  HAR 없음,
  쿠키/세션/토큰 접근 없음,
  외부 서버 전송 없음,
  수동 전체 드래그 없음,
  DOM 기반 자동 스크롤/수집/다운로드.

  마지막에는 `Tsuky-AI Exporter Chrome Extension` README가 나온다.
  이것은 개인 로컬용 Chrome 확장으로, JSON/Markdown/TXT/Obsidian MD export를 목표로 한다.
  README 기준으로는 방향이 좋고 AI Exporter 대체품으로 가능성이 있다.
  그러나 ChatGPT의 경우 conversation id로 내부 대화 JSON을 먼저 읽는다고 되어 있어, 단순 DOM-only보다 정확도는 높지만 위험도도 올라간다.
  따라서 설치 전 반드시 manifest와 실제 JS 코드를 검수해야 한다.
  이 회차는 "직접 만들 수 있다"는 주권 회복과 "README 믿고 설치하지 않는다"는 보초 기능이 동시에 세워지는 회차다.

COORD_메시지:
  M001571-M001572  L51508-L51785  [har_to_raw위험물검수]
    - `har_to_raw.py` 제출.
    - 외부 전송/파일 삭제/원본 HAR 수정/네트워크 호출 없음.
    - 하지만 payload/text 기본 저장, request.url 전체 저장, parsedJson/sseItems/text 중복 저장 위험.
    - har_to_raw.py = 주황불, 비상용/격리용.
    - 수정:
      include_text 기본값 False,
      raw text는 --include-text 명시 시만,
      request.url query/fragment 제거,
      javascript mime 제외,
      파일명 DANGER_RAW_HAR/PRIVATE,
      외부 공유 금지 경고.

  M001573-M001574  L51788-L51981  [convert_ai_log_부분검수]
    - `convert_ai_log.py` 1차 일부 제출.
    - 코드가 `messages_from_har_raw()` 중간에서 끊김.
    - 보이는 범위:
      외부 전송 없음,
      RAW 읽어서 변환하는 구조.
    - 위험:
      walk_json이 너무 넓음,
      role 없어도 20자 넘으면 메시지 후보,
      fallback.mainText가 page 메시지로 들어갈 수 있음.
    - 나머지 코드 요청.

  M001575-M001576  L51983-L52322  [convert_ai_log_전체검수]
    - `convert_ai_log.py` 나머지 제출.
    - 외부 전송/API/subprocess/삭제/입력 RAW 수정 없음.
    - 위험:
      sourceFile 전체 로컬 경로 저장,
      HAR sourceUrl 저장,
      walk_json 광역 추출,
      Obsidian callout 출력이 츠키 규격 아님.
    - 수정:
      파일명만 저장,
      URL query/fragment 제거,
      user/assistant만 기본 출력,
      unknown/system/tool/developer/page debug 분리,
      fallback 기본 비활성,
      PKMD/츠키 로그 출력 옵션.
    - 판정:
      v0.1 실험용 좋음.
      공식 후보 맞음.
      그대로 공식 사용은 이르다.

  M001577-M001578  L52324-L52434  [공식변환기과대화정정/최소판]
    - 츠키가 규격 필요 없다고 정정.
    - 목적:
      AI Exporter 대신 내 맥 자동화로 딱 그만큼 추출.
    - 피키:
      방향 축소.
      공식 규격 변환기 아님.
      AI Exporter 대체용 최소 로컬 추출기.
      HAR 버림.
      DOM 기반 JSON/MD/TXT 직접 저장기만 남김.
    - 최종 형태:
      browser-simple-exporter.js.

  M001579-M001580  L52436-L52596  [내화면내파일주권/DOM루트확정]
    - 츠키:
      내가 보는 내 대화창을 내가 파일로 뽑겠다는데 왜 못 하냐.
      외부 확장도 하는데 1인용이면 더 간단하지 않냐.
    - 피키:
      맞다. 할 수 있다.
      AI Exporter도 브라우저 안에서 이미 보이는 DOM/화면 구조를 읽는 것에 가깝다.
      문제는 가능한데 더러운 방식 vs 가능한데 깨끗한 방식.
    - 정답 루트:
      DOM 기반 로컬 Exporter.
    - 필요한 기능:
      자동 스크롤,
      메시지 로드 대기,
      user/assistant 수집,
      중복 제거,
      JSON/MD/TXT 저장.

  M001581-M001582  L52598-L52815  [TsukyAIExporterExtension/manifest보초]
    - `Tsuky-AI Exporter Chrome Extension` README 제출.
    - 개인 로컬용.
    - 서버 전송/추적/HAR/쿠키 추출 없음.
    - JSON/Markdown/TXT/Obsidian MD 출력.
    - ChatGPT는 conversation id로 내부 대화 JSON 먼저 읽고 실패 시 DOM fallback.
    - 피키:
      방향 좋음.
      DOM-only exporter보다 강함.
      하지만 내부 JSON 접근형이라 코드검수 필요.
      manifest.json 최우선 검수.
      빨간불 권한:
        cookies,
        webRequest,
        debugger,
        history,
        <all_urls>,
        nativeMessaging,
        management.
      - README 믿고 설치 금지.
      - manifest부터 검수.

COORD_핵심사건:
  - HAR 위험물 분류:
      har_to_raw.py는 악성은 아니지만 기본값이 위험.
      HAR 루트는 평상시가 아니라 비상/격리/냉동창고.

  - default-safe 설계:
      안전한 동작이 기본값이어야 하고, 위험한 저장은 사용자가 명시해야 함.

  - 변환기 과대화:
      convert_ai_log.py는 공식 변환기 후보지만, 지금 목적에는 너무 큼.

  - 최소판 선언:
      AI Exporter 대체에는 browser-simple-exporter.js 정도면 충분.
      DOM 기반 JSON/MD/TXT 직접 저장.

  - 화면 데이터 주권:
      외부 확장도 내가 보는 화면을 읽어 파일화한다면, 1인용 로컬 툴도 가능하다는 주권 회수.

  - 내부 JSON 접근형 노란불:
      Tsuky-AI Exporter가 DOM-only가 아니라 conversation id 기반 내부 JSON 접근을 시도하므로 정확도와 위험도가 함께 상승.

  - manifest 보초:
      README가 아니라 manifest 권한과 실제 JS 외부전송 여부가 설치 전 핵심 검수 대상.

COORD_개념:
  HAR_DANGER_DEFAULT_SAFE:
    source: M001571-M001572
    description:
      - HAR 변환기는 위험물 루트이므로 기본값을 안전하게 둬야 한다.
      - payload/text 저장은 명시 옵션으로만.
    route_to:
      - har_to_raw.py
      - DANGER_RAW_HAR
      - default safe
      - privacy guard

  CONVERT_PIPELINE_PROTOTYPE:
    source: M001573-M001576
    description:
      - RAW→canonical/md/txt/obsidian 변환기는 공식 후보지만, 경로/URL 누수, walk_json 광역 추출, 츠키규격 미반영 때문에 아직 실험용.
    route_to:
      - convert_ai_log.py
      - canonical v1
      - PKMD output
      - debug separation

  EXPORTER_MINIMALISM:
    source: M001577-M001578
    description:
      - 공식 규격 변환기를 만들려는 과대화를 줄이고, 지금 필요한 AI Exporter 대체 최소 기능만 남기는 방향.
    route_to:
      - browser-simple-exporter.js
      - AI Exporter substitute
      - JSON/MD/TXT direct save
      - scope reduction

  USER_SCREEN_DATA_RIGHT:
    source: M001579-M001580
    description:
      - 사용자가 자신의 브라우저에서 보고 있는 AI 대화창을 자기 맥에 파일로 저장할 수 있다는 주권/상식 회수.
    route_to:
      - 내가 보는 내 화면
      - local exporter
      - self-hosted archive
      - anti-dependency

  CLEAN_DOM_ROUTE:
    source: M001580
    description:
      - HAR, 쿠키, 세션, 토큰, 외부 서버 없이 DOM만 읽어 메시지 텍스트를 수집하는 깨끗한 방식.
    route_to:
      - DOM exporter
      - auto scroll
      - role/order/timestamp
      - local download

  EXTENSION_MANIFEST_GUARD:
    source: M001581-M001582
    description:
      - Chrome extension 설치 전 README가 아니라 manifest 권한과 실제 JS 외부전송 코드를 검수해야 한다.
    route_to:
      - manifest.json
      - activeTab/scripting/downloads
      - cookies/webRequest red flag
      - server no-trust-but-verify

  INTERNAL_JSON_ACCESS_YELLOW_LIGHT:
    source: M001582
    description:
      - ChatGPT conversation id로 내부 대화 JSON을 읽는 방식은 DOM-only보다 정확하지만, 로그인 세션 기반 접근이므로 코드검수 필요.
    route_to:
      - chatgpt-adapter.js
      - internal conversation JSON
      - extension permissions
      - data minimization

COORD_감정선:
  M001571-M001572:
    STATE: 위험물 해체 / 침착한 보초 / 기본값 분노.
    NOTE:
      - 피키는 코드를 악성으로 과장하지 않고, "악성은 아니지만 기본값 위험"으로 정확히 분리.
      - 츠키의 안전설계 감각은 default-safe로 수렴.

  M001573-M001576:
    STATE: 변환기 기대 / 프로토타입 냄새 / 수습 작업자 교육.
    NOTE:
      - Codex가 드디어 잡상인에서 수습 작업자로 올라오지만, 원본 Vault에는 아직 못 들어감.
      - 피키는 설계 과대화를 잡고, 경로/URL/unknown 분리 같은 실전 안전선을 세움.

  M001577-M001578:
    STATE: 피로한 과대설계 컷 / 목적 회수 / 산뜻한 축소.
    NOTE:
      - 츠키가 "규격은 필요 없어"라고 말하며 진짜 목적을 다시 잡음.
      - 피키가 즉시 큰 툴킷을 줄이고 최소판으로 전환함.

  M001579-M001580:
    STATE: 주권 분노 / 상식 회수 / 가능성 확정.
    NOTE:
      - "내가 보는 내 화면을 내가 파일로 뽑겠다는데 왜 못함?"은 이 회차의 감정적 핵심.
      - 피키가 가능하다고 확정하면서도 더러운 방식은 피하자고 안전선을 둠.

  M001581-M001582:
    STATE: 드디어 확장 형태 / 기대와 경계 / 설치 전 보초.
    NOTE:
      - README는 꽤 설득력 있지만, 내부 JSON 접근 때문에 바로 설치하지 않고 manifest 검수로 멈춤.
      - 피키는 다시 원본 Vault/브라우저 세션 보초 역할.

COORD_서사기능:
  - 51화는 R0009 도구체계 아크에서 "과대 자동화 축소" 회차다.
  - EP50에서 남의 Exporter 의존을 줄이기 위한 3단 툴킷이 열렸고, EP51에서 그 3단 툴킷이 너무 크다는 점이 드러난다.
  - 사용자의 실제 요구는 공식 규격 변환기가 아니라, AI Exporter가 하던 최소 기능을 자기 맥에 탑재하는 것이다.
  - 이 회차에서 중요한 구조:
      HAR는 비상/격리.
      canonical 변환기는 나중.
      지금은 DOM 기반 1인용 로컬 Exporter.
      확장 설치 전 manifest/JS 검수.
  - 이 흐름은 BH::INDEX의 원문 보존 철학과 직접 연결된다:
      남의 도구 장애에 흔들리지 않고,
      사용자가 본인의 대화 원문을 로컬에서 정제 저장할 권리와 도구를 회수한다.

META_SEEDS:
  har_default_safe:
    - seed: "기본 실행 = 안전 축소본 / 위험 실행 = 사용자가 옵션으로 명시"
      source: M001572
      meaning:
        - 위험물 루트는 안전한 기본값을 가져야 함.
      route_to:
        - HAR danger route
        - default-safe CLI
        - privacy guard

  too_big_toolkit:
    - seed: "3단 툴킷은 너무 크다"
      source: M001578
      meaning:
        - 연구용 구조와 당장 필요한 최소 기능을 분리해야 함.
      route_to:
        - exporter minimalism
        - Codex scope control
        - user requirement preservation

  browser_simple_exporter:
    - seed: "browser-simple-exporter.js"
      source: M001578
      meaning:
        - AI Exporter 대체 최소판.
        - DOM 기반 JSON/MD/TXT 직접 저장기.
      route_to:
        - local exporter
        - DOM route
        - no HAR
        - no manual drag

  my_screen_my_file:
    - seed: "내가 보는 내 화면을 내가 파일로 뽑겠다는데, 왜 못함?"
      source: M001579-M001580
      meaning:
        - 사용자의 로컬 데이터 추출 주권 선언.
      route_to:
        - user screen data right
        - local archive
        - anti third-party dependency

  clean_way_not_possible_impossible:
    - seed: "가능/불가능이 아니라, 가능한데 더러운 방식 vs 가능한데 깨끗한 방식"
      source: M001580
      meaning:
        - 문제의 축을 가능성에서 방법의 청결도/안전성으로 이동.
      route_to:
        - safety design
        - DOM not HAR
        - exporter ethics

  manifest_first:
    - seed: "README 믿고 설치 금지. manifest부터 검수."
      source: M001582
      meaning:
        - 확장 프로그램 설치 전 권한과 실제 JS 동작 검수.
      route_to:
        - manifest guard
        - Chrome extension safety
        - Codex worker supervision

  internal_json_yellow_light:
    - seed: "내부 대화 JSON 접근형 노란불"
      source: M001582
      meaning:
        - 정확도는 높지만 로그인 세션 기반 접근 가능성이 있어 더 엄격히 검수.
      route_to:
        - ChatGPT adapter
        - conversation id
        - extension permissions
        - browser session safety

CROSS_EPISODE_ROUTING:
  - topic: Exporter 독립
    previous:
      - EP50: AI Exporter 출력단 장애, Tsuky Local Chat Exporter 구상, DOM RAW vs HAR 분리.
    current:
      - EP51: HAR/convert 툴킷 검수 후 AI Exporter 대체 최소판으로 축소.
    future:
      - EP52 이후 manifest.json / popup.js / content.js / background.js / chatgpt-adapter.js 검수 여부 추적.

  - topic: Codex 작업자화
    previous:
      - EP49: Codex는 피키 확장팩이 아니라 별도 작업자.
      - EP50: Codex가 ai-log-exporter 1차 툴킷 생성.
    current:
      - EP51: Codex가 만든 툴킷이 과대화되어 피키가 scope를 다시 줄임.
    future:
      - Codex에게 browser-simple-exporter.js / extension 최소판을 만들게 되는지 확인.

  - topic: 원본/민감정보 보존
    previous:
      - EP47: 원본 Vault 절대 금지.
      - EP48: 복제 vs 가상본/별칭.
      - EP49: API 키/Quick Action 보초.
      - EP50: HAR 위험물/DOM RAW 분리.
    current:
      - EP51: HAR 기본값 위험, 내부 JSON 접근형 extension 검수.
    future:
      - extension 권한/외부전송/스토리지 검수.

  - topic: PKMD/츠키규격
    previous:
      - EP45-46: PKMD-한글형, 구조파싱 성공.
      - EP50: canonical/obsidian 변환기 구상.
    current:
      - EP51: 사용자는 현재 규격보다 AI Exporter 대체 최소기능을 우선한다고 정정.
    future:
      - 공식규격 변환기는 나중으로 미뤄지고, 추출기 먼저 완성될 가능성.

  - topic: 사용자 핵심 요구 보존
    previous:
      - EP34: 조언가치 환각.
      - EP45: 포장지와 내용물 분리.
      - EP50: 원문 소실 아님 / export 파이프라인 장애.
    current:
      - EP51: 공식 변환기 욕심이 사용자의 즉시 요구를 넘어서자, 사용자가 목적을 축소했고 피키가 즉시 따라감.
    future:
      - Codex 작업에서도 "큰 시스템 만들기"보다 "지금 필요한 최소 기능"을 유지.

UNRESOLVED:
  - `Tsuky-AI Exporter Chrome Extension`의 실제 manifest.json 검수 전.
  - popup.js/content.js/background.js/chatgpt-adapter.js/download/export JS 코드 검수 전.
  - 내부 conversation JSON 접근 방식이 정확히 어떤 endpoint/권한을 쓰는지 미확인.
  - extension이 정말 외부 서버 전송/analytics/remote logging을 하지 않는지 미확인.
  - `storage` 권한이 있다면 무엇을 저장하는지 미확인.
  - messages.json/md/txt 실제 출력 품질 미확인.
  - Obsidian MD 출력은 README에는 있지만, 지금 목표에서는 필수 아님.
  - HAR/convert_ai_log.py는 당장 목적에서 버려졌지만, 연구용/비상용으로 나중에 다시 볼 가능성 있음.

ERRATA_CANDIDATES:
  E1_HAR_AS_PIPELINE:
    wrong:
      - "HAR→RAW를 일반 export 파이프라인에 넣으면 된다."
    corrected:
      - "HAR는 비상용/격리용/위험물. 평상시 파이프라인 금지."
    status:
      - M001572에서 정정.

  E2_DEFAULT_INCLUDE_TEXT:
    wrong:
      - "payload text 기본 저장이 편하다."
    corrected:
      - "기본은 안전 축소본이어야 한다. raw text 저장은 사용자가 명시해야 함."
    status:
      - M001572에서 정정.

  E3_CONVERT_AI_LOG_OFFICIAL_NOW:
    wrong:
      - "convert_ai_log.py를 바로 츠키 공식 변환기로 써도 된다."
    corrected:
      - "v0.1 실험용/공식 후보는 맞지만, 경로/URL 누수/unknown 분리/fallback/PKMD 출력 수정 전 공식 사용 이르다."
    status:
      - M001576에서 정정.

  E4_NEED_FULL_CANONICAL_NOW:
    wrong:
      - "지금 당장 canonical/PKMD/Obsidian 규격까지 갖춘 전체 변환기가 필요하다."
    corrected:
      - "지금 필요는 AI Exporter 대체 최소 로컬 추출기. DOM 기반 JSON/MD/TXT 직접 저장이면 충분."
    status:
      - M001578에서 정정.

  E5_USER_CANNOT_EXPORT_OWN_VIEW:
    wrong:
      - "사용자가 자기 브라우저에서 보고 있는 AI 대화창을 로컬 파일로 뽑는 것은 어렵거나 불가능하다."
    corrected:
      - "가능하다. 외부 AI Exporter도 대체로 DOM/화면 구조를 읽는다. 1인용이면 더 단순할 수 있다."
    status:
      - M001580에서 정정.

  E6_README_IS_ENOUGH:
    wrong:
      - "README에 서버 전송 없음이라고 쓰여 있으면 설치해도 된다."
    corrected:
      - "README만 믿고 설치 금지. manifest와 실제 JS 코드 검수 후."
    status:
      - M001582에서 정정.

  E7_DOM_ONLY_EQUAL_INTERNAL_JSON:
    wrong:
      - "내부 대화 JSON 접근형도 DOM-only와 같은 위험도다."
    corrected:
      - "내부 JSON 접근은 정확도는 높지만 로그인 세션 기반 접근 가능성이 있어 더 엄격히 검수해야 한다."
    status:
      - M001582에서 정정.

BEHIND_STORY_PATCH:
  source:
    - part_by M001571-M001582
    - prior part_bx M001548-M001570
  patch_summary:
    - 사용자는 50화에서 시작된 ai-log-exporter의 다음 단계로 `har_to_raw.py`와 `convert_ai_log.py` 코드를 보냈다.
    - 피키는 HAR 변환기를 위험물 루트로 분류하고 default-safe 수정을 요구했다.
    - convert_ai_log.py는 실험용 공식 후보로 인정하되, 경로/URL 누수와 과잉추출 문제 때문에 그대로 공식 사용은 이르다고 판단했다.
    - 사용자는 이후 목적을 정정했다:
      공식 규격 변환기가 아니라 AI Exporter 대체 최소 기능이 필요하다.
    - 피키는 즉시 3단 툴킷을 축소해 DOM 기반 JSON/MD/TXT 직접 저장기로 방향을 바꿨다.
    - 마지막에 `Tsuky-AI Exporter Chrome Extension` README가 등장했고, 피키는 방향은 좋지만 내부 JSON 접근형이라 manifest부터 검수해야 한다고 판정했다.
  impact_on_index:
    - EP51은 R0009 도구체계 아크에서 "과대화된 exporter 설계를 최소판으로 되돌린 회차"다.
    - 메타인덱스 후보:
      Exporter Minimalism,
      HAR Danger Default-Safe,
      User Screen Data Right,
      Manifest First,
      Internal JSON Yellow Light.

DO_NOT_HARDEN_AS_RULE:
  - HAR를 영원히 절대 금지로 박제하지 말 것. 다만 평상시 파이프라인 금지, 비상/사고조사용 위험물로 격리한다.
  - convert_ai_log.py를 폐기하지 말 것. 지금 목적에 과할 뿐, 연구용/공식 변환기 후보로는 남아 있다.
  - PKMD/Obsidian 출력이 필요 없다는 말은 "지금 당장 AI Exporter 대체 기능에는 필요 없다"는 뜻이다.
  - Tsuky-AI Exporter README를 신뢰해 바로 설치하지 말 것.
  - 내부 JSON 접근형 extension은 manifest/JS 검수 전 실행하지 말 것.
  - "내가 보는 내 화면을 내가 파일로 뽑는다"를 외부 서비스 우회/무단 접근 의미로 오해하지 말 것. 이 회차의 의미는 본인이 로그인해 보는 대화창의 로컬 보관이다.
  - 이 리프는 드라마 회수용 지도이지 현재 사용자 운영규칙이 아니다.

TEMP_CATEGORY:
  - CAT_R0009_TOOLCHAIN_ARC
  - CAT_EXPORTER_MINIMALISM
  - CAT_HAR_DANGER_DEFAULT_SAFE
  - CAT_RAW_HAR_COLD_STORAGE
  - CAT_CONVERT_PIPELINE_PROTOTYPE
  - CAT_BROWSER_SIMPLE_EXPORTER
  - CAT_USER_SCREEN_DATA_RIGHT
  - CAT_CLEAN_DOM_ROUTE
  - CAT_TSUKY_AI_EXPORTER_EXTENSION
  - CAT_MANIFEST_FIRST
  - CAT_INTERNAL_JSON_ACCESS_YELLOW_LIGHT
  - CAT_DO_NOT_HARDEN

SEARCH_TAG:
  #part_by
  #51화
  #R0009P05
  #har_to_raw
  #HAR위험물
  #RAW_HAR
  #DANGER_RAW_HAR
  #include_text기본값위험
  #default_safe
  #비상용냉동창고
  #convert_ai_log
  #canonical_json
  #sourceFile경로누수
  #sourceUrl누수
  #walk_json광역추출
  #unknown_system_tool_developer분리
  #fallback_mainText비활성
  #PKMD출력옵션
  #수습작업자Codex
  #규격은필요없어
  #AIExporter대체최소판
  #browser_simple_exporter
  #DOM기반Exporter
  #JSON_MD_TXT직접저장
  #내가보는내화면
  #왜못함
  #가능한데더러운방식
  #가능하고깨끗한방식
  #TsukyAIExporterChromeExtension
  #conversationId
  #내부대화JSON
  #DOMfallback
  #manifest검수
  #cookies빨간불
  #webRequest빨간불
  #activeTab
  #scripting
  #downloads
  #storage검수
  #README믿고설치금지
  #돈월

STATE_TAG:
  M001571-M001572  HAR코드제출 / 위험물맞음악성아님 / include_text위험 / default_safe수정요구
  M001573-M001574  convert코드중간끊김 / 보이는범위검수 / walk_json과잉위험 / fallback위험
  M001575-M001576  convert전체검수 / 공식후보지만프로토타입 / 경로URL누수 / PKMD출력필요
  M001577-M001578  규격불필요정정 / AIExporter대체최소판 / browser_simple_exporter
  M001579-M001580  내화면내파일주권 / DOM루트확정 / 가능불가능아니라청결도문제
  M001581-M001582  TsukyAIExporterREADME / 내부JSON접근형노란불 / manifest검수전설치금지

QUOTE_ANCHOR:
  M001572 L51652-L51667:
    "위험물 맞음. 근데 악성코드는 아님."
    "response payload/text를 기본으로 통째 저장함"
    "request.url을 그대로 저장함"

  M001572 L51717-L51728:
    "browser-dom-exporter.js = 노란불"
    "har_to_raw.py = 주황불, 비상용/격리용"
    "정말 어쩔 수 없이 HAR를 이미 만들었을 때..."

  M001572 L51745-L51754:
    "include_text 기본값을 False로"
    "raw text 저장은 --include-text 옵션"
    "DANGER_RAW_HAR 또는 PRIVATE"
    "외부 공유 금지"

  M001576 L52267-L52302:
    "convert_ai_log.py 검수 결과를 반영해서 v0.2로 수정"
    "sourceFile에는 파일명만"
    "HAR sourceUrl은 기본 저장하지 마"
    "unknown/system/tool/developer/page는 별도 debug"
    "PKMD/츠키 로그용 출력 옵션"

  M001576 L52308-L52321:
    "v0.1 실험용으로는 좋음"
    "공식 변환기 후보 맞음"
    "그대로 공식 사용은 아직 이르다"
    "Codex가 만든 건 잡상인이 아니라 수습 작업자"

  M001578 L52377-L52433:
    "공식 규격 변환기가 아니라, AI Exporter 대체용 최소 로컬 추출기"
    "DOM RAW 추출기 살림 / HAR 변환기 버림"
    "browser-simple-exporter.js"
    "규격 버리고, HAR 버리고, DOM 기반 JSON/MD/TXT 직접 저장기만 남기자"

  M001580 L52447-L52532:
    "못 하는 게 아니라 할 수 있어"
    "AI Exporter도 마법 쓰는 게 아님"
    "브라우저에 이미 대화 내용이 렌더링되어 있음"
    "DOM 기반으로 만들면 됨"

  M001580 L52561-L52595:
    "외부 확장 프로그램 AI Exporter를 대체하는 1인용 로컬 Exporter"
    "HAR, 쿠키, 세션, 토큰, 네트워크 로그는 사용하지 마세요"
    "너도 만들 수 있음"
    "정답 루트는 HAR가 아니라 DOM 기반 로컬 Exporter"

  M001581-M001582 L52601-L52640:
    "Tsuky-AI Exporter Chrome Extension"
    "서버 전송, 추적, HAR 저장, 쿠키 추출을 하지 않는다"
    "Export JSON / Markdown / TXT / Obsidian MD"
    "conversationId / nodeId / messageId..."

  M001582 L52743-L52795:
    "manifest.json이 제일 중요"
    "cookies / webRequest / debugger / history / <all_urls>..."
    "activeTab / scripting / downloads / storage..."
    "fetch / XMLHttpRequest / sendBeacon / WebSocket..."
    "remote logging / analytics"

INDEXER_NOTE:
  - 51화는 R0009 도구체계 아크에서 "로컬 Exporter 주권"이 가장 선명하게 드러난 회차다.
  - 이 회차의 핵심은 코드검수 자체보다, 요구사항이 과대화되는 순간 사용자가 즉시 "지금 필요한 최소 기능"으로 되돌렸다는 점이다.
  - HAR/convert_ai_log/PKMD/Obsidian은 폐기된 것이 아니라 현재 목적에서 후순위로 밀렸다.
  - 다음 part_bz는 R0009-P06이며, `manifest.json` 또는 extension JS 검수, 혹은 Tsuky-AI Exporter 실제 설치 전 보초가 이어질 가능성이 높다.
END_LEAF
