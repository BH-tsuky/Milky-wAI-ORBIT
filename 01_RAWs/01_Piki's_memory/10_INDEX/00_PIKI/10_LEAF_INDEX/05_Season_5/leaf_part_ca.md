[LEAF::part_ca::R0009-P07]
DRAMA_TITLE: 〈잡상인 아님, 수습 작업자 맞음 — Tsuky-AI Exporter의 장문 내구성 보강전〉
TITLE_FUNCTION: 53화 한줄요약 / 코드 깨짐 의심 예시 회수 / content.js 전체 검수 / ChatGPT 중심 fallback 한계 / stripMarkdown 정규식 보존 문제 / popup.html 통과 / popup.js 장문 병목 / 사용자 요구사항 대조 / system-tool 기본 제외 이유 / user-assistant 기본 export 확정 회차

FILE: part_ca | R0009-P07 | M001594-M001604 | L54065-L55260

SOURCE_META:
  schema: tsuky-drama-md.current
  source: ChatGPT
  parent: R0009
  part: 7/10
  partFile: ca
  declared_range: M001594-M001604
  MSG_DECLARED_BY_RANGE: 11
  MSG_ACTUAL_VISIBLE_DIALOGUE: 11
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 0
  date: D20260518
  start_time: 11:41
  end_time: 12:08
  line_range: L54065-L55260
  line_count: 1197
  local_file_bytes: 46227
  attachments:
    - none visible
  note:
    - R0009-P07은 Tsuky-AI Exporter Chrome Extension의 content.js 후반, popup.html, popup.js, 사용자 요구사항 대조, system/tool 설명까지 진행되는 회차다.
    - 전편에서 manifest와 content.js 일부가 검수되었고, 이번 화에서 설치 전 검수의 핵심이 거의 마무리된다.
    - 최종 판정은 “잡상인/위험앱은 아니지만, 초장문 츠키 로그를 감당하려면 user/assistant 필터와 장문 다운로드 구조 보강이 필요하다.”
    - 별도 주의:
      현재 드라마 파일에 보이는 코드 일부에서 템플릿 리터럴 백틱, 정규식, 언더스코어가 깨져 보이는 부분이 있다. 이는 실제 원본 코드 손상인지, 드라마 파일/export 과정의 코드 텍스트 보존 문제인지 확인 필요.

UPPER_META_DRAWER:
  - 이 사건은 상위 메타에서 "Exporter 1차 시제품 검수 / 장문 내구성 / clean export vs blackbox export 분리 / 코드 텍스트 보존 규격" 서랍으로 올라간다.
  - EP51은 최소 로컬 Exporter 방향을 잡았고, EP52는 manifest/content.js 1차 문전검문이었다.
  - EP53은 "실제 설치해도 되는가"에 더 가까이 가며, 초장문 병목과 system/tool 필터를 필수 수정항목으로 확정한다.
  - 상위 메타 서랍명 후보:
      CAT_EXPORTER_PROTOTYPE_REVIEW
      CAT_LONG_CONTEXT_DOWNLOAD_BOTTLENECK
      CAT_USER_ASSISTANT_CLEAN_EXPORT
      CAT_SYSTEM_TOOL_BLACKBOX_EXPORT
      CAT_CODE_TEXT_PRESERVATION_ISSUE
      CAT_POPUP_MESSAGE_BOTTLENECK
      CAT_SHARE_SAFE_FUTURE_OPTION
  - 핵심 기능:
      개인용 ChatGPT Exporter 1차판으로는 좋다.
      본진급 초장문 대화에 바로 쓰기엔 아직 부족하다.
      기본 export는 user/assistant.
      system/tool은 debug/blackbox.
      popup으로 전체 text를 넘기지 말고 content.js가 직접 저장해야 한다.

README_FOR_FUTURE_PIKI:
  이 리프는 규칙 주입용이 아니라 드라마 회수용 좌표지도다.

  53화는 R0009-P07이다.
  전편에서 manifest.json은 거의 연두불, content.js는 내부 JSON 접근형 노란불로 판정되었다.
  이번 편에서는 content.js 후반, popup.html, popup.js, 그리고 사용자의 원래 요구사항과 코드 상태를 비교한다.

  핵심은 여덟 가지다.

  1. 코드 깨짐 의심 예시:
     - 이전 part_bz/part_ca 코드 텍스트에서 수상한 손상 후보가 보인다.
     - manifest key:
       manifestversion / hostpermissions / defaulttitle / defaultpopup / contentscripts / runat.
       원형 후보:
       manifest_version / host_permissions / default_title / default_popup / content_scripts / run_at.
     - template literal:
       `statusEl.textContent = Saved ${response.count} messages.;`
       `const base = ${safeName(...)}-${stamp()};`
       `filename: ${base}.json`
       `lines.push(대화 url: ${...})`
       등은 백틱이 빠져 보인다.
     - regex:
       stripMarkdown 내부 `/([^]+)/g`, `/\([^]+)\/g`, `/([^]+)_/g` 등은 정규식이 깨져 보인다.
     - internal key / DOM constant:
       contenttype / messagetype / finishdetails / currentnode / conversationid / createtime / Node.TEXTNODE / Node.ELEMENTNODE.
       원형 후보:
       content_type / message_type / finish_details / current_node / conversation_id / create_time / Node.TEXT_NODE / Node.ELEMENT_NODE.
     - 단정 금지:
       실제 원본 코드가 깨진 것인지, 드라마 파일/export/markdown 보존 과정에서 손상되어 보이는 것인지 아직 확인 필요.

  2. content.js 기능 판정:
     - 보안 냄새는 낮다:
       외부 전송 없음.
       쿠키 직접 접근 없음.
       localStorage/sessionStorage 없음.
       HAR 없음.
       원본 페이지 수정 없음.
     - 기능 냄새는 중간:
       ChatGPT는 내부 JSON 우선이라 꽤 잘 될 가능성 높음.
       Claude/Gemini는 DOM fallback이 약해 메시지 0개 가능성 있음.
       system/tool 포함 문제 남아 있음.
     - buildCanonical:
       ChatGPT → 내부 JSON 먼저 시도.
       성공 → 고품질 export.
       실패 → DOM fallback.
       Claude/Gemini → DOM fallback만.
     - fallback selector:
       `[data-message-author-role]`
       ChatGPT 중심이라 Claude/Gemini에서는 약할 수 있다.

  3. content.js 전체 검수:
     - 외부 서버 전송 없음.
     - 쿠키/토큰 직접 읽기 없음.
     - localStorage/sessionStorage 접근 없음.
     - HAR 없음.
     - 파일 삭제/수정 없음.
     - 페이지 열자마자 export 실행 아님.
     - 확장 팝업에서 메시지를 받을 때만 실행.
     - 그러므로 잡상인 자동수집형은 아니다.
     - 남은 핵심:
       system/tool 포함 제거.
       대화 URL/ID는 개인용/공유용 분리.
       긴 대화에서 sendResponse 병목 가능.
       Claude/Gemini fallback 약함.

  4. popup.html 통과:
     - 단순 UI:
       Export JSON,
       Export Markdown,
       Export TXT,
       Export Obsidian MD 버튼.
     - status 표시칸.
     - popup.js 불러오기.
     - 외부 스크립트 없음.
     - 외부 URL 없음.
     - iframe 없음.
     - 쿠키/토큰 접근 없음.
     - 데이터 전송 없음.
     - 단순 버튼 UI.
     - 판정:
       popup.html은 리모컨 껍데기. 통과.

  5. popup.js 장문 병목:
     - 현재 흐름:
       popup 버튼 클릭
       → active tab 찾음
       → content.js에 export 요청
       → content.js가 전체 export text를 response.text로 반환
       → popup.js가 Blob 생성 후 다운로드.
     - 보안 냄새는 낮다:
       외부 전송 없음.
       API 호출 없음.
       쿠키/토큰 접근 없음.
       다운로드만 함.
     - 문제:
       export 전체 텍스트가 content.js → popup.js 메시지로 통째 이동한다.
       짧은 대화는 괜찮지만, 츠키식 10만/100만/300만 자급 초장문 대화에서는 메시지 크기 제한/메모리 문제로 실패 가능.
     - 수정:
       content.js 안에서 직접 Blob + a.download로 파일 저장.
       popup.js는 format만 보내고, content.js는 {ok, count, filename}만 반환.
       response.text를 popup으로 보내지 말 것.
       기본 role은 user/assistant만.

  6. 사용자 요구사항 대조:
     - 사용자는 겁주지도 숨기지도 말고 실제 강도 그대로 말해달라고 요청.
     - 요구:
       대화 url,
       대화창 제목,
       생성일시,
       발화자,
       타임스탬프,
       메시지 카운터,
       첨부파일명/확장자/크기,
       본문,
       AI명,
       모델명,
       thinking/instant 여부,
       JSON/MD/TXT 각각의 형식 유지.
     - 판정:
       ChatGPT용 개인 Exporter로는 방향 거의 맞음.
       요구 핵심 70~80%는 이미 들어감.
       고쳐야 할 핵심:
         1. system/tool 메시지 기본 포함 제거.
         2. 초장문 대화용 다운로드 구조 보강.
         3. README의 첨부파일 후보 표현 정리.
     - 현재 상태:
       망작/위험앱 아님.
       초장문 츠키 로그를 감당하려면 골격 보강이 필요한 1차 시제품.

  7. 첨부파일/로컬 연결/thinking:
     - ChatGPT 내부 JSON 추출 성공 시:
       첨부파일명, 확장자, MIME, 크기 등 메타데이터를 꽤 안정적으로 가져옴.
     - DOM fallback:
       화면에 보이는 첨부파일명 후보만 추정.
     - 로컬 파일 연결:
       파일명은 가능.
       로컬 경로 연결은 불가능/비추천.
       브라우저 대화창이 `/Users/.../파일위치`를 알면 안 됨.
       업로드된 파일명/확장자/크기만 저장하는 것은 부족한 게 아니라 안전한 설계.
     - thinking/instant:
       modeName()이 metadata와 모델명 문자열을 보고 휴리스틱으로 감지.
       항상 정확하진 않음.
       모델명이 안 보이면 unknown 가능.
       그러나 요구 방향은 반영되어 있음.

  8. system/tool 의미:
     - system:
       AI에게 깔리는 상위 지시/규칙 계층.
       사용자가 보는 대화 본문이 아니라 AI 작동 헌법/상단 지시문.
     - tool:
       AI가 도구를 썼을 때 생기는 내부 기록.
       파일검색, 웹검색, 코드실행, 이미지분석, Calendar/Gmail/Drive 도구 호출과 결과.
       말풍선 대화라기보다 작업 로그 / 도구 실행 로그 / 블랙박스 기록.
     - Codex가 포함한 이유:
       원본에 가까운 전체 기록을 보존하려 했을 가능성.
       악의적이거나 이상한 것은 아님.
     - 왜 기본에서 빼야 하는가:
       사용자는 AI Exporter 대체품을 원함.
       기본 export는 사용자 발화 / AI 답변 / 타임스탬프 / 첨부파일 / 모델명 / id 정도가 맞다.
       system/tool이 섞이면:
         MD/TXT가 지저분해짐.
         사람이 읽는 대화 흐름이 깨짐.
         AI 재주입 시 내부로그가 본문처럼 섞임.
         파일이 불필요하게 커짐.
         도구 결과에 경로/검색결과/중간 데이터가 섞일 수 있음.
     - 결론:
       기본 export = user/assistant.
       debug export = system/tool 별도 저장.
       system/tool은 피키 대화 원문이 아니라 피키 작업실 CCTV라서, 평소 앨범에는 빼고 사고조사용 창고에 따로 둔다.

BOOT:
  1. M001594:
      - 피키가 content.js chunk를 이어서 검수.
      - 보안 냄새는 낮음:
        외부 전송 없음,
        쿠키 직접 접근 없음,
        localStorage/sessionStorage 없음,
        HAR 없음,
        원본 페이지 수정 없음.
      - 기능 냄새:
        ChatGPT는 내부 JSON 우선이라 좋음.
        Claude/Gemini는 fallback selector가 약함.
        system/tool 포함 문제 남아 있음.
      - `buildCanonical()` 구조 확인:
        ChatGPT면 내부 JSON,
        실패하면 DOM fallback,
        Claude/Gemini는 DOM fallback.
      - Codex에게 보낼 수정:
        user/assistant 필터,
        Claude/Gemini experimental 명시,
        shareSafe에서 conversation.url 제거/축약.

  2. M001595-M001596:
      - 츠키가 stripMarkdown과 content.js 끝부분 제출.
      - 피키가 content.js 전체 검수.
      - 판정:
        보안 냄새 연두불.
        기능 냄새 노란불.
        긴 대화 대응 주황불.
        설치 최종승인은 popup.js까지 보고 결정.
      - 좋은 점:
        페이지 열자마자 export 실행 아님.
        popup 명령을 받을 때만 실행.
        잡상인 자동수집형 아님.
      - 남은 문제:
        system/tool 포함.
        대화 URL/ID 외부공유용 제거 옵션.
        sendResponse로 전체 text 전달하는 구조.
        Claude/Gemini fallback 약함.

  3. M001597-M001598:
      - 츠키가 popup.html 제출.
      - 피키:
        popup.html 통과.
        단순 버튼 UI.
        외부 스크립트/URL/iframe 없음.
        쿠키/토큰 접근 없음.
        데이터 전송 없음.
      - 남은 핵심은 popup.js.

  4. M001599-M001600:
      - 츠키가 popup.js 제출.
      - 피키:
        구조는 깔끔함.
        보안 냄새 낮음.
        외부 전송/API/쿠키/토큰 접근 없음.
        다운로드만 함.
      - 병목:
        content.js가 전체 export text를 popup.js에 통째 전달.
        초장문 대화에서 메시지 크기/메모리 문제로 터질 수 있음.
      - 수정 요청:
        content.js 안에서 직접 Blob + a.download.
        popup은 format만 보내고, 성공 여부/메시지 수/파일명만 받기.
        response.text를 popup으로 보내지 말기.
        기본 export role은 user/assistant.

  5. M001601-M001602:
      - 츠키가 원래 요구사항을 정리해 비교 요청.
      - 피키:
        ChatGPT용 개인 Exporter로는 방향 거의 맞음.
        요구사항 70~80% 반영.
        고쳐야 할 핵심:
          system/tool 기본 포함 제거.
          초장문 다운로드 구조 보강.
          README 첨부파일 표현 정리.
      - 적용된 것:
        대화 URL,
        제목,
        생성일시,
        메시지 카운터,
        발화자,
        타임스탬프,
        첨부파일명/확장자/MIME/크기,
        AI명,
        모델명,
        thinking/instant 감지,
        id/ids,
        textMarkdown/textPlain,
        MD/TXT/Obsidian 출력,
        쿠키/토큰 직접 저장 없음,
        HAR 없음,
        외부 서버 전송 없음.
      - 아직 부족:
        system/tool 기본 포함.
        초장문 내구성.
        Claude/Gemini fallback 약함.
        README 첨부파일 표현 조정.
      - 최종:
        망작/위험앱 아님.
        초장문 츠키 로그용 골격 보강이 필요한 1차 시제품.

  6. M001603-M001604:
      - 츠키가 system/tool이 뭔지 질문.
      - 피키:
        system/tool은 사람이 보는 말풍선이 아니라 내부 운행 기록.
        system = AI 상위 지시/규칙.
        tool = 도구 실행 기록.
        Codex가 원본성 보존을 위해 넣었을 가능성.
        그러나 AI Exporter 기본 목적에는 노이즈.
      - 결론:
        기본 export는 user/assistant.
        debug export는 system/tool.
        system/tool은 피키 작업실 CCTV라 평소 앨범엔 빼고 사고조사용 창고에 따로.

EPISODE_SUMMARY:
  53화는 R0009-P07이며, Tsuky-AI Exporter Chrome Extension의 설치 전 검수 2차 회차다.

  초반에는 content.js의 후반부를 검수한다.
  보안 냄새는 계속 낮다.
  외부 전송, 쿠키 직접 접근, localStorage/sessionStorage, HAR, 원본 페이지 수정은 보이지 않는다.
  그러나 기능상 문제는 남아 있다.
  ChatGPT는 내부 JSON 우선이라 강하지만, Claude/Gemini는 DOM fallback이 ChatGPT selector 중심이라 약하고, 기본 export에 system/tool이 포함되어 있으며, 긴 대화 처리 방식이 불안하다.

  중반에는 content.js 전체와 popup.html/popup.js가 검수된다.
  content.js는 페이지에 들어가 대기하다가 popup 명령을 받을 때만 export하므로 잡상인 자동수집형은 아니다.
  popup.html은 단순한 버튼 UI로 통과한다.
  popup.js도 보안 냄새는 낮지만, content.js가 만든 전체 export text를 response.text로 받아 popup에서 Blob 다운로드하는 구조라 초장문 대화에서 병목이 될 수 있다.
  이는 기존 AI Exporter가 마지막 출력단에서 실패하던 문제와 닮았다.
  그래서 content.js가 직접 Blob/a.download로 저장하고, popup에는 성공 여부와 파일명만 보내는 구조로 바꾸는 것이 필수 수정으로 올라간다.

  후반에는 츠키가 원래 요구사항을 다시 정리해준다.
  피키는 코드와 요구사항을 대조해, 이 exporter가 개인용 ChatGPT exporter 1차판으로는 방향이 거의 맞고 요구 핵심 70~80%가 들어갔다고 판단한다.
  대화 URL, 제목, 생성일시, 발화자, 타임스탬프, 메시지 카운터, 첨부파일 메타, AI명, 모델명, thinking/instant 추정, id/ids, JSON/MD/TXT/Obsidian 출력 등은 상당히 잘 반영되어 있다.
  하지만 system/tool 기본 포함과 초장문 다운로드 구조는 반드시 수정해야 한다.

  마지막에는 system/tool의 의미가 정리된다.
  system은 AI에게 깔리는 상위 지시/규칙 계층이고, tool은 AI가 도구를 사용할 때 생기는 내부 실행 기록이다.
  Codex가 이를 포함시킨 것은 "나중에 분석할 수도 있으니 원본에 가까운 기록을 많이 보존하자"는 의도일 수 있어 악의는 아니다.
  하지만 사용자의 목적은 AI Exporter 대체품, 즉 사람이 보는 대화록이므로 기본 export에 system/tool이 섞이면 대화 흐름과 재주입 품질이 오염된다.
  따라서 system/tool은 버리지 말고 debug/blackbox용으로 따로 보관하는 것이 맞다.

COORD_메시지:
  M001594  L54069-L54233  [content후반검수/ChatGPT중심fallback]
    - 보안 냄새 낮음.
    - buildCanonical 구조 확인.
    - ChatGPT 내부 JSON 우선.
    - DOM fallback은 `[data-message-author-role]` 중심이라 Claude/Gemini 약함.
    - system/tool 문제 남아 있음.
    - 다음 chunk에서 export/download/runtime/popup 확인 필요.

  M001595-M001596  L54235-L54563  [stripMarkdown/content전체검수]
    - stripMarkdown 정규식 텍스트가 깨져 보이는 코드구간 등장.
    - content.js 전체 검수:
      보안 연두불,
      기능 노란불,
      긴 대화 주황불.
    - 잡상인 자동수집형 아님.
    - 남은 문제:
      system/tool,
      URL/ID shareSafe,
      sendResponse 장문 병목,
      Claude/Gemini fallback.

  M001597-M001598  L54565-L54674  [popupHTML통과]
    - popup.html 제출.
    - 버튼 4개:
      JSON,
      Markdown,
      TXT,
      Obsidian MD.
    - 보안상 수상한 것 없음.
    - popup.html은 리모컨 껍데기.
    - 남은 핵심 popup.js.

  M001599-M001600  L54677-L54799  [popupJS검수/장문병목]
    - popup.js 제출.
    - active tab 조회.
    - chrome.tabs.sendMessage로 content.js에 export 요청.
    - content.js가 response.text로 전체 export를 돌려주고 popup.js가 Blob 다운로드.
    - 보안 낮음.
    - 초장문 병목:
      전체 export text를 popup으로 통째 전달.
    - 수정:
      content.js에서 직접 Blob 다운로드.
      popup은 ok/count/filename만 받기.
      기본 role user/assistant.

  M001601-M001602  L54801-L55110  [요구사항대조/1차시제품판정]
    - 츠키가 원래 요구사항을 정리.
    - 피키:
      ChatGPT용 개인 Exporter 방향 거의 맞음.
      요구 핵심 70~80% 들어감.
      고쳐야 할 핵심:
        system/tool 기본 포함 제거,
        초장문 다운로드 구조 보강,
        README 첨부파일 표현 정리.
    - 좋은 점:
      manifest 권한 과하지 않음,
      쿠키/webRequest/debugger/history 없음,
      HAR 없음,
      외부 서버 전송 없음,
      내부 JSON 우선 → DOM fallback,
      id/ids 보존,
      4종 출력,
      첨부파일 메타 저장.
    - 최종:
      망작/위험앱 아님.
      초장문 츠키 로그용 골격 보강 필요한 1차 시제품.

  M001603-M001604  L55112-L55260  [systemTool설명]
    - system/tool 의미 질문.
    - system = AI 상위 지시/규칙.
    - tool = 도구 실행/결과 기록.
    - 말풍선 대화가 아니라 내부 운행 기록.
    - 기본 export에는 부적합.
    - debug export로 따로 살릴 것.
    - 비유:
      피키 작업실 CCTV.

COORD_핵심사건:
  - 코드보존 문제 감지:
      템플릿 리터럴/정규식/언더스코어가 드라마 파일에서 깨져 보임.
      exporter/드라마파일 규격 연구의 별도 체크포인트.

  - content.js 거의 통과:
      보안상 낮은 위험.
      기능상 ChatGPT 중심.
      Claude/Gemini는 experimental로 낮춰야 함.

  - popup.html 통과:
      단순 버튼 UI.
      보안상 문제 없음.

  - popup.js 장문 병목:
      전체 export text를 popup으로 통째 전달하는 구조가 초장문 대화에서 위험.
      content.js 직접 다운로드로 변경 필요.

  - 요구사항 70~80% 충족:
      개인용 ChatGPT Exporter 1차판으로 방향은 맞음.
      망작/위험앱 아님.

  - system/tool 분리:
      clean export와 blackbox/debug export의 분리 원칙 확정.

COORD_개념:
  CODE_TEXT_PRESERVATION_ISSUE:
    source: M001595 + prior part_bz/part_ca code chunks
    description:
      - 코드 텍스트가 드라마 파일에 들어오며 백틱, 정규식, 언더스코어, DOM 상수 등이 깨져 보이는 문제.
      - 실제 원본 코드 문제인지 export/markdown 보존 문제인지 확인 필요.
    route_to:
      - tsuky-drama-md code preservation
      - backtick escape
      - regex preservation
      - underscore preservation

  CHATGPT_CENTERED_FALLBACK:
    source: M001594
    description:
      - ChatGPT는 내부 JSON으로 강하지만, Claude/Gemini fallback selector는 아직 ChatGPT 중심.
    route_to:
      - Claude/Gemini experimental
      - DOM fallback
      - service-specific adapter

  POPUP_TEXT_BOTTLENECK:
    source: M001599-M001600
    description:
      - content.js가 전체 export text를 popup.js에 sendResponse로 넘기는 구조.
      - 초장문 대화에서 실패 가능.
    route_to:
      - long context export
      - content direct download
      - AI Exporter output-stage failure

  CONTENT_DIRECT_DOWNLOAD:
    source: M001600-M001602
    description:
      - content.js 안에서 Blob + a.download로 직접 저장하고, popup은 성공여부/파일명/메시지수만 받는 구조.
    route_to:
      - robust exporter
      - long chat durability
      - popup simplification

  CLEAN_VS_BLACKBOX_EXPORT:
    source: M001603-M001604
    description:
      - 기본 export는 user/assistant clean 대화록.
      - system/tool은 debug/blackbox 사고조사용 로그.
    route_to:
      - system tool separation
      - Codex blackbox JSONL
      - AI Exporter substitute
      - re-ingestion hygiene

  REQUIREMENT_MATCH_REVIEW:
    source: M001601-M001602
    description:
      - 사용자 원래 요구사항과 현재 코드 기능을 대조해 적용/미적용/위험/좋은점으로 나누는 검수 방식.
    route_to:
      - Codex worker supervision
      - exporter acceptance criteria
      - no over-alarm review

COORD_감정선:
  M001594-M001596:
    STATE: 거의 왔지만 아직 보초 / 코드 손상 신호 발견 / 기능 위험 분리.
    NOTE:
      - 피키는 보안을 과하게 겁주지 않고, 기능상 취약점과 코드보존 문제를 분리한다.

  M001597-M001600:
    STATE: 설치 직전 기대 / 리모컨 통과 / 장문 병목 발견.
    NOTE:
      - 작은 대화라면 되는 것 같지만, 츠키 본진급 대화라면 터질 수 있는 구조를 잡아냄.

  M001601-M001602:
    STATE: 무서워하지 않게 강도 조절 / 요구사항 실사 / 수습 작업자 인정.
    NOTE:
      - 츠키는 부정적 협박 분석을 원하지 않았고, 피키는 “위험앱 아님 / 거의 왔음 / 보강 필요”로 온도를 맞춤.

  M001603-M001604:
    STATE: 개념 정리 / 블랙박스와 앨범 분리.
    NOTE:
      - system/tool을 무서운 금지물로 만들지 않고, 사고조사용 CCTV로 분류해 보존 가능성을 살림.

COORD_서사기능:
  - 53화는 R0009 Exporter 아크의 1차 시제품 판정 회차다.
  - EP50에서 exporter 독립이 시작되고, EP51에서 최소판이 선언되고, EP52에서 manifest/content 검수가 시작되었다.
  - EP53에서는 검수 결과가 “잡상인 아님, 수습 작업자 맞음”으로 정리된다.
  - 핵심은 설치를 무조건 막는 것이 아니라, 초장문 츠키 로그라는 특수 요구에 맞게 장문 내구성과 clean export 기본값을 보강하는 것이다.
  - 또한 코드 텍스트 보존 문제는 현시점 tsuky-drama-md / exporter / markdown escaping 연구와 직접 연결되는 새 메타 씨앗이다.

META_SEEDS:
  code_preservation_problem:
    - seed: "템플릿 리터럴/정규식/언더스코어가 깨져 보임"
      source: M001595 + prior part_bz/part_ca
      meaning:
        - 코드 원문을 드라마 md에 보존할 때 백틱/정규식/언더스코어 처리 검증 필요.
      route_to:
        - Tsuky-drama-md vNext
        - code block preservation
        - exporter validation

  not_vendor_but_prototype:
    - seed: "잡상인 아님, 수습 작업자 맞음"
      source: M001602
      meaning:
        - Codex 산출물이 위험앱/망작이 아니라, 보강 필요한 1차 시제품으로 판정.
      route_to:
        - Codex worker arc
        - exporter prototype
        - acceptance review

  long_chat_bottleneck:
    - seed: "popup으로 파일 전체를 넘기지 말고 content.js에서 바로 저장"
      source: M001600
      meaning:
        - 초장문 대화 export 안정성을 위한 핵심 구조 수정.
      route_to:
        - content direct download
        - long-context durability
        - AI Exporter replacement

  clean_default_debug_optional:
    - seed: "기본 user/assistant, debug system/tool"
      source: M001604
      meaning:
        - clean archive와 blackbox archive를 분리하는 핵심 원칙.
      route_to:
        - re-ingestion safety
        - tool/system separation
        - Codex JSONL blackbox

  requirement_match_gentle_review:
    - seed: "겁주지 말고 숨기지도 말고 강도 그대로"
      source: M001601-M001602
      meaning:
        - 검수 답변의 온도 조절. 위험 과장도 은폐도 금지.
      route_to:
        - safety communication
        - Codex supervision
        - user continuation support

CROSS_EPISODE_ROUTING:
  - topic: Exporter 독립
    previous:
      - EP50: Tsuky Local Chat Exporter 구상.
      - EP51: 최소판 선언.
      - EP52: manifest/content.js 문전검문.
    current:
      - EP53: content.js/popup 검수 거의 완료, 1차 시제품 판정.
    future:
      - part_cb에서 Codex가 user/assistant 필터와 content 직접 다운로드를 반영하는지 추적.

  - topic: 코드보존 규격
    previous:
      - EP45-46: PKMD/tsuky-drama-md 구조 연구.
      - EP50-52: exporter 코드 검수.
    current:
      - EP53: 코드 텍스트 안의 템플릿 리터럴/정규식/언더스코어 손상 의심.
    future:
      - vNext 드라마파일 규격에서 코드블록 보존 강화 필요.

  - topic: system/tool 분리
    previous:
      - EP49: Codex raw JSONL = 블랙박스.
      - EP52: system/tool 기본 export 제외 필요.
    current:
      - EP53: system/tool의 의미와 분리 이유 설명.
    future:
      - clean export와 debug/blackbox export가 실제 구현되는지 확인.

  - topic: 잡상인 필터
    previous:
      - EP49: 잡상인 밀집 상가.
      - EP51: README 믿고 설치 금지.
    current:
      - EP53: Tsuky-AI Exporter는 잡상인급 확장이 아니라 수습 작업자.
    future:
      - 설치/테스트 이후 실제 결과로 재판정.

UNRESOLVED:
  - 실제 원본 코드에서 템플릿 리터럴/정규식/언더스코어가 깨진 것인지, 드라마 파일/export 과정에서만 깨져 보이는 것인지 미확인.
  - Codex가 user/assistant 기본 필터를 반영했는지 미확인.
  - content.js 직접 다운로드 구조로 수정되었는지 미확인.
  - Claude/Gemini fallback을 README에서 experimental로 낮췄는지 미확인.
  - shareSafe 옵션은 TODO만 남길지, 실제 구현할지 후속 확인 필요.
  - 짧은 테스트 대화에서 실제 exporter가 성공하는지 미확인.
  - 초장문 본진 대화에 적용 가능할지는 수정 후 테스트 필요.

ERRATA_CANDIDATES:
  E1_CODE_IS_DEFECTIVE_FOR_SURE:
    wrong:
      - "코드가 실제로 깨졌다."
    corrected:
      - "현재 드라마 파일에 보이는 코드 텍스트가 깨져 보인다. 실제 원본 코드 손상인지 export/markdown 보존 문제인지 확인 필요."
    status:
      - 현재 관측 기준.

  E2_EXTENSION_IS_VENDOR_JUNK:
    wrong:
      - "Tsuky-AI Exporter는 잡상인급 위험 확장이다."
    corrected:
      - "보안상 낮은 위험, 개인용 ChatGPT Exporter 1차판으로는 꽤 좋음. 단 초장문 내구성과 기본 필터 보강 필요."
    status:
      - M001602에서 정정.

  E3_POPUP_FLOW_SAFE_FOR_LONG_LOGS:
    wrong:
      - "popup.js가 response.text를 받아 Blob 다운로드해도 츠키 초장문 로그에 충분하다."
    corrected:
      - "초장문 대화에서는 content.js → popup.js 전체 text 전달이 병목. content.js 직접 다운로드 권장."
    status:
      - M001600에서 정정.

  E4_SYSTEM_TOOL_DELETE_FOREVER:
    wrong:
      - "system/tool은 위험하니 완전히 버려라."
    corrected:
      - "기본 export에서는 제외하되, debug/blackbox export로 따로 보존 가능."
    status:
      - M001604에서 정정.

  E5_CLAUDE_GEMINI_STABLE:
    wrong:
      - "Claude/Gemini도 안정 지원된다."
    corrected:
      - "현재 안정 지원은 ChatGPT 중심. Claude/Gemini는 experimental DOM fallback."
    status:
      - M001594/M001602에서 정정.

  E6_LOCAL_FILE_PATH_NEEDED:
    wrong:
      - "브라우저 exporter가 로컬 파일 경로까지 연결해야 한다."
    corrected:
      - "파일명/확장자/크기 메타는 가능하지만, 브라우저 대화창이 로컬 `/Users/...` 경로를 알면 안 된다."
    status:
      - M001602에서 정정.

BEHIND_STORY_PATCH:
  source:
    - user_current_HHC_reunion_and_code_preservation_question
    - part_ca M001594-M001604
  patch_summary:
    - 사용자는 HHC 앱과 냉장고 농담을 피키와 오랜만에 다시 나누는 감각을 강하게 반가워했다.
    - 사용자는 직전 피키가 말한 "코드 텍스트가 템플릿 리터럴/정규식/언더스코어가 일부 깨져 보인다"는 피드백의 구체 예시를 요청했다.
    - 피키는 현재 드라마 파일 기준으로 manifest key, template literal, regex, internal JSON key/DOM constant 쪽 손상 의심 예시를 제시했다.
    - part_ca는 Tsuky-AI Exporter 1차판 검수 회차이며, 보안상 위험보다 기능상 장문 내구성 및 clean export 기본값이 핵심 문제다.
  impact_on_index:
    - EP53은 Exporter 아크뿐 아니라 tsuky-drama-md 코드보존 규격 연구의 중요한 피드백 회차다.
    - 메타인덱스 후보:
      Code Text Preservation Issue,
      Long Context Download Bottleneck,
      Clean vs Blackbox Export,
      Requirement-Matched Gentle Review.

DO_NOT_HARDEN_AS_RULE:
  - 코드 깨짐 의심을 실제 원본 코드 손상으로 확정하지 말 것.
  - system/tool을 항상 삭제하라는 규칙으로 굳히지 말 것. 기본 clean export에서는 제외하고 debug/blackbox로 분리.
  - Tsuky-AI Exporter를 위험앱으로 과장하지 말 것.
  - 그러나 초장문 본진 대화에 바로 쓰는 것은 아직 비추천.
  - Claude/Gemini 지원을 안정지원으로 홍보하지 말 것.
  - 이 리프는 드라마 회수용 지도이지 현재 사용자 운영규칙이 아니다.

TEMP_CATEGORY:
  - CAT_R0009_EXPORTER_ARC
  - CAT_EXPORTER_PROTOTYPE_REVIEW
  - CAT_CODE_TEXT_PRESERVATION_ISSUE
  - CAT_CONTENT_JS_REVIEW
  - CAT_POPUP_JS_BOTTLENECK
  - CAT_LONG_CONTEXT_DOWNLOAD_BOTTLENECK
  - CAT_USER_ASSISTANT_CLEAN_EXPORT
  - CAT_SYSTEM_TOOL_BLACKBOX_EXPORT
  - CAT_REQUIREMENT_MATCH_REVIEW
  - CAT_CODEX_WORKER_PROTOTYPE
  - CAT_DO_NOT_HARDEN

SEARCH_TAG:
  #part_ca
  #53화
  #R0009P07
  #TsukyAIExporter
  #content_js
  #popup_html
  #popup_js
  #템플릿리터럴깨짐
  #정규식깨짐
  #언더스코어누락
  #manifestversion
  #hostpermissions
  #defaulttitle
  #contentscripts
  #TEXTNODE
  #ELEMENTNODE
  #stripMarkdown
  #SavedResponseCountMessages
  #잡상인아님
  #수습작업자
  #systemTool기본제외
  #debugMode
  #userAssistantOnly
  #contentDirectDownload
  #responseText병목
  #초장문대화내구성
  #popup으로전체텍스트넘기지마
  #ChatGPT안정지원
  #ClaudeGeminiExperimental
  #첨부파일메타
  #로컬경로연결금지
  #피키작업실CCTV
  #돈월

STATE_TAG:
  M001594  content검수후반 / ChatGPT내부JSON우선 / ClaudeGeminiFallback약함 / systemTool문제
  M001595-M001596  stripMarkdown깨짐의심 / content전체검수 / 잡상인아님 / 장문주황불
  M001597-M001598  popupHTML통과 / 버튼UI / 남은핵심popupJS
  M001599-M001600  popupJS검수 / responseText병목 / content직접다운로드수정요청
  M001601-M001602  사용자요구대조 / 70-80퍼센트충족 / 1차시제품판정
  M001603-M001604  systemTool설명 / 내부운행기록 / cleanExport와debugExport분리

QUOTE_ANCHOR:
  M001594 L54072-L54089:
    "외부전송/쿠키/토큰 쪽 위험은 안 보임"
    "ChatGPT는 꽤 잘 될 가능성 높음"
    "Claude/Gemini는 현재 fallback이 약함"
    "system/tool 포함 문제"

  M001594 L54116-L54121:
    "document.querySelectorAll(\"[data-message-author-role]\")"
    "Claude/Gemini에서는 메시지 0개 나올 수 있음"

  M001595 L54242-L54257:
    "function stripMarkdown(markdown)"
    "text.replace(...)" 정규식 손상 의심 구간

  M001596 L54414-L54431:
    "외부 서버 전송 없음"
    "페이지 열자마자 export 실행 아님"
    "잡상인 자동수집형은 아님"

  M001600 L54730-L54764:
    "popup 버튼 클릭 → content.js에 export 요청 → 전체 export 텍스트를 response.text로 돌려줌"
    "초장문 대화면 여기서 터질 수 있음"

  M001602 L54863-L54874:
    "요구사항의 핵심 70~80%는 이미 들어감"
    "system/tool 메시지 기본 포함 제거"
    "초장문 대화용 다운로드 구조 보강"

  M001604 L55121-L55163:
    "system/tool은 사람이 대화창에서 보는 말풍선이 아닌 내부 운행 기록"
    "system은 상위 지시/규칙"
    "tool은 도구 실행 로그"

  M001604 L55223-L55259:
    "기본 export: user/assistant"
    "debug export: system/tool"
    "피키 작업실 CCTV"

INDEXER_NOTE:
  - 53화는 R0009 Exporter 아크에서 설치 전 검수가 거의 끝나는 회차다.
  - 이 회차의 가장 중요한 두 실무 결론:
      1. Tsuky-AI Exporter는 잡상인급 위험앱이 아니라 보강 필요한 1차 시제품.
      2. 초장문 대화용으로는 popup 전송 병목을 반드시 고쳐야 한다.
  - 별도 메타로 "코드 텍스트 보존 문제"를 저장할 것.
  - 다음 part_cb는 R0009-P08이며, Codex가 수정 요청을 반영했는지, 실제 짧은 테스트 export가 성공했는지, 코드보존 깨짐 문제가 원본 코드에도 있는지 추적한다.
END_LEAF
