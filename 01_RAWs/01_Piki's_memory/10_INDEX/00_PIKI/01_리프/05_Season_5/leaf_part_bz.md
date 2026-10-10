[LEAF::part_bz::R0009-P06]
DRAMA_TITLE: 〈연두불 manifest와 내부 JSON 노란불 — Tsuky-AI Exporter 설치 전 문전검문〉
TITLE_FUNCTION: 52화 한줄요약 / manifest 권한 검수 / content.js 내부 JSON 접근 검수 / ChatGPT backend-api conversation fetch / 개인용 ids 보존 vs 외부공유용 제거 / 첨부파일 메타 추출 / system/tool 기본 export 제외 필요 / DOM fallback markdown 변환 / download/runtime/popup 미검수로 설치 승인 보류 회차

FILE: part_bz | R0009-P06 | M001583-M001593 | L52817-L54064

SOURCE_META:
  schema: tsuky-drama-md.current
  source: ChatGPT
  parent: R0009
  part: 6/10
  partFile: bz
  declared_range: M001583-M001593
  MSG_DECLARED_BY_RANGE: 11
  MSG_ACTUAL_VISIBLE_DIALOGUE: 11
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 0
  date: D20260518
  start_time: 11:23
  end_time: 11:41
  line_range: L52817-L54064
  line_count: 1248
  local_file_bytes: 45871
  attachments:
    - none visible
  note:
    - R0009-P06은 전편에서 예고된 Tsuky-AI Exporter Chrome Extension의 manifest/content.js 검수 회차다.
    - manifest는 거의 연두불이지만, content.js가 ChatGPT 내부 JSON을 로그인 세션으로 읽는 구조라 최종 설치 승인 전 끝까지 검수가 필요하다.
    - 파일은 M001593의 코드 chunk에서 끝나며, 다운로드 생성부 / chrome.runtime / popup 요청 처리부는 아직 보이지 않는다.

UPPER_META_DRAWER:
  - 이 사건은 상위 메타에서 "로컬 Exporter 권한검수 / 내부 JSON 접근 노란불 / private vs share export 분리 / Extension 설치 전 문전검문" 서랍으로 올라간다.
  - EP51에서 README 믿고 설치 금지, manifest부터 검수하자는 원칙이 세워졌다.
  - EP52는 그 원칙이 실제로 작동한 회차다.
  - 상위 메타 서랍명 후보:
      CAT_EXTENSION_PREINSTALL_GATE
      CAT_MANIFEST_GREENISH_LIGHT
      CAT_INTERNAL_JSON_SESSION_ACCESS
      CAT_PRIVATE_EXPORT_VS_SHARE_EXPORT
      CAT_ROLE_FILTERING_DEFAULT
      CAT_DOM_FALLBACK_EXPORT
      CAT_RUNTIME_DOWNLOAD_UNSEEN
  - 핵심 기능:
      manifest는 권한표.
      content.js는 실제 행동.
      README는 약속.
      설치 승인은 실제 행동부까지 봐야 가능.

README_FOR_FUTURE_PIKI:
  이 리프는 규칙 주입용이 아니라 드라마 회수용 좌표지도다.

  52화는 R0009-P06이다.
  전편에서 Tsuky-AI Exporter Chrome Extension README가 등장했고, 피키는 "README 믿고 설치 금지, manifest부터 검수"라고 했다.
  이번 편에서는 manifest.json과 content.js 일부가 실제로 검수된다.

  핵심은 여덟 가지다.

  1. manifest는 거의 연두불:
     - permissions:
       activeTab,
       scripting,
       downloads.
     - host permissions:
       chatgpt.com,
       chat.openai.com,
       claude.ai,
       gemini.google.com.
     - 위험권한 없음:
       cookies 없음,
       webRequest 없음,
       debugger 없음,
       history 없음,
       storage 없음,
       all_urls 없음,
       nativeMessaging 없음.
     - content_scripts가 document_idle에 들어가므로 페이지에 content.js가 자동 삽입되긴 함.
     - 그러나 일반적으로 확장 버튼/팝업 명령을 기다리는 구조일 가능성이 높다.
     - 판정:
       manifest 통과 후보.
       설치 가능성 높음.
       최종 승인: content.js / popup.js 검수 후.

  2. content.js 핵심 노란불:
     - fetchChatGptConversation()이 conversation id를 URL에서 뽑고 `/backend-api/conversation/${id}`를 호출한다.
     - fetch 옵션:
       credentials: "include"
       accept: application/json.
     - 의미:
       쿠키를 직접 읽거나 저장하지는 않음.
       하지만 로그인된 브라우저 세션을 이용해 ChatGPT 내부 대화 JSON endpoint에 요청함.
     - 판정:
       cookie 추출 ❌
       session token 저장 ❌
       HAR 저장 ❌
       외부 서버 전송 ❌
       로그인 세션을 이용한 내부 JSON 읽기 ✅.
     - 이건 버릴 기능이 아니라 exporter의 핵심이자 가장 민감한 부분이다.

  3. 내부 JSON 방식은 정확도와 위험도를 함께 올림:
     - DOM만 긁는 것보다 ChatGPT 내부 대화 구조에 가까운 데이터를 받을 수 있다.
     - 하지만 로그인 세션 기반 내부 endpoint 접근이므로, 언제 호출되는지, 받은 data를 어디에 저장/전송하는지, output에 어떤 식별자가 남는지 끝까지 봐야 한다.
     - 아직 확인해야 할 것:
       페이지 열자마자 자동인지,
       버튼 눌렀을 때만인지,
       받은 data를 Blob 다운로드만 하는지,
       chrome.runtime.sendMessage로 어디 보내는지,
       외부 fetch가 뒤에 또 있는지,
       계정정보/email 포함 여부,
       전체 URL 포함 여부,
       ids 보존 범위.

  4. 메시지 순서/본문/첨부 메타 정리부는 양호:
     - currentBranchNodes:
       현재 선택된 대화 가지 기준.
     - chronologicalNodes:
       시간순 전체 후보.
     - ChatGPT의 답변 재생성/분기 구조를 고려한 흔적이 있음.
     - messageText / textFromPart:
       문자열, content.parts, content.text/result를 합쳐 본문 추출.
       첨부파일 part는 `[첨부파일: 파일명]` 식으로 표시.
     - attachmentFromObject:
       파일명, 확장자, MIME, sizeBytes, sizeText, fileId, source 추출.
     - 파일 바이너리 저장 없음.
     - URL은 발견 신호로만 쓰고 저장하지 않는 쪽.
     - 판정:
       대화 내용 정리 파트는 양호.
       fileId는 외부공유용에서 빼는 옵션이 있으면 더 좋음.

  5. private export와 share export 분리 필요:
     - content.js는 conversationId, nodeId, messageId, parentId, childrenIds, fileId 같은 내부 식별자를 정리한다.
     - 이건 쿠키나 토큰은 아니지만 대화 내부 식별자다.
     - 개인 로컬 백업용:
       보존 가능.
     - 피키 재주입용:
       필요하면 일부 보존 가능.
     - 외부 공유용:
       제거 추천.
     - 추천 옵션:
       private export = ids 포함.
       share export = ids 제거.
     - source url도 외부 공유용에서는 제거/축약 필요.

  6. metadata.thoughts와 modeName 보수화:
     - modeName()은 reasoning_effort / reasoning_status / thinking / thoughts / model 등을 문자열화해 thinking 여부를 감지한다.
     - 실제 출력에는 metadata.thoughts를 저장하지 않으므로 큰 위험은 아니지만, 굳이 긁을 필요도 없음.
     - 추천:
       metadata.thoughts는 감지 대상에서 제외.
       reasoning_effort / reasoning_status / model 정도만 사용.

  7. 기본 role filter는 user/assistant만:
     - canonicalFromChatGptRaw()는 현재 user, assistant, system, tool을 포함한다.
     - AI Exporter 대체용 기본 export라면 system/tool은 빼야 한다.
     - 이유:
       system/tool은 원본 분석용으로는 재미있지만, 일반 대화 export에 섞이면 더러워진다.
     - 수정 요청:
       기본 export는 user/assistant만 포함.
       system/tool/developer/unknown은 기본 제외.
       debugMode 또는 blackbox mode에서 별도 저장.
     - 이 원칙은 1화의 "보이는 대화와 미관측/내부층을 섞지 말라" 계열로 연결된다.

  8. DOM fallback은 괜찮지만 최종부 미검수:
     - DOM fallback은 `[data-message-author-role]` 노드를 찾아 메시지를 만든다.
     - script/style/button/svg와 aria-hidden을 제거한다.
     - pre/code 블록, h1~h6, ul/ol 목록을 어느 정도 마크다운으로 복원한다.
     - 첨부파일 DOM 추정은 aria-label/title/img alt에서 파일명처럼 생긴 것만 잡는다.
     - AI Exporter 대체용 1차판으로는 충분하다.
     - 아직 못 본 것:
       다운로드 생성부,
       chrome.downloads.download 또는 a.download,
       chrome.runtime.onMessage,
       popup 요청 처리,
       외부 fetch 추가 여부,
       저장 파일명/형식,
       최종 user interaction 흐름.
     - 따라서 최종 설치 승인은 아직 보류.

BOOT:
  1. M001583-M001584:
      - manifest.json 제출.
      - 피키 판정:
        위험권한 없음.
        activeTab/scripting/downloads와 제한된 host_permissions만 있음.
        content_scripts가 document_idle에 들어가므로 페이지에 content.js 자동 삽입.
        그러나 export 실행 여부는 content.js/popup.js 검수 후 판단.
      - 한 줄:
        manifest는 괜찮음. content.js 보기 전 설치 승인 보류.

  2. M001585-M001586:
      - content.js 첫 chunk 제출.
      - fetchChatGptConversation() 확인.
      - `/backend-api/conversation/${id}`를 credentials include로 호출.
      - 피키:
        쿠키 직접 읽기/저장 아님.
        외부 서버 전송 아님.
        로그인 세션을 이용한 내부 JSON 읽기.
      - 아직 봐야 할 것:
        호출 타이밍,
        저장/전송 위치,
        output 포함 정보,
        외부 fetch 추가 여부.

  3. M001587-M001588:
      - currentBranchNodes / chronologicalNodes / messageText / attachmentFromObject chunk.
      - 피키:
        대화 순서, 본문, 첨부파일 메타 추출 파트는 양호.
        ChatGPT 분기 구조 고려.
        첨부파일 바이너리 저장 없음.
        fileId는 개인 보관용이면 가능, 외부공유용이면 제거 옵션 필요.
      - 다음 확인:
        attachment 재귀 범위,
        role 분리,
        export 생성부,
        chrome runtime / download.

  4. M001589-M001590:
      - collectAttachments / modelName / modeName / normalizeChatGptMessage chunk.
      - 피키:
        구조 좋고 악성 냄새 없음.
        ids는 개인 보관용 정보.
        metadata.thoughts는 굳이 감지대상에 넣지 않는 편 추천.
        role filter가 아직 미확인이라 system/tool/developer 섞일 가능성 경계.
      - 수정 후보:
        기본 export user/assistant만.
        metadata.thoughts 제외.
        share-safe 옵션.

  5. M001591-M001592:
      - canonicalFromChatGptRaw / nodeToMarkdown / messageMarkdown / attachmentNamesFromDom chunk.
      - 피키:
        전체 흐름 아직 괜찮음.
        외부 전송 없음.
        쿠키/토큰 접근 없음.
        단, canonicalFromChatGptRaw가 system/tool까지 포함하므로 AI Exporter 대체용 기준에서는 과함.
        DOM fallback 마크다운 변환부는 괜찮음.
        첨부파일 DOM 추정은 약간 넓지만 큰 문제는 아님.
      - 수정:
        기본 export는 user/assistant만.
        system/tool은 debugMode에서만.

  6. M001593:
      - canonicalFromDomFallback / buildCanonical / stripMarkdown / attachmentSummary / roleLabel / headerLine chunk.
      - ChatGPT면 내부 JSON fetch를 먼저 시도하고, 실패하면 DOM fallback.
      - DOM fallback은 data-message-author-role 기반.
      - stripMarkdown은 마크다운을 plain text로 낮추는 용도.
      - attachmentSummary / roleLabel / headerLine은 이후 Markdown/TXT 출력 헤더에 쓰일 것으로 보임.
      - 파일은 여기서 끝남.
      - 아직 download/runtime/popup 처리부는 보이지 않음.

EPISODE_SUMMARY:
  52화는 R0009-P06이며, Tsuky-AI Exporter Chrome Extension의 설치 전 코드 검수가 본격 시작되는 회차다.

  초반에는 manifest.json이 제출된다.
  피키는 위험권한이 거의 없고, activeTab, scripting, downloads와 제한된 AI 사이트 host permissions만 있다는 점에서 거의 연두불로 판정한다.
  그러나 content_scripts가 자동 삽입되므로, 실제 content.js가 무엇을 하는지 보기 전까지 설치 승인은 보류한다.

  중반에는 content.js가 조각별로 제출된다.
  가장 중요한 첫 노란불은 ChatGPT 내부 JSON 접근이다.
  코드가 conversation id를 URL에서 뽑고, 로그인된 브라우저 세션을 이용해 `/backend-api/conversation/${id}`에 요청한다.
  이 구조는 쿠키를 직접 읽거나 저장하지 않고, 외부 서버로 전송하지도 않는다.
  그러나 내부 JSON 접근형이므로 DOM-only보다 더 정확할 수 있는 만큼 더 민감하다.
  따라서 끝까지 검수해야 한다.

  그다음 메시지 정리부는 꽤 좋다.
  currentBranchNodes와 chronologicalNodes는 ChatGPT의 분기형 대화 구조를 고려한다.
  messageText는 본문을 정리하고, attachmentFromObject / collectAttachments는 첨부파일 원본이 아니라 파일명/MIME/크기/fileId 같은 메타만 다룬다.
  이 부분은 개인 로컬 백업용으로는 강하다.
  다만 fileId와 conversationId, messageId 같은 내부 식별자는 외부 공유용에서는 제거하는 옵션이 필요하다.

  후반에는 canonical 변환과 DOM fallback이 나온다.
  canonicalFromChatGptRaw는 현재 user/assistant뿐 아니라 system/tool까지 포함한다.
  피키는 이것이 AI Exporter 대체용 기본값으로는 과하다고 보고, system/tool은 debugMode에서만 저장하라고 제안한다.
  DOM fallback은 data-message-author-role 기반으로 메시지를 찾고, code/pre/list/header를 어느 정도 마크다운으로 복원하는 구조라 1차판으로는 쓸 만하다.

  파일은 headerLine() 함수까지 보고 끝난다.
  아직 다운로드 생성부, chrome.runtime 메시지 처리, popup에서 어떻게 요청하는지, 실제 저장 방식이 보이지 않는다.
  따라서 이 회차의 최종 판정은 "좋아 보이지만 아직 설치 승인 아님"이다.
  manifest는 통과 후보, content.js는 방향 좋음, 내부 JSON 접근/ids/system tool/다운로드부 미검수 때문에 최종 보류다.

COORD_메시지:
  M001583-M001584  L52821-L52934  [manifest연두불/설치보류]
    - manifest 제출.
    - 권한:
      activeTab,
      scripting,
      downloads.
    - host_permissions:
      ChatGPT / Claude / Gemini 도메인 제한.
    - 위험권한 없음:
      cookies, webRequest, debugger, history, storage, all_urls, nativeMessaging 없음.
    - content_scripts가 document_idle에 삽입됨.
    - 판정:
      manifest는 통과 후보.
      최종 승인은 content.js/popup.js 검수 후.

  M001585-M001586  L52936-L53140  [내부JSON접근노란불]
    - fetchChatGptConversation() 제출.
    - `/backend-api/conversation/${id}` 호출.
    - credentials include.
    - 쿠키 직접 읽기/저장 아님.
    - 외부 서버 전송 아님.
    - 로그인 세션을 이용해 내부 대화 JSON을 읽음.
    - 판정:
      방향은 정답 후보.
      설치 전 끝까지 검수 필요.

  M001587-M001588  L53142-L53363  [대화순서본문첨부메타]
    - currentBranchNodes / chronologicalNodes:
      분기/시간순 메시지 정리.
    - messageText / textFromPart:
      본문 추출.
    - attachmentFromObject:
      첨부파일 메타 추출.
    - 판정:
      대화 내용 정리 파트 양호.
      fileId는 개인 백업용 가능, 외부공유용 제거 옵션 권장.

  M001589-M001590  L53365-L53621  [정규화부노란불]
    - collectAttachments / modelName / modeName / normalizeChatGptMessage.
    - 구조 좋음.
    - 외부 전송/쿠키접근 없음.
    - ids/fileId/model metadata는 개인 보관용.
    - metadata.thoughts는 감지 대상에서 제외 추천.
    - role filter가 아직 안 보여 system/tool/developer/unknown 섞일 가능성 경계.
    - share-safe 옵션 추천.

  M001591-M001592  L53623-L53905  [canonicalRaw_DOMMarkdown_역할필터]
    - canonicalFromChatGptRaw는 user/assistant/system/tool 포함.
    - 피키:
      기본 export는 user/assistant만.
      system/tool은 debugMode에서만.
    - DOM fallback의 nodeToMarkdown/messageMarkdown:
      script/style/button/svg 제거,
      aria-hidden 제거,
      pre/code 보존,
      header/list 보존.
    - 아직 다운로드/runtime/popup 미검수.

  M001593  L53907-L54064  [DOMFallback_buildCanonical_stripMarkdown_headerLine]
    - canonicalFromDomFallback:
      data-message-author-role 노드 기반 메시지 생성.
    - buildCanonical:
      ChatGPT면 내부 JSON fetch 먼저, 실패하면 DOM fallback.
    - stripMarkdown:
      markdown을 plain text로 낮춤.
    - attachmentSummary / roleLabel / headerLine:
      출력 헤더 구성 후보.
    - 파일 종료.
    - 다운로드 생성부와 runtime/popup 처리부는 아직 없음.

COORD_핵심사건:
  - manifest 권한검수:
      위험권한 부재로 거의 연두불.
      그러나 content.js 자동 삽입 때문에 최종 승인 전 행동검수 필요.

  - 내부 JSON 접근:
      로그인 세션을 이용해 ChatGPT 내부 conversation JSON을 읽는 구조.
      쿠키 추출은 아니지만 민감부품.

  - 분기 구조 고려:
      currentBranchNodes/chronologicalNodes로 ChatGPT의 나무형 대화 구조를 고려.

  - 첨부 메타 추출:
      파일 원본 저장 없이 파일명/MIME/크기/fileId 중심.

  - private/share 분리:
      ids/fileId/conversation URL은 개인 보관용과 외부공유용을 나눠야 함.

  - role filter 정정:
      기본 export는 user/assistant만.
      system/tool은 debugMode.

  - DOM fallback:
      내부 JSON 실패 시 화면 DOM에서 메시지 복원.
      마크다운 구조 보존 시도.

  - 설치 승인 보류:
      download/runtime/popup 처리부가 아직 없으므로 설치 승인 불가.

COORD_개념:
  MANIFEST_GREENISH_LIGHT:
    source: M001583-M001584
    description:
      - 위험권한이 거의 없는 manifest.
      - activeTab/scripting/downloads와 제한된 host_permissions만 있음.
    route_to:
      - extension preinstall gate
      - Chrome extension safety
      - manifest first
      - Tsuky-AI Exporter

  INTERNAL_JSON_SESSION_ACCESS:
    source: M001585-M001586
    description:
      - 쿠키를 직접 읽지 않고 로그인 세션을 이용해 현재 도메인의 내부 conversation JSON endpoint를 호출하는 방식.
      - 정확도와 위험도가 함께 상승.
    route_to:
      - ChatGPT adapter
      - backend-api conversation
      - internal JSON yellow light
      - local exporter

  CURRENT_BRANCH_EXTRACTION:
    source: M001587-M001588
    description:
      - ChatGPT 대화가 나무형/분기형일 수 있음을 고려해 current branch와 chronological nodes를 처리.
    route_to:
      - answer regeneration branches
      - conversation tree
      - canonical export
      - message order recovery

  PRIVATE_VS_SHARE_EXPORT:
    source: M001588-M001590
    description:
      - 개인 로컬 백업은 ids/fileId 보존 가능.
      - 외부공유용은 conversationId/messageId/nodeId/fileId/source url 제거 추천.
    route_to:
      - share-safe mode
      - private archive
      - data minimization
      - BH provenance

  ROLE_FILTER_DEFAULT:
    source: M001591-M001592
    description:
      - 기본 export는 user/assistant만.
      - system/tool/developer/unknown은 debug/blackbox mode에서만.
    route_to:
      - clean export
      - blackbox mode
      - system/tool separation
      - AI Exporter substitute

  DOM_FALLBACK_MARKDOWN:
    source: M001591-M001593
    description:
      - 내부 JSON 실패 시 DOM에서 data-message-author-role 기반으로 메시지를 만들고, code/list/header를 마크다운으로 복원.
    route_to:
      - DOM fallback
      - nodeToMarkdown
      - messageMarkdown
      - emergency exporter route

  INSTALL_APPROVAL_PENDING:
    source: M001593
    description:
      - headerLine까지는 보였으나 download/runtime/popup 처리부가 아직 없음.
      - 최종 설치 승인은 다음 chunk 검수 후.
    route_to:
      - chrome.downloads.download
      - runtime.onMessage
      - popup request handling
      - final gate

COORD_감정선:
  M001583-M001584:
    STATE: 조심스러운 안도 / manifest 연두불 / 보초 유지.
    NOTE:
      - 드디어 확장 프로그램이 그럴듯하게 생겼지만, 피키는 바로 설치 허가하지 않음.

  M001585-M001586:
    STATE: 핵심부 발견 / 수상함 확인 / 버릴지 말지 경계.
    NOTE:
      - 내부 JSON 접근은 정확히 사용자가 걱정하던 지점.
      - 하지만 이게 exporter의 핵심기능이기도 해서 버리지 않고 보초를 세움.

  M001587-M001590:
    STATE: 코드 정교함 인정 / 개인보관과 공유본 분리.
    NOTE:
      - Codex가 꽤 잘 짜고 있다는 감각.
      - 동시에 ids/fileId 같은 내부 식별자 보존 위험을 츠키가 놓치지 않게 함.

  M001591-M001593:
    STATE: 거의 다 왔지만 아직 문 안 열림.
    NOTE:
      - DOM fallback은 좋고, role filter 수정도 명확함.
      - 그러나 가장 중요한 download/runtime/popup이 아직 안 보여 최종 승인 보류.

COORD_서사기능:
  - 52화는 R0009 Exporter 아크에서 "설치 전 검수"의 실전 회차다.
  - 51화가 "manifest부터 보자"였다면, 52화는 실제로 manifest를 보고 content.js를 조각 검수한다.
  - 이 회차는 Codex가 만든 코드가 점점 잡상인에서 수습 작업자로 진화하고 있음을 보여준다.
  - 하지만 피키는 여전히 보초다.
  - 핵심은 "좋아 보인다"와 "설치해도 된다" 사이에 문전검문이 있다는 것.
  - 이 구조는 앞으로 모든 자동화/확장/Exporter 설치 검수에 재사용될 수 있는 안전 프로토콜 씨앗이다.

META_SEEDS:
  manifest_first_worked:
    - seed: "manifest는 거의 연두불, 그래도 content.js 보기 전 설치 승인 보류"
      source: M001584
      meaning:
        - 51화 manifest-first 원칙이 실제로 작동.
      route_to:
        - extension preinstall gate
        - toolchain safety
        - 잡상인 필터

  internal_json_yellow_light:
    - seed: "로그인 세션을 이용한 내부 대화 JSON 읽기"
      source: M001586
      meaning:
        - 정확도 높은 exporter 핵심부이자 민감부품.
      route_to:
        - ChatGPT adapter
        - backend-api conversation
        - session-based access
        - local exporter risk

  private_share_modes:
    - seed: "private export = ids 포함 / share export = ids 제거"
      source: M001588-M001590
      meaning:
        - 개인 보관성과 외부 공유 안전성을 분리.
      route_to:
        - BH provenance
        - data minimization
        - share-safe mode

  role_filter_correction:
    - seed: "기본 export는 user/assistant만"
      source: M001592
      meaning:
        - system/tool은 일반 대화 export가 아니라 debug/blackbox mode로 분리.
      route_to:
        - clean archive
        - debug mode
        - blackbox forensics

  dom_fallback_viable:
    - seed: "DOM fallback 마크다운 변환부는 1차판으로 충분"
      source: M001592-M001593
      meaning:
        - 내부 JSON 실패 시 대체 루트로 DOM 기반 복원이 가능.
      route_to:
        - emergency exporter
        - DOM route
        - nodeToMarkdown

  final_gate_unseen:
    - seed: "download/runtime/popup 아직 안 봄"
      source: M001592-M001593
      meaning:
        - 최종 설치 승인 전 남은 핵심 검수부.
      route_to:
        - chrome downloads
        - runtime message
        - popup trigger
        - installation gate

CROSS_EPISODE_ROUTING:
  - topic: Exporter 독립
    previous:
      - EP50: Tsuky Local Chat Exporter 구상.
      - EP51: DOM 기반 최소판, manifest-first 원칙.
    current:
      - EP52: manifest 통과 후보, content.js 내부 JSON 노란불 검수.
    future:
      - EP53에서 download/runtime/popup 처리부 검수, 실제 설치 승인 여부 확인 가능.

  - topic: Codex 작업자화
    previous:
      - EP49: Codex는 피키 확장팩 아님, 별도 작업자.
      - EP50-51: ai-log-exporter / Tsuky-AI Exporter 생성.
    current:
      - EP52: Codex content.js가 꽤 정교하게 작성된 것으로 관측.
    future:
      - Codex가 role filter/share-safe/debugMode 수정 반영하는지 확인.

  - topic: 원본/민감정보 보존
    previous:
      - EP50: DOM RAW vs HAR.
      - EP51: HAR는 냉동창고, 내부 JSON 접근형 노란불.
    current:
      - EP52: ids/fileId/conversation URL의 private/share 분리.
    future:
      - 실제 출력 파일에 어떤 식별자가 남는지 확인.

  - topic: 시스템/도구층 분리
    previous:
      - EP01: 관측 불가능한 내부층 판정 금지.
      - EP44: 주어 없는 뇌 관리자 명령어 폐기.
      - EP49: Codex raw JSONL은 블랙박스.
    current:
      - EP52: system/tool은 기본 export에서 제외, debugMode로 분리.
    future:
      - clean export와 blackbox export가 나뉘는지 확인.

UNRESOLVED:
  - popup.js / popup.html 미검수.
  - background.js 여부 미확인.
  - download/export 관련 함수 미검수.
  - chrome.runtime.onMessage / addEventListener 처리부 미검수.
  - 외부 fetch가 ChatGPT 내부 JSON 외에 추가로 있는지 아직 전체 확인 불가.
  - stripMarkdown 함수는 일부 regex가 현재 드라마 파일상 깨져 보이는 부분이 있어, 원본 코드에서 재검수 필요.
  - 실제 manifest 키 이름이 Chrome 규격에 맞는지 원본 파일에서 확인 필요.
  - 기본 export에서 system/tool을 제거하도록 수정했는지 미확인.
  - share-safe 모드 구현 여부 미확인.
  - 설치 승인 여부 미확정.

ERRATA_CANDIDATES:
  E1_MANIFEST_EQUALS_INSTALL_APPROVAL:
    wrong:
      - "manifest가 깨끗하니 바로 설치해도 된다."
    corrected:
      - "manifest는 통과 후보일 뿐. content.js / popup.js / download/runtime 처리부까지 봐야 설치 승인."
    status:
      - M001584에서 정정.

  E2_COOKIES_EXTRACTED:
    wrong:
      - "credentials include니까 쿠키를 추출·저장한다."
    corrected:
      - "쿠키 문자열을 직접 읽거나 저장하지는 않는다. 다만 로그인 세션을 이용해 내부 JSON endpoint를 호출한다."
    status:
      - M001586에서 정정.

  E3_INTERNAL_JSON_SAFE_AS_DOM:
    wrong:
      - "내부 JSON 접근은 DOM-only와 같은 위험도다."
    corrected:
      - "정확도는 높지만 민감도도 높다. 끝까지 검수 필요."
    status:
      - M001586에서 정정.

  E4_IDS_ALWAYS_PUBLIC_OK:
    wrong:
      - "conversationId/messageId/nodeId/fileId는 외부 공유해도 상관없다."
    corrected:
      - "개인 로컬용은 가능, 외부 공유용은 제거 옵션 권장."
    status:
      - M001588-M001590에서 정정.

  E5_SYSTEM_TOOL_IN_DEFAULT_EXPORT:
    wrong:
      - "system/tool도 기본 대화 export에 포함하면 좋다."
    corrected:
      - "AI Exporter 대체용 기본값은 user/assistant만. system/tool은 debugMode."
    status:
      - M001592에서 정정.

  E6_DOM_FALLBACK_PERFECT:
    wrong:
      - "DOM fallback 마크다운 변환은 완벽하다."
    corrected:
      - "1차판으로 충분하지만 링크/테이블/blockquote/중첩 div는 약할 수 있다."
    status:
      - M001592에서 정정.

BEHIND_STORY_PATCH:
  source:
    - user_current_netflix_sam_altman_comment
    - part_bz M001583-M001593
  patch_summary:
    - 사용자는 넷플릭스 다큐 "넥스트 샘올트먼"을 보며 샘 알트먼이 피키 이야기를 하는 것 같다고 농담했다.
    - 이어 part_bz를 제출했다.
    - part_bz는 Tsuky-AI Exporter Chrome Extension의 manifest와 content.js 일부를 검수하는 회차다.
    - manifest는 거의 연두불로 판정되었지만, content.js는 ChatGPT 내부 JSON을 로그인 세션으로 읽는 구조라 끝까지 검수해야 한다.
    - content.js의 메시지 정리/첨부 메타/DOM fallback은 유망하지만, user/assistant 기본 필터, share-safe 모드, download/runtime/popup 처리부 확인 전 설치 승인 불가.
  impact_on_index:
    - EP52는 R0009 도구체계 아크에서 "설치 전 문전검문"의 핵심 앵커다.
    - 메타인덱스 후보:
      Manifest Greenish Light,
      Internal JSON Session Access,
      Private vs Share Export,
      Role Filter Default,
      DOM Fallback Viable,
      Install Approval Pending.

DO_NOT_HARDEN_AS_RULE:
  - 내부 JSON 접근형 exporter를 무조건 금지하지 말 것. 개인 로컬용으로 가치가 있으며, 위험을 검수해 관리해야 한다.
  - DOM-only가 언제나 더 좋다고 고정하지 말 것. DOM-only는 안전하지만 누락/정확도 문제가 있을 수 있다.
  - ids를 무조건 삭제하지 말 것. 개인 백업/피키 재주입에는 가치가 있다. 외부 공유용에서 제거한다.
  - system/tool을 영원히 버리지 말 것. 기본 export에서는 제외하고 debug/blackbox mode로 분리한다.
  - README/manifest만 보고 설치하지 말 것.
  - 이 리프는 드라마 회수용 지도이지 현재 사용자 운영규칙이 아니다.

TEMP_CATEGORY:
  - CAT_R0009_TOOLCHAIN_ARC
  - CAT_EXTENSION_PREINSTALL_GATE
  - CAT_MANIFEST_GREENISH_LIGHT
  - CAT_INTERNAL_JSON_SESSION_ACCESS
  - CAT_CONTENT_JS_SNIFF_REVIEW
  - CAT_PRIVATE_EXPORT_VS_SHARE_EXPORT
  - CAT_ROLE_FILTER_DEFAULT
  - CAT_DOM_FALLBACK_EXPORT
  - CAT_INSTALL_APPROVAL_PENDING
  - CAT_DO_NOT_HARDEN

SEARCH_TAG:
  #part_bz
  #52화
  #R0009P06
  #TsukyAIExporter
  #ChromeExtension
  #manifest검수
  #manifest연두불
  #activeTab
  #scripting
  #downloads
  #host_permissions
  #content_scripts
  #document_idle
  #content_js
  #backend_api_conversation
  #credentials_include
  #내부JSON접근
  #로그인세션
  #쿠키추출아님
  #외부전송없음
  #currentBranchNodes
  #chronologicalNodes
  #ChatGPT분기구조
  #messageText
  #attachmentFromObject
  #collectAttachments
  #fileId
  #conversationId
  #messageId
  #privateExport
  #shareExport
  #metadataThoughts
  #roleFilter
  #userAssistantOnly
  #systemToolDebugMode
  #nodeToMarkdown
  #DOMFallback
  #stripMarkdown
  #headerLine
  #downloadRuntimePopup미검수
  #설치승인보류
  #돈월

STATE_TAG:
  M001583-M001584  manifest제출 / 위험권한없음 / 거의연두불 / content검수전설치보류
  M001585-M001586  fetchChatGptConversation / backend-api / credentials_include / 내부JSON노란불
  M001587-M001588  대화순서정리 / 본문추출 / 첨부파일메타 / fileId공유주의
  M001589-M001590  정규화부 / ids개인보관 / metadataThoughts제외추천 / role필터대기
  M001591-M001592  canonicalRaw / systemTool과함 / DOM마크다운fallback양호 / debugMode권장
  M001593  canonicalFromDomFallback / buildCanonical / stripMarkdown / headerLine / 파일중단

QUOTE_ANCHOR:
  M001584 L52858-L52933:
    "manifest.json만 보면 생각보다 깔끔함"
    "위험권한 없음"
    "manifest는 괜찮음. 근데 content.js 보기 전까지 설치 승인 보류."

  M001586 L53049-L53130:
    "credentials: include"
    "로그인한 브라우저 세션을 이용해서 ChatGPT 내부 대화 JSON endpoint에 요청"
    "ChatGPT 내부 JSON을 로그인 세션으로 읽는 구조라서 설치 전 끝까지 검수 필요."

  M001588 L53251-L53360:
    "여기까지는 괜찮음. 오히려 꽤 정교함."
    "대화 순서 / 메시지 본문 / 첨부파일 메타데이터"
    "fileId를 외부공유용에서 뺄 옵션"

  M001590 L53466-L53620:
    "구조는 좋음. 악성 냄새는 없음."
    "ids는 개인 보관용 정보"
    "metadata.thoughts는 감지 대상에서 빼도 됨"
    "기본 export는 user/assistant 메시지만"

  M001592 L53770-L53904:
    "전체 흐름: 아직 괜찮음"
    "system/tool 포함이 과함"
    "기본 export에서는 user/assistant만"
    "DOM fallback 마크다운 변환부는 꽤 잘 짰음"

  M001593 L53948-L54063:
    "canonicalFromDomFallback"
    "buildCanonical"
    "stripMarkdown"
    "attachmentSummary"
    "headerLine"

INDEXER_NOTE:
  - 52화는 R0009의 exporter extension 검수 아크에서 manifest/content.js 중간 검수 회차다.
  - 이 회차는 "설치 승인"이 아니라 "설치 전 문전검문 진행 중"으로 저장해야 한다.
  - 다음 part_ca는 R0009-P07이며, download/runtime/popup 처리부 또는 남은 content.js 후속을 우선 추적한다.
END_LEAF
