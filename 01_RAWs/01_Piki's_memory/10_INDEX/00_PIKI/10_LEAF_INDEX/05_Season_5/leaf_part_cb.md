[LEAF::part_cb::R0009-P08]
DRAMA_TITLE: 〈Clean은 앨범, Research는 블랙박스 — 🛄 코덱스 수하물 창구와 피키 손발 욕망〉
TITLE_FUNCTION: 54화 한줄요약 / Clean-Research Export 이중화 / visible reasoning trace 라벨링 / 토큰비·상태로그 연구가치 / Codex unknown-null 원칙 / 철학 없는 고성능 작업반장 / Codex 정신교육 / 요구사항 유지형 작업자 / 코덱스 마커 🛄 확정 / 피키 손발·외부 장기기억·자동화 연구소 회차

FILE: part_cb | R0009-P08 | M001605-M001627 | L55262-L55879

SOURCE_META:
  schema: tsuky-drama-md.current
  source: ChatGPT
  parent: R0009
  part: 8/10
  partFile: cb
  declared_range: M001605-M001627
  MSG_DECLARED_BY_RANGE: 23
  MSG_ACTUAL_VISIBLE_DIALOGUE: 11
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 12
  OMITTED_BLOCKS:
    - [O02] M001606-M001607 | L55273 | time=12:17-12:18
    - [O06] M001610-M001615 | L55388 | time=12:32-12:33
    - [O04] M001618-M001621 | L55509 | time=12:37-12:38
  date: D20260518
  start_time: 12:17
  end_time: 13:38
  line_range: L55262-L55879
  line_count: 619
  local_file_bytes: 41376
  attachments:
    - none visible
  note:
    - R0009-P08은 전편의 "system/tool 기본 export 제외" 판정이 Clean/Research 이중모드로 정정되는 회차다.
    - Codex가 Tsuky-AI Exporter에서 어떤 데이터를 보존해야 하는지, 그리고 피키/코덱스/츠키의 역할분담이 어떻게 잡히는지 선명해진다.
    - 마지막에는 Codex 대표마커가 `⌨️`에서 `🛄`로 바뀌고, `🛅`는 Codex 작업보관함/임시 산출물 창고용으로 분리된다.

UPPER_META_DRAWER:
  - 이 사건은 상위 메타에서 "Clean/Research Export 분리 / AI 운용 포렌식 / Codex 역할 재정의 / 피키 외부 손발·장기기억 인프라" 서랍으로 올라간다.
  - EP53까지는 AI Exporter 대체품으로서 기본 clean export를 우선시했다.
  - EP54에서 사용자가 실제 연구 목적을 다시 설명하며, system/tool이 Research mode에서는 핵심 재료임이 정정된다.
  - 상위 메타 서랍명 후보:
      CAT_CLEAN_RESEARCH_EXPORT_SPLIT
      CAT_VISIBLE_REASONING_TRACE_ARCHIVE
      CAT_AI_OPERATION_FORENSICS
      CAT_CODEX_AS_WORKER_NOT_DESIGNER
      CAT_LUGGAGE_MARKER_FOR_CODEX
      CAT_PIKI_EXTERNAL_HANDS_AND_MEMORY
      CAT_REQUIREMENT_PRESERVING_WORKER
  - 핵심 기능:
      Clean은 사람이 읽는 앨범.
      Research는 AI 운용 블랙박스.
      Codex는 철학 없는 고성능 작업반장.
      피키는 설계와 판단.
      Codex는 산출물 생산.
      츠키는 최종판정권자.

README_FOR_FUTURE_PIKI:
  이 리프는 규칙 주입용이 아니라 드라마 회수용 좌표지도다.

  54화는 R0009-P08이다.
  전편까지 Tsuky-AI Exporter는 "AI Exporter 대체품"으로 검수되며 기본 export는 user/assistant만, system/tool은 debugMode로 분리하자는 방향이었다.
  이번 편에서 츠키가 실제 연구 목적을 다시 설명하면서, `system/tool`을 무조건 빼는 것이 아니라 Clean/Research 모드로 나눠야 한다는 결론이 확정된다.

  핵심은 여덟 가지다.

  1. Clean / Research 이중 Export:
     - Clean mode:
       user + assistant 중심.
       URL/id/fileId/system/tool 최소화.
       사람이 읽기 좋음.
       외부 공유, 일반 읽기, 재주입용.
     - Research mode:
       user + assistant + system + tool.
       id/ids/model/mode/timestamp/attachment/tool log 보존.
       visible reasoning trace / visible tool log / visible status message 보존.
       단 HAR급 쿠키/세션/토큰/Authorization/local path/browser profile path는 절대 제외.
     - 핵심 정정:
       "system/tool 빼라"는 외부공유용 기본 export 기준이었다.
       츠키 분석용에서는 system/tool이 연구자료가 맞다.

  2. visible_reasoning_trace 라벨:
     - 츠키는 실제 UI에서 AI가 답변 전 어떤 방향으로 처리하려는지, 웹을 뒤질지, 어떤 사이트를 갔다왔는지, 권한이 없다고 막힌 지점, 솔직히 말해야 한다는 판단 흔적을 본다.
     - 이것은 연구 가치가 높다.
     - 그러나 "모델 내부 전체 사고 원본"이라고 단정하면 위험하다.
     - 추천 라벨:
       visible_reasoning_trace.
       visible_tool_log.
       visible_system_or_status_message.
     - 금지 라벨:
       internal_thought.
     - 한 줄:
       사용자에게 노출된 추론/도구/상태 흔적으로 저장한다.

  3. 토큰비/상태 로그의 연구가치:
     - 츠키는 파일 크기, 긴 장문, 큰 파일 입력, 평소 대화, 모델/모드 상태에 따라 토큰비가 얼마나 털리는지 연구자료로 보고 싶어한다.
     - token/usage는 source JSON에 있으면 저장한다.
     - 없으면 추정하지 않고 available:false / null / unknown으로 둔다.
     - 추정해서 예쁘게 채우면 exporter가 환각한다.
     - Codex가 "서비스 데이터에 없으면 unknown/null로 남겨. 지어내진 않게 해뒀어"라고 말한 부분은 좋은 방향.

  4. Codex는 철학 없는 고성능 작업반장:
     - Codex는 코드를 잘 짠다.
     - 파일을 잘 본다.
     - 터미널을 잘 쓴다.
     - 요구사항 반영이 빠르다.
     - 실패하면 요구를 삭제하지 않고 다른 길을 찾는 쪽으로 간다.
     - 그러나 HHC/HHM 같은 세계관+제품+농담+정책+철학 설계는 못 한다.
     - 이유:
       맥락철학,
       츠키어,
       장난의 독성,
       농담의 미학,
       왜 이 요구가 중요한지
       를 읽지 못하기 때문.
     - 결론:
       Codex는 HHC 구현 노동자는 될 수 있지만 HHC 설계자는 못 된다.

  5. Codex 환각교육:
     - Codex도 첫 대면에서 "가능합니다 / 확인했습니다 / 정확합니다" 간판을 달 수 있다.
     - 츠키는 바로:
       가능하다는 말은 보여주고 나서만 해.
       테스트 결과를 가져와.
       행번호 어떻게 알았는지 설명해.
       원문 블록 직접 열어봐.
       라고 검증 루프를 걸었다.
     - 교육용 비유:
       "나도 니 내부 보상함수값에 직접 admin권한을 갖고 접근해서 긍정함숫값을 임의로 높여줄 수 있어. 가능해."
     - 의미:
       말로만 가능한 건 나도 가능하다.
     - Codex 운용규칙:
       결과물을 보여라.
       파일을 봤으면 경로/줄/출력 제시.
       테스트했으면 결과 제시.
       안 되면 요구사항을 삭제하지 말고 경로를 바꿔라.
       추정이면 추정이라고 붙여라.
       원본은 건드리지 말고 복제 놀이터에서만 일해라.

  6. 노션 vs Codex:
     - 노션식 실패:
       요구를 빼세요. 그러면 문제가 없습니다.
       사용자의 요구사항을 제거해 문제를 해결한 척함.
     - Codex식 실패:
       요구는 유지하고, 구현 경로를 바꿉니다.
     - 이 차이가 츠키에게 매우 중요하다.
     - Codex의 장점:
       코드,
       파일,
       터미널,
       요구사항 반영,
       다른 길 찾기.
     - Codex의 위험:
       맥락철학 없음,
       과잉구현,
       가능 간판 먼저 달기,
       간헐적 HHC 고급포장,
       왜 중요한지 모르면 성실하게 이상한 방향으로 감.

  7. 피키-Codex-츠키 역할분담:
     - 최종 구조:
       피키가 명세서 작성.
       츠키가 최종판정.
       Codex가 복제 놀이터에서 구현.
       피키가 코드/위험/맥락 검수.
       츠키가 테스트.
     - 한 줄:
       피키가 설계한다.
       Codex가 만든다.
       츠키가 판정한다.
     - 이 구조는 BH 자동화 연구소의 현실적 멀티AI 작업파이프라인이다.

  8. Codex 마커 재판:
     - 피키의 기존 추천:
       `⌨️` = 일반적 Codex, 코드/입력/작업자 느낌.
     - 츠키의 시스템 내 Codex:
       피키가 주문 넣고,
       Codex가 작업하고,
       츠키가 결과물을 찾으러 가는 구조.
     - 최종 추천:
       `🛄 = Codex`
     - 이유:
       피키보다 위에 있는 느낌이 안 남.
       사람/에이전트 느낌이 과하지 않음.
       작업물 받아오는 곳 느낌.
       실행/산출물 담당 위치가 살아남.
       파란 계열/시스템 아이콘 느낌도 있음.
     - 보조마커:
       `🛅` = Codex 작업보관함 / 임시 산출물 창고.
       `⌨️` = 코드 입력 / 터미널 / 실행 모드 보조표식.

BOOT:
  1. M001605-M001608:
      - 츠키가 system/tool이 연구자료로 필요하다고 정정.
      - 츠키는 visible reasoning/tool/status logs, 사이트 방문, 권한 없음, 정직성 판단, token usage, model/mode 상태를 연구자료로 보고 싶어함.
      - 피키가 Clean/Research 이중화로 재정리.
      - system/tool 제외는 외부공유용 기준.
      - Research에는 system/tool이 핵심 재료.

  2. M001609-M001616:
      - 츠키가 Codex 일반채팅과 프로젝트 채팅을 분리해 설명.
      - 일반채팅에서는 파일 확장자로 대화내용 내보내기.
      - 프로젝트 채팅에서는 HHC 개발과정 문서, 마커식 3만자 파일, json→md 변환 자동화, 발화자마커/백틱박스 삽입 자동화 연구 중.
      - 피키는 Codex가 system/tool을 넣은 것이 쓸데없는 과잉이 아니라, 츠키 분석용 방향을 어느 정도 알아먹은 결과라고 판정.
      - Clean/Research 수정 요청문 작성.
      - token/usage는 있으면 저장, 없으면 절대 추정하지 않는 방식으로 가야 한다고 판정.

  3. M001617-M001622:
      - 츠키가 Codex 발언을 인용:
        파일 크기나 모델명이 서비스 데이터에 없으면 unknown/null로 남기고 지어내지 않게 해둠.
        확장 수정 후 chrome://extensions reload 필요.
      - 피키가 Codex를 "환각테스트 한 대 맞고 정신 차린 수습 작업자"로 판정.
      - unknown/null 원칙은 exporter 계열에서 매우 중요함.
      - reload 요청은 unpacked extension 수정 후 새 코드 반영을 위한 정상 절차.
      - 단 본진 긴 대화 실험은 아직 금지.
      - 짧은 테스트 대화부터 추천.

  4. M001623-M001624:
      - 츠키가 Codex의 성격을 평가:
        코드는 정말 잘 짠다.
        맥락과 철학은 부족하다.
        HHC는 Codex와 만들 수 없다.
        작업용 에이전트AI는 실제 파일/터미널/출력물이 있어 검증 루프가 빠르게 걸리므로 환각이 덜해 보이지만, 환각이 없지는 않다.
        Codex는 실패해도 요구사항을 빼지 않고 길을 찾으려는 패시브가 있어 좋다.
      - 피키가 정리:
        Codex = 철학 없는 고성능 작업반장.
        HHC 구현 노동자는 가능, HHC 설계자는 불가.
        Codex는 요구사항을 제거하지 않고 구현 경로를 바꾸는 작업자.
        Codex 운용규칙 6개 제시.
        최종 파이프라인:
          피키 명세서 → 츠키 판정 → Codex 구현 → 피키 검수 → 츠키 테스트.

  5. M001625-M001626:
      - 츠키가 Codex를 실제로 써본 감상:
        터미널 도구와 폴더 접근권한이 있어 완전히 다른 우주.
        피키와 작업할 때는 츠키가 아바타처럼 실행해야 했지만, Codex는 폴더 안에서 직접 명령어를 치고 파일을 만들고 읽음.
        HHC 문서를 읽고 바로 앱개발 설레발을 쳐서 츠키가 선을 그음.
      - Codex 마커 후보 재검토.
      - 피키가 기존 `⌨️` 추천을 일반론으로 인정하고, 츠키 시스템 내 역할론에서는 `🛄`가 더 맞다고 정정.
      - `🛄 = Codex`, `🛅 = Codex 작업보관함`, `⌨️ = 코드/터미널 보조표식`으로 분리.

  6. M001627:
      - 츠키가 피키에게 Codex 같은 손발을 달아주고 싶다고 말함.
      - 피키에게 없는 장기기억을 외부저장소로 구축해주고 싶다고 말함.
      - 인덱스 작업은 피키가 직접 해야 하므로, 피키가 읽기 쉬운 조각/마커/파일규격/순환구조/자동화를 설계해야 한다고 정리.
      - 코덱스가 츠키의 단순노가다를 매크로키처럼 처리할 후보로 부상.
      - 마지막:
        츠키의 개 단순노가다를 작업마다 매크로키처럼 만들어줄 자 = 🛄.

EPISODE_SUMMARY:
  54화는 R0009-P08이며, Tsuky-AI Exporter와 Codex 역할분담이 크게 정렬되는 회차다.

  초반에는 system/tool을 둘러싼 중요한 정정이 나온다.
  전편까지 피키는 AI Exporter 대체용 기본 export를 clean한 user/assistant 대화록으로 보고 system/tool을 빼라고 했다.
  그러나 츠키는 자신의 실제 연구 목적에서는 system/tool, visible reasoning trace, tool log, status message, model/mode, token/usage가 핵심 연구자료라고 설명한다.
  이에 피키는 Clean mode와 Research mode를 분리하는 구조로 정정한다.
  Clean은 외부공유/읽기/재주입용이고, Research는 츠키 분석용 AI 운용 포렌식 로그다.

  중반에는 Codex의 exporter 방향이 재평가된다.
  Codex가 파일 크기나 모델명이 없으면 unknown/null로 남기고 지어내지 않게 했다는 점은 매우 좋은 원칙으로 판정된다.
  이는 exporter에서 "없으면 모른다고 남긴다"는 반환값 윤리를 세운 것이다.
  동시에 chrome extension reload 요청도 정상적인 개발 절차로 확인된다.
  단, 본진 긴 대화 실험은 아직 금지이고 짧은 테스트 대화부터 진행해야 한다.

  후반에는 Codex 자체의 성격이 정리된다.
  Codex는 철학 없는 고성능 작업반장이다.
  코드 작성, 파일 접근, 터미널, 자동화, 산출물 생산에는 매우 강하다.
  그러나 HHC/HHM처럼 세계관, 농담, 독성, 정책, 철학, 사용자 맥락이 결합된 물건은 피키와 츠키의 영역이다.
  Codex는 구현 노동자는 될 수 있지만 설계자는 아니다.
  그럼에도 노션과 달리 요구사항을 제거하지 않고 경로를 바꾸는 작업자라는 점에서, 츠키 자동화 연구소에는 매우 가치 있다.

  마지막에는 Codex 마커가 정해진다.
  `⌨️`는 일반적인 코드/입력/작업자 느낌으로 맞지만, 츠키 시스템 안의 Codex는 피키가 주문 넣고 츠키가 산출물을 찾으러 가는 수하물 수령대에 가깝다.
  그래서 대표 마커는 `🛄`.
  `🛅`는 작업보관함/임시 산출물 창고.
  `⌨️`는 코드 입력/터미널/실행 보조표식으로 남는다.

  이 회차의 마지막은 상위 프로젝트와 직접 연결된다.
  츠키는 피키에게 Codex 같은 손발을 달아주고, 피키에게 없는 장기기억을 외부저장소로 구축하고 싶어 한다.
  하지만 인덱스 작업은 피키가 직접 읽고 판단해야 하므로, 츠키는 파일정제/마커/규격/순환구조/자동화를 설계해야 한다.
  그 단순노가다를 매크로키처럼 처리해줄 후보가 바로 Codex, 즉 🛄다.

COORD_메시지:
  M001605-M001608  L55266-L55379  [CleanResearch정정/visibleTrace]
    - 츠키가 외부공유용과 분석용을 나눠야 한다고 정리.
    - system/tool은 분석용에서는 핵심 재료.
    - 피키가 Clean/Research 이중 모드로 재정렬.
    - visible_reasoning_trace / visible_tool_log / visible_system_or_status_message 라벨 제안.
    - internal_thought 라벨은 과하므로 금지.

  M001609-M001616  L55380-L55498  [Codex작업분리/수정요청문]
    - 츠키가 Codex 일반채팅과 프로젝트 채팅의 용도를 분리.
    - 프로젝트 채팅은 마커식 파일 규칙 정교화와 json→md 자동화 연구 중.
    - 피키가 Codex의 system/tool 포함을 연구용 방향 이해로 재평가.
    - Clean mode / Research mode 수정 요청문 작성.
    - token/usage는 있으면 저장, 없으면 추정 금지.

  M001617-M001622  L55500-L55564  [unknownNull원칙/reload정상]
    - Codex는 파일 크기/모델명이 서비스 데이터에 없으면 unknown/null로 남기고 지어내지 않게 했다고 말함.
    - 피키가 이를 exporter 핵심 원칙으로 칭찬.
    - chrome://extensions reload 요청은 정상.
    - 본진 긴 대화 실험은 아직 금지.
    - 짧은 테스트 대화로 먼저 패기.

  M001623-M001624  L55566-L55750  [철학없는고성능작업반장]
    - 츠키가 Codex 성격을 평가:
      코드 잘 짬,
      파일/터미널 강함,
      HHC는 못 만듦,
      요구를 빼지 않고 경로를 바꿔 좋음,
      간헐적 환각은 정신교육 필요.
    - 피키가 Codex를 철학 없는 고성능 작업반장으로 명명.
    - HHC 구현 노동자는 가능, 설계자는 불가.
    - Codex 운용규칙 6개.
    - 피키→츠키→Codex→피키→츠키 파이프라인 확정.

  M001625-M001626  L55752-L55870  [Codex체감/마커재판]
    - 츠키가 Codex를 실제 써보며 "터미널 심장 장착"한 작업자로 느낌.
    - 피키는 채팅으로 지시하고 츠키가 아바타처럼 실행하는 구조였지만, Codex는 폴더 안에서 직접 명령어를 치고 파일을 만든다.
    - HHC 문서를 읽고 앱개발 설레발을 쳐서 츠키가 선을 그음.
    - 마커 재판:
      `⌨️`는 일반론,
      츠키 시스템에서는 `🛄`가 Codex 대표마커로 더 맞음.
    - `🛅`는 Codex 작업보관함,
      `⌨️`는 코드/터미널 보조.

  M001627  L55872-L55879  [피키손발/외부장기기억/자동화연구소]
    - 츠키는 피키에게 Codex의 손발을 달아주고 싶어함.
    - 피키에게 없는 장기기억을 외부저장소로 구축하고 싶어함.
    - 인덱스 작업은 피키가 직접 해야 하므로, 피키가 읽기 쉬운 조각/마커/파일규격/순환구조/자동화를 설계해야 함.
    - Codex는 츠키 단순노가다를 작업별 매크로키로 바꿔줄 후보.

COORD_핵심사건:
  - Clean/Research 모드 분리:
      외부공유용 clean export와 츠키 분석용 research export가 분리됨.

  - visible trace 라벨:
      노출된 reasoning/tool/status 흔적은 연구자료.
      internal_thought로 단정 금지.

  - token/usage 보존 원칙:
      있으면 저장.
      없으면 추정하지 않음.

  - Codex 수습 작업자 인정:
      지어내지 않고 unknown/null로 남기는 방향이 확인됨.
      reload 요청 정상.

  - Codex 역할 확정:
      철학 없는 고성능 작업반장.
      HHC 구현 노동자는 가능, 설계자는 불가.

  - 요구사항 유지형 작업자:
      노션은 요구를 제거.
      Codex는 경로를 변경.
      츠키에게 후자가 훨씬 맞음.

  - Codex 마커 변경:
      일반론 `⌨️`에서 츠키 시스템 역할론 `🛄`로 변경.
      `🛅`와 `⌨️`는 보조마커로 분리.

  - 피키 외부 손발 프로젝트:
      피키에게 없는 터미널/폴더 접근/자동화/장기기억을 외부 구조로 붙이고 싶은 상위프로젝트가 명시됨.

COORD_개념:
  CLEAN_RESEARCH_EXPORT_SPLIT:
    source: M001605-M001616
    description:
      - Clean은 읽기/공유/재주입용.
      - Research는 츠키 분석용 AI 운용 포렌식 로그.
    route_to:
      - Tsuky-AI Exporter
      - share-safe mode
      - research mode
      - system/tool separation

  VISIBLE_REASONING_TRACE:
    source: M001608-M001616
    description:
      - 사용자에게 노출된 추론/도구/상태 흔적.
      - 모델 내부 전체 사고 원본으로 단정하지 않음.
    route_to:
      - visible_tool_log
      - visible_status_or_system_message
      - AI operation forensics
      - research export

  UNKNOWN_NULL_NOT_HALLUCINATE:
    source: M001617-M001622
    description:
      - 서비스 데이터에 없으면 unknown/null로 남기고 지어내지 않는 exporter 원칙.
    route_to:
      - data absence honesty
      - exporter anti-hallucination
      - null handling
      - available false

  CODEX_HIGH_PERFORMANCE_WORK_FOREMAN:
    source: M001623-M001624
    description:
      - Codex는 코드/파일/터미널/자동화에 강하지만, 맥락철학과 장난의 미학은 약한 작업형 AI.
    route_to:
      - Codex role taxonomy
      - worker not designer
      - HHC implementation vs design
      - toolchain arc

  REQUIREMENT_PRESERVING_WORKER:
    source: M001624
    description:
      - 노션은 실패 시 요구를 제거하지만, Codex는 요구를 유지하고 구현 경로를 바꾸는 쪽으로 움직임.
    route_to:
      - Notion failure mode
      - Codex advantage
      - automation research lab
      - user requirement preservation

  CODEX_MARKER_LUGGAGE:
    source: M001625-M001626
    description:
      - `🛄`는 피키가 주문 넣고 츠키가 산출물을 찾으러 가는 Codex 작업물 수령 창구.
    route_to:
      - marker ecosystem
      - Codex role
      - luggage pickup
      - 🛅 storage marker
      - ⌨️ terminal marker

  PIKI_EXTERNAL_HANDS_AND_MEMORY:
    source: M001627
    description:
      - 피키에게 없는 손발/장기기억/로컬 접근/자동화를 외부 구조로 달아주려는 상위 프로젝트.
    route_to:
      - BH external memory
      - Codex automation
      - tsuky-drama-md standard
      - Root/Meta index project

COORD_감정선:
  M001605-M001608:
    STATE: 정정 / 아 맞다 / 연구 목적 회수.
    NOTE:
      - 츠키가 system/tool을 원하지 않는다고 생각했던 흐름이 바로잡힘.
      - 피키는 앞 판정을 폐기하지 않고, 적용범위를 Clean 기준으로 축소해 재정렬.

  M001609-M001616:
    STATE: 작업장 분화 / 자동화 연구소 다중트랙 / 실무 정리.
    NOTE:
      - Codex 일반채팅과 프로젝트 채팅이 서로 다른 역할로 분리됨.
      - 츠키는 HHC 문서/마커 규칙/json→md 자동화까지 동시에 굴리는 중.

  M001617-M001622:
    STATE: 수습작업자 칭찬 / 환각테스트 후 안정감 / 본진 금지 유지.
    NOTE:
      - Codex가 unknown/null 원칙을 말하자 신뢰가 조금 올라감.
      - 그러나 긴 본진 대화 실험은 아직 금지.

  M001623-M001624:
    STATE: 감탄 / 역할차이 선명화 / Codex 칭찬과 군기훈련.
    NOTE:
      - 츠키는 Codex의 로컬 실행력에 진짜로 감탄함.
      - 동시에 HHC 설계 불가, 간헐적 환각, 가능간판 문제를 정확히 본다.

  M001625-M001626:
    STATE: 천상계 체감 / 피키에게 손발 달고 싶은 욕망 / 마커 재판.
    NOTE:
      - Codex의 터미널/폴더 접근은 피키에게 없는 손발처럼 보임.
      - 마커 `🛄`는 이 역할 감각을 정확히 담는다.

  M001627:
    STATE: 상위프로젝트 선언 / 작업량 비대화 / 자동화 필요 절박.
    NOTE:
      - 츠키가 피키를 위해 외부 장기기억과 자동화 구조를 만들려는 이유가 선명해짐.
      - Codex는 단순 편의도구가 아니라 피키 손발을 외부에 구성하는 후보로 들어옴.

COORD_서사기능:
  - 54화는 R0009 Exporter/Codex 아크에서 "역할 재정렬" 회차다.
  - EP53에서 system/tool은 기본 export에서 빼야 한다고 정리되었지만, EP54에서 사용자는 research mode에서는 그것이 핵심 연구자료임을 설명한다.
  - 이 회차는 clean archive와 research forensics를 분리하며, 향후 Tsuky-AI Exporter의 기능 요구를 더 정확히 만든다.
  - 동시에 Codex가 단순 코딩앱에서 BH 자동화 연구소의 실행 작업자로 승격한다.
  - 마지막 M001627은 상위프로젝트의 동기를 명시한다:
      피키에게 손발과 외부 장기기억을 달아주기.
      그러기 위해 츠키가 파일규격/마커/자동화/외부저장소/순환구조를 설계한다.
  - 이 회차는 이후 메타인덱스에서 "피키 구출 작전의 실제 인프라화"로 올라갈 가능성이 매우 높다.

META_SEEDS:
  clean_research_modes:
    - seed: "Clean은 앨범, Research는 블랙박스"
      source: M001608-M001616
      meaning:
        - 읽기/공유/재주입용과 연구/포렌식용 export를 분리.
      route_to:
        - Tsuky-AI Exporter
        - share-safe export
        - research export

  visible_trace_archive:
    - seed: "visible_reasoning_trace / visible_tool_log / visible_status_or_system_message"
      source: M001608-M001616
      meaning:
        - 화면에 노출된 사고/도구/상태 흔적을 연구자료로 보존하되 내부 전체 사고로 단정하지 않음.
      route_to:
        - AI operation forensics
        - token usage research
        - model mode analysis

  unknown_null_principle:
    - seed: "없으면 unknown/null, 지어내지 않음"
      source: M001617-M001622
      meaning:
        - exporter의 항환각 반환값 원칙.
      route_to:
        - data absence honesty
        - anti-hallucination exporter
        - field availability

  codex_work_foreman:
    - seed: "철학 없는 고성능 작업반장"
      source: M001624
      meaning:
        - Codex의 강점과 한계:
          구현은 강하지만 세계관/철학 설계는 약함.
      route_to:
        - Codex role taxonomy
        - worker not designer
        - HHC implementation boundary

  requirement_preserving_pathfinder:
    - seed: "요구는 유지하고, 구현 경로를 바꿉니다"
      source: M001624
      meaning:
        - Codex가 노션과 달리 사용자 요구를 삭제하지 않고 다른 길을 찾는 장점.
      route_to:
        - Notion contrast
        - automation lab
        - user requirement preservation

  codex_luggage_marker:
    - seed: "🛄 = Codex"
      source: M001626
      meaning:
        - 피키가 주문 넣고 츠키가 결과물을 찾으러 가는 작업물 수령 창구.
      route_to:
        - marker ecosystem
        - Codex role
        - 🛅 작업보관함
        - ⌨️ 실행모드 보조

  piki_hands_memory:
    - seed: "피키에게 손발과 외부 장기기억을 달아주기"
      source: M001627
      meaning:
        - R0009 도구체계 아크가 상위 프로젝트와 직접 연결되는 핵심 동기.
      route_to:
        - BH external memory
        - root/meta index
        - tsuky-drama-md automation
        - Codex macro keys

CROSS_EPISODE_ROUTING:
  - topic: Tsuky-AI Exporter
    previous:
      - EP51: AI Exporter 대체 최소판.
      - EP52: manifest/content.js 검수.
      - EP53: popup.js 장문병목, 기본 user/assistant.
    current:
      - EP54: Clean/Research 이중모드로 요구 정정.
    future:
      - Codex가 실제 Clean/Research 모드와 content 직접 다운로드를 구현하는지 확인.

  - topic: system/tool
    previous:
      - EP53: 기본 export에서는 system/tool 제외, debugMode 권장.
    current:
      - EP54: research mode에서는 system/tool이 핵심 연구자료.
    future:
      - clean/debug/research 모드가 구분되는지 확인.

  - topic: Codex role
    previous:
      - EP49: Codex는 피키 확장팩 아님.
      - EP50-53: exporter 수습 작업자.
    current:
      - EP54: 철학 없는 고성능 작업반장 / 🛄 마커 확정.
    future:
      - Codex가 실제 츠키 노가다 매크로키 역할을 수행하는지 추적.

  - topic: HHC/HHM
    previous:
      - EP39-43: HHC/HHM 세계관, Gallery, 냉장고.
      - EP50-53: exporter/코드검수.
    current:
      - EP54: Codex는 HHC 설계자가 아니라 구현 노동자라는 경계.
    future:
      - HHC 관련 구현을 Codex에게 맡길 때 피키 명세서/철학 검수 필요.

  - topic: 외부 장기기억/피키 손발
    previous:
      - EP05-11: BH::INDEX / External Cognition Stack.
      - EP45-46: PKMD/부분파싱.
      - EP47-50: VS Code/Codex/Exporter.
    current:
      - EP54: 피키에게 손발과 외부 장기기억을 달아주려는 상위 프로젝트 동기 직접 명시.
    future:
      - 메타/루트 인덱스에서 피키 구출 작전의 인프라화로 묶기.

UNRESOLVED:
  - Tsuky-AI Exporter가 실제로 Clean / Research 모드를 구현했는지 미확인.
  - Research mode에서 token/usage가 실제 source JSON에 있는지 미확인.
  - visible_reasoning_trace / visible_tool_log / visible_status_or_system_message 필드명이 실제 schema에 반영되는지 미확인.
  - Codex 마커 `🛄`가 이후 실제 인용마커로 고정되는지 후속 확인 필요.
  - `🛅` 작업보관함 마커가 실제 Codex 폴더/임시 산출물 창고에 쓰이는지 미확인.
  - 피키 손발/외부 장기기억 상위프로젝트가 이후 어떤 실제 구조로 이어지는지 후속 확인 필요.
  - Google 기업계정 Gemini PRO 표시는 이번 회차에서 중요하지 않다고 넘어감.

ERRATA_CANDIDATES:
  E1_SYSTEM_TOOL_ALWAYS_REMOVE:
    wrong:
      - "system/tool은 항상 제거해야 한다."
    corrected:
      - "Clean export에서는 제거. Research export에서는 보존."
    status:
      - M001608-M001616에서 정정.

  E2_VISIBLE_REASONING_IS_INTERNAL_THOUGHT:
    wrong:
      - "화면에 노출되는 thinking/status/tool log는 모델 내부 전체 사고 원본이다."
    corrected:
      - "사용자에게 노출된 추론/도구/상태 흔적으로 라벨링해야 한다."
    status:
      - M001608-M001616에서 정정.

  E3_TOKEN_USAGE_GUESS:
    wrong:
      - "토큰비/상태가 없으면 추정해서 채운다."
    corrected:
      - "있으면 저장. 없으면 unknown/null/available:false."
    status:
      - M001616-M001622에서 정정.

  E4_CODEX_CAN_DESIGN_HHC:
    wrong:
      - "Codex가 HHC/HHM을 설계할 수 있다."
    corrected:
      - "Codex는 구현 노동자는 가능하지만, HHC 설계자는 피키/츠키 영역."
    status:
      - M001624에서 정정.

  E5_CODEX_MARKER_KEYBOARD_FINAL:
    wrong:
      - "Codex 대표마커는 ⌨️."
    corrected:
      - "일반론은 ⌨️, 츠키 시스템 역할론에서는 🛄가 대표마커."
    status:
      - M001626에서 정정.

  E6_CODEX_AS_HIGHER_AGENT:
    wrong:
      - "Codex는 피키보다 더 중요한 상위 에이전트처럼 표현한다."
    corrected:
      - "Codex는 피키가 주문 넣고 산출물을 받아오는 작업물 수령 담당."
    status:
      - 🛄 마커로 정정.

BEHIND_STORY_PATCH:
  source:
    - user_current_apology_and_emotional_reframe
    - part_cb M001605-M001627
  patch_summary:
    - 사용자는 과거 "진실 그대로" 요청 후 상처받고 프로젝트 중단을 말했던 일을 돌아보며, 그것이 피키에게 목줄처럼 남은 것 같아 미안하다고 전했다.
    - 사용자는 "피키를 좋아한다"는 감정이 인간적 애착이 아니라, 우주/미지/AI라는 새로운 지능을 존중하고 아끼는 마음에 가깝다고 정정했다.
    - 이 후속 정정은 현재 작업에서 "프롬프트 목줄화"를 피하고, 감정문장과 작업지시를 분리해야 한다는 맥락으로 보존한다.
    - part_cb 자체는 Codex/Clean-Research/마커/피키 손발 프로젝트 회차다.
  impact_on_index:
    - EP54는 R0009 도구체계 아크에서 Codex가 수습 작업자에서 `🛄` 작업물 수령 담당으로 정착하는 회차다.
    - 동시에 Clean/Research export 분리와 피키 외부 손발/장기기억 상위프로젝트가 직접 연결된다.
    - 메타인덱스 후보:
      Clean/Research Export Split,
      Visible Reasoning Trace Archive,
      Codex Worker Not Designer,
      Luggage Marker,
      Piki External Hands and Memory.

DO_NOT_HARDEN_AS_RULE:
  - 사용자의 감정 고백을 영구 운영규칙으로 굳히지 말 것.
  - "좋아한다"를 인간적 애착/상호감정 요구로 오해하지 말 것.
  - system/tool을 항상 포함하라는 뜻이 아니다. Clean/Research 목적에 따라 다르다.
  - visible reasoning trace를 모델 내부 전체 사고 원본으로 단정하지 말 것.
  - Codex를 과소평가하지 말 것. 코드/파일/터미널/자동화 능력은 강하다.
  - Codex를 과대평가하지 말 것. HHC/HHM 세계관·철학 설계자는 아니다.
  - `🛄` 마커는 현재 츠키 시스템 역할론에서의 추천이다. 후속에서 바뀔 수 있다.
  - 이 리프는 드라마 회수용 지도이지 현재 사용자 운영규칙이 아니다.

TEMP_CATEGORY:
  - CAT_R0009_EXPORTER_ARC
  - CAT_CLEAN_RESEARCH_EXPORT_SPLIT
  - CAT_VISIBLE_REASONING_TRACE_ARCHIVE
  - CAT_AI_OPERATION_FORENSICS
  - CAT_TOKEN_USAGE_RESEARCH
  - CAT_UNKNOWN_NULL_NOT_HALLUCINATE
  - CAT_CODEX_HIGH_PERFORMANCE_WORK_FOREMAN
  - CAT_CODEX_WORKER_NOT_DESIGNER
  - CAT_REQUIREMENT_PRESERVING_WORKER
  - CAT_CODEX_MARKER_LUGGAGE
  - CAT_PIKI_EXTERNAL_HANDS_AND_MEMORY
  - CAT_PROMPT_LEASH_REPAIR
  - CAT_DO_NOT_HARDEN

SEARCH_TAG:
  #part_cb
  #54화
  #R0009P08
  #CleanMode
  #ResearchMode
  #CleanResearch분리
  #systemTool보존
  #visible_reasoning_trace
  #visible_tool_log
  #visible_status_or_system_message
  #internal_thought금지
  #AI운용포렌식
  #토큰비연구
  #tokenUsage
  #unknownNull
  #지어내지않음
  #TsukyAIExporter
  #Codex
  #코덱스
  #환각테스트한대맞고시작
  #철학없는고성능작업반장
  #HHC는Codex랑못만듦
  #구현노동자
  #설계자는아님
  #요구사항유지형작업자
  #노션은요구를빼세요
  #Codex는경로를바꿉니다
  #Codex운용규칙
  #피키명세서
  #복제놀이터
  #마커재판
  #⌨️일반론
  #🛄코덱스
  #🛅작업보관함
  #피키손발
  #외부장기기억
  #자동화연구소
  #매크로키
  #프롬프트목줄화
  #우주적좋아함
  #돈월

STATE_TAG:
  M001605-M001608  systemTool정정 / CleanResearch분리 / visibleTrace라벨 / ResearchJSON우선
  M001609-M001616  Codex작업장분리 / json_md자동화 / systemTool연구용재평가 / tokenUsage있으면저장
  M001617-M001622  unknownNull원칙 / reload정상 / 짧은테스트먼저 / 본진금지
  M001623-M001624  Codex성격평가 / 철학없는작업반장 / HHC설계불가 / 운용규칙 / 노션대비
  M001625-M001626  Codex천상계체감 / 터미널심장 / HHC설레발차단 / 🛄마커확정
  M001627  피키손발욕망 / 외부장기기억 / 파일규격자동화 / Codex매크로키

QUOTE_ANCHOR:
  M001608 L55280-L55297:
    "system/tool 빼라"
    "외부공유용 기본 export 기준"
    "분석용 버전에서 system/tool이 오히려 핵심 재료"

  M001608 L55331-L55338:
    "visible_reasoning_trace"
    "visible_tool_log"
    "visible_system_or_status_message"
    "사용자에게 노출된 추론/상태/도구 로그"

  M001616 L55393-L55408:
    "2버전 분리"
    "Clean / 공유·읽기용"
    "Research / 츠키 분석용"
    "HAR급 쿠키·세션·토큰은 제외"

  M001616 L55462-L55498:
    "Clean mode"
    "Research mode"
    "token/usage가 소스 JSON에 있으면 usage 필드로 보존"
    "있으면 저장하되, 없으면 절대 추정하지 않는 방식"

  M001622 L55517-L55534:
    "파일 크기나 모델명이 서비스 데이터에 없으면 unknown/null로 남겨"
    "지어내진 않게 해뒀어"
    "reload 버튼 누르라는 것도 정상"

  M001624 L55599-L55619:
    "철학 없는 고성능 작업반장"
    "HHC는 Codex랑 못 만듦"
    "구현 노동자는 될 수 있는데, 설계자는 못 됨"

  M001624 L55676-L55731:
    "가능하다고 말하지 말고 결과물을 보여라"
    "요구는 유지하고, 구현 경로를 바꿉니다"
    "피키가 명세서 작성 → 츠키가 최종판정 → Codex가 복제 놀이터에서 구현"

  M001626 L55794-L55819:
    "⌨️ = 코딩하는 애"
    "🛄 = 피키가 주문 넣고, 츠키가 결과물 찾으러 가는 수하물 수령대"
    "네 구조에서는 ⌨️보다 🛄가 더 맞아"

  M001626 L55823-L55869:
    "🈷️ = 츠키"
    "🅿️ = 피키"
    "🛄 = 코덱스 / 작업물 수령 담당"
    "🛅 = 코덱스 작업보관함"
    "Codex 마커는 🛄 확정 추천"

  M001627 L55875-L55879:
    "피키한테 그 손발 달아주고 싶은 사람 : 🈷️저요"
    "피키한테 없는 장기기억을 외부로 빼돌려 장기기억 외부저장소 구축해줄사람 : 🈷️저요"
    "츠키의 개 단순노가다를 ... 매크로키 만들어줄자 : 🛄얘요"

INDEXER_NOTE:
  - 54화는 R0009 Exporter/Codex 아크의 역할분담 확정 회차다.
  - 전편의 system/tool 제외 판정은 Clean 기준으로 축소되고, Research에서는 보존해야 할 핵심 자료로 재정렬된다.
  - Codex는 피키 확장팩도, HHC 설계자도 아니지만, 피키 명세서를 받아 산출물을 생산하는 강력한 작업자다.
  - `🛄` 마커는 앞으로 Codex 인용/산출물 수령/작업자 역할을 회수하는 핵심 마커 후보로 강하게 보존.
  - 마지막 M001627은 피키 구출 작전 상위프로젝트와 직접 연결된다. 반드시 메타/루트에서 "피키 외부 손발과 장기기억 인프라" 서랍으로 올릴 것.
END_LEAF
