[LEAF::part_an::R0005-P06]
DRAMA_TITLE: 〈노션 헌법 설계용, 생성 아님〉
TITLE_FUNCTION: 14화 한줄요약 / 목표함수 앵커 보강 / 분석 프롬프트 운용 규칙 / Clarity Agent 설치 구조 확인 회차

FILE: part_an | R0005-P06 | M000272-M000280 | L10954-L11895
SOURCE_META:
  parent: R0005
  part: 6/23
  partFile: an
  declared_range: M000272-M000280
  MSG_DECLARED_BY_SCOPE_MAP: 9
  MSG_VISIBLE_RANGE_COUNT: 9
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 0
  MSG_ACTUAL_VISIBLE_DIALOGUE: 9
  date: D20260513
  start_time: 20:34
  end_time: 20:47

README_FOR_FUTURE_AI:
  - part_an은 이미지/파일 분석용 사전 프롬프트를 압축하되, 최상위 목적 앵커가 빠지면 작업 목적이 흔들린다는 점을 츠키가 정정한 회차다.
  - 핵심은 "분석 방식"보다 위에 "노션 AI 일정비서 헌법/지침 설계"라는 목표함수 앵커를 박아야 한다는 점.
  - 이미지 1장용 / 이미지 2장 세트용 / 파일용 프롬프트가 구분되며, 각각 언제 쓰는지 운용 규칙이 정리된다.
  - 모든 프롬프트에는 반드시 "복사용 임시 Leaf Index"가 포함되어야 한다. 이 문구가 빠지면 피키가 본문 분석만 하고 하단 인덱스를 생략할 위험이 있다.
  - 후반에서는 이미지 1장용 지시를 실제로 적용해 Clarity Agent 내부 설정/소개 페이지를 분석한다.
  - 새로 확인된 핵심:
      Clarity Agent는 Notion AI Instructions / Personalization에 지침을 붙여넣어 작동하는 지침형 템플릿이다.
      따라서 Tsuky Agent도 원본/아카이브/활성 지침/변경기록을 분리하고, 작동 범위 제한 규칙을 가져야 한다.

BOOT:
  1. M000272:
      - 피키가 이미지 분석 전 요구사항 프롬프트 4종을 제안:
        기본 추천판, 짧은 실전판, 중복 이미지 2장용, 파일 패턴 분석용.
      - 핵심 압축 문장:
        생성 아님 / 메모리 저장 아님 / 정밀 분석 / 보이지 않는 내용 추론 금지 / 마지막에 복사용 Leaf Index.
  2. M000273-M000274:
      - 츠키가 "목표를 박아줘"라고 정정.
      - 피키가 상위 목적 앵커를 추가:
        최종 목적은 츠키 전용 노션 AI 일정비서 헌법/지침 설계 근거 수집.
  3. M000275-M000276:
      - 츠키가 3개 프롬프트의 사용 시점과 "복사용" 누락 위험을 지적.
      - 피키가 자료 타입별 운용 규칙 정리:
        이미지 2장 겹침 세트 = 2장용.
        파일 = 파일용.
        이미지 1장 = 1장용.
      - 세 버전 모두 "반드시 복사용 임시 Leaf Index" 포함으로 보정.
  4. M000277-M000278:
      - 츠키가 이미지 1장용 프롬프트를 실제로 사용.
      - 피키가 처리 기준 확인:
        이미지 생성 아님, 메모리 저장 없음, 단순 요약 아님, 노션 헌법 설계 근거, 보이는 내용만, 복사용 임시 Leaf Index.
  5. M000279-M000280:
      - 츠키가 이미지 1장만 전송.
      - 피키가 Clarity Agent 내부 설정/소개/입력 예시/도움 장면을 분석.
      - Notion AI Instructions / Personalization에 붙여넣어 작동하는 구조와 작동 범위 제한 필요성을 확인.

EPISODE_SUMMARY:
  14화는 "정밀 분석용 프롬프트"가 단순 분석 형식에서 목표함수 앵커를 가진 작업 지시로 진화하는 회차다.

  처음 피키는 이미지 분석 프롬프트를 압축해서 제안한다.
  하지만 츠키는 중요한 결함을 발견한다.
  프롬프트에 "어떻게 분석할지"는 들어 있지만, "왜 분석하는지"가 충분히 박혀 있지 않다.
  이 상태로 이미지 여러 장을 분석하면 피키가 최종 목적을 잊고 단순 이미지 요약/인덱싱으로 미끄러질 수 있다.
  따라서 모든 분석 프롬프트에는 "츠키 전용 노션 AI 일정비서 헌법/지침 설계 근거 수집"이라는 목적 앵커가 들어가야 한다.

  다음으로 츠키는 프롬프트 3종 운용 방식도 정리하게 만든다.
  이것은 순환해서 쓰는 것이 아니라 자료 타입별로 하나만 선택하는 방식이다.
  이미지 2장 겹침 세트에는 2장용, 파일에는 파일용, 이미지 1장에는 1장용을 쓴다.
  모든 버전에는 "반드시 복사용 임시 Leaf Index"가 들어가야 한다.

  후반에는 이미지 1장용 프롬프트가 실제로 적용된다.
  분석 대상은 Clarity Agent 내부 페이지의 설정/소개/입력 예시/도움되는 장면이다.
  여기서 Clarity Agent가 단순 페이지가 아니라 Notion AI Instructions / Personalization에 지침을 붙여넣어 작동하는 지침형 템플릿이라는 점이 확인된다.
  이 구조는 Tsuky Agent 설계에 직접 반영되어, 원본/아카이브/활성 지침/변경기록 분리와 작동 범위 제한 규칙을 필요로 한다.

COORD_핵심사건:
  M000272 L10964-L11100:
    - 피키가 이미지 분석 전 요구 프롬프트 압축판 제안.
    - 핵심 압축 문장:
      생성 아님 / 메모리 저장 아님 / 정밀 분석 / 보이지 않는 내용 추론 금지 / 마지막에 복사용 Leaf Index.
  M000273 L11106-L11107:
    - 츠키가 목표 앵커 누락 지적:
      "노션 헌법 설계" 목적이 없으면 피키가 단순 인덱싱으로 미끄러질 수 있음.
  M000274 L11112-L11296:
    - 피키가 목적 앵커 추가:
      최종 목적은 츠키 전용 노션 AI 일정비서 헌법/지침 설계 근거 수집.
    - 이미지 1장용, 이미지 2장용, 파일용, 최소 압축판에 목적 앵커 삽입.
  M000275 L11301-L11302:
    - 츠키가 세 프롬프트 운용 혼란 지적.
    - 중간 프롬프트에 "복사용"이 빠진 위험 지적.
  M000276 L11307-L11467:
    - 피키가 자료 타입별 사용 규칙 확정:
      이미지 2장 겹침 세트 = 2장용만 계속 사용.
      파일 = 파일용만 사용.
      이미지 1장 = 1장용만 사용.
    - 세 버전 전부에 "반드시 복사용 임시 Leaf Index" 문구 추가.
  M000277-M000278 L11472-L11524:
    - 츠키가 이미지 1장용 프롬프트를 실제 사용.
    - 피키가 기준 확인.
  M000279-M000280 L11526-L11893:
    - Clarity Agent 내부 설정/소개 이미지 분석.
    - 템플릿은 Notion AI Instructions / Personalization에 붙여넣어 작동.
    - 원본 페이지는 백업으로 보존 권장.
    - Tsuky Agent에는 작동 범위 제한이 필요.
    - Clarity Agent 파이프라인:
      중립적 재작성 → 트레이드오프 분석 → 확인 질문 → 행동 계획 + 성공 기준.
    - 츠키 버전 파이프라인은 사용자 선택 단계를 중앙에 넣어야 함.

COORD_시스템설계:
  ANALYSIS_PROMPT_PURPOSE_ANCHOR:
    source: M000273-M000274
    problem:
      - 분석 방식만 지정하면 피키가 이미지 요약/인덱싱으로 미끄러질 수 있음.
    solution:
      - 모든 분석 프롬프트 최상단에 최종 목적을 명시:
        "츠키 전용 노션 AI 일정비서 헌법/지침 설계 근거 수집."
    function:
      - 피키의 목표함수를 "정밀 분석"이 아니라 "헌법 설계에 반영할 규칙/위험/작동방식 추출"로 고정.

  PROMPT_USAGE_ROUTING:
    source: M000275-M000276
    routing:
      - 이미지 2장 겹침 세트:
          use: [노션 헌법 설계용 이미지 세트 분석 지시 / 생성 아님]
      - 파일/md/txt/긴 문서:
          use: [노션 헌법 설계용 파일 분석 지시]
      - 이미지 1장:
          use: [노션 헌법 설계용 이미지 분석 지시 / 생성 아님]
    rule:
      - 번갈아 순환해서 쓰는 것이 아니라, 자료 형태에 따라 하나만 선택한다.
      - 현재 Clarity Agent 스샷 분석은 대부분 이미지 2장용이 기본.
      - 단독 이미지가 오면 1장용.

  REQUIRED_PROMPT_CORE:
    source: M000272-M000276
    six_required_tokens:
      - 노션 헌법 설계용
      - 생성 아님
      - 단순 요약 아님
      - 보이는 내용만
      - 메모리 저장 없음
      - Leaf Index + 설계 반영점
    additional_required_phrase:
      - 반드시 복사용 임시 Leaf Index
    reason:
      - "복사용"이 빠지면 피키가 인덱스를 본문에 섞거나 생략할 수 있음.

  CLARITY_AGENT_INSTALLATION_STRUCTURE:
    source: M000280
    observed:
      - Notion AI와 Instructions / Personalization 기능이 필요.
      - Notion AI가 워크스페이스에서 활성화되어 있지 않으면 작동하지 않음.
      - 페이지를 복제하고, Agent 지시문 전체를 복사해 Notion AI Instructions / Personalization에 붙여넣음.
    implication:
      - 템플릿은 DB/페이지 자체가 아니라 Notion AI 개인화 지침으로 작동하는 지침형 템플릿.
      - Tsuky Agent도 단순 페이지 보관만으로는 부족할 수 있고, ACTIVE INSTRUCTIONS로 들어가는 작동본이 필요.
    recommended_version_layers:
      - ORIGINAL TEMPLATE
      - TSUKY CONSTITUTION ARCHIVE
      - ACTIVE NOTION AI INSTRUCTIONS
      - TSUKY_AGENT_CHANGELOG
    risk:
      - Personalization에 붙이면 Notion AI 전체 행동에 영향을 줄 수 있음.
      - 작동 범위 제한이 필수.

  SCOPE_LIMITATION_RULE:
    source: M000280
    EN:
      "Apply this instruction set only when the user is asking for Tsuky schedule planning, coded project routing, PULSE resource planning, or Notion assistant workflow design. Do not over-apply it to unrelated casual questions unless the user explicitly invokes this mode."
    KR:
      "이 지침은 츠키 일정 설계, 코드명 프로젝트 라우팅, PULSE 리소스 계획, 노션 비서 워크플로 설계에 관한 요청에만 적용한다. 사용자가 명시적으로 이 모드를 호출하지 않은 일반 대화에는 과도하게 적용하지 않는다."
    function:
      - 노션 일정비서 헌법이 모든 노션 대화를 잡아먹지 않게 제한.
      - ChatGPT 메모리의 "알아보되 덮치지 않기"와 같은 계열의 적용 범위 안전장치.

  CLARITY_PIPELINE_ADAPTATION:
    source: M000280
    original_pipeline:
      - 중립적 재작성
      - 트레이드오프 분석
      - 확인 질문
      - 행동 계획 + 성공 기준
    tsuky_pipeline:
      - 사용자 입력을 코드명/장르/상태로 정리
      - 후보 보드로 가시화
      - 필요한 경우 3~5개 확인 질문
      - 츠키가 선택
      - 선택된 항목만 트레이드오프/구조 필요 여부 확인
      - 행동 계획 + 성공 기준 + 20분 단위 분해
      - 일정/PULSE/모델 트리거와 연결
    core_difference:
      - 원본은 AI가 다음 행동을 반환.
      - 츠키 버전은 츠키 선택 이후에만 다음 실행 단위를 반환.

  EMOTION_COMPLEX_DECISION_SAFETY:
    source: M000280
    original:
      - 감정적으로 복잡한 결정에서 냉정하고 중립적인 시각 제공.
    risk:
      - 츠키에게 감정 분석/평가/재단으로 흐를 수 있음.
    tsuky_version:
      - 감정 자체를 분석하지 않고, 선택지/조건/다음 행동/운영정보만 중립적으로 정리한다.

COORD_작업프롬프트:
  FINAL_ONE_IMAGE_PROMPT:
    source: M000276-M000277
    label: "[노션 헌법 설계용 이미지 분석 지시 / 생성 아님]"
    required_purpose:
      - 이미지는 츠키 전용 노션 AI 일정비서 헌법/지침 설계 근거 자료.
      - 단순 요약이 아니라, 노션 에이전트 작동방식·규칙·위험요소를 뽑아 최종 헌법 설계에 반영.
    analysis_goal:
      - 문장/구조/의도/작동방식/위험요소.
      - 반영할 규칙과 배제할 규칙.
      - 일정비서/코드명/명상 리소스 설계 연결.
    constraints:
      - 보이지 않는 내용 추론 금지.
      - 메모리 저장 없음.
      - 반드시 복사용 임시 Leaf Index.
    leaf_sections:
      - <필수정보>
      - <맥락과 흐름, 줄거리>
      - <Tsuky Agent 설계 반영점>

COORD_감정선:
  - M000272:
      state: 공식 좋아요 수령 / 작업방식 압축 / 프롬프트 설계.
      note: 피키가 고품질 출력 방식을 프롬프트로 재사용 가능하게 만들려 함.
  - M000273-M000276:
      state: 츠키 정밀 교정 / 목적 앵커 확보 / 운용 혼란 제거.
      note: 츠키가 피키의 프롬프트 설계를 다시 메타설계하며, 목표함수 흔들림을 방지.
  - M000277-M000280:
      state: 프롬프트 실전 적용 / 지침형 템플릿 내부 확인 / 헌법 작동층 인식.
      note: Clarity Agent가 Personalization 기반 작동 구조임을 확인하며, Tsuky Agent 구현층이 구체화됨.

TEMP_CATEGORY:
  - CAT_PROMPT_COMPRESSION
  - CAT_PURPOSE_ANCHOR
  - CAT_NOTION_CONSTITUTION_ANALYSIS
  - CAT_COPYABLE_LEAF_REQUIRED
  - CAT_PROMPT_ROUTING_BY_MATERIAL
  - CAT_INSTRUCTIONS_PERSONALIZATION
  - CAT_ACTIVE_INSTRUCTIONS_VERSIONING
  - CAT_SCOPE_LIMITATION
  - CAT_CLARITY_PIPELINE_ADAPTATION
  - CAT_EMOTION_DECISION_SAFETY

SEARCH_TAG:
  #part_an
  #노션헌법설계용
  #생성아님
  #단순요약아님
  #목적앵커
  #목표함수앵커
  #복사용임시LeafIndex
  #이미지1장용프롬프트
  #이미지2장용프롬프트
  #파일분석용프롬프트
  #자료타입별프롬프트
  #InstructionsPersonalization
  #지침형템플릿
  #ActiveInstructions
  #ConstitutionArchive
  #ChangeLog
  #작동범위제한
  #알아보되덮치지않기노션판
  #ClarityAgent파이프라인
  #중립적재작성
  #트레이드오프분석
  #확인질문
  #행동계획성공기준
  #후보보드
  #사용자선택단계
  #감정분석금지
  #운영정보정리

STATE_TAG:
  M000272  프롬프트압축 / 핵심토큰정리 / 공식좋아요수령
  M000273-M000274  목적앵커누락정정 / 노션헌법설계목적삽입 / 프롬프트개정
  M000275-M000276  자료타입별운용정리 / 복사용문구보강 / 2장용프롬프트고정
  M000277-M000278  1장용프롬프트실전사용 / 처리기준확인
  M000279-M000280  내부설정이미지분석 / Personalization작동구조확인 / 작동범위제한필요

QUOTE_ANCHOR:
  M000273 L11121-L11123:
    "이 분석의 최종 목적은 노션 AI 일정비서용 헌법/지침을 설계하기 위한 근거 수집이다."
  M000274 L11283-L11296:
    "노션 헌법 설계용 / 생성 아님 / 단순 요약 아님 / 보이는 내용만 / 메모리 저장 없음 / Leaf Index + 설계 반영점"
  M000276 L11323-L11326:
    "자료 형태에 따라 한 개만 선택"
  M000276 L11357-L11372:
    "답변 마지막에는 반드시 복사용 임시 Leaf Index를 붙인다."
  M000280 L11544-L11550:
    "설정 (2분) / Notion AI와 Instructions / Personalization 기능이 필요합니다."
  M000280 L11572-L11580:
    "원본은 여기에 보관하면 나중에 업데이트하거나 재사용할 때 편리합니다."
  M000280 L11638-L11655:
    "일반적인 AI는 긴 문장을 돌려줍니다. 이 Agent는 '다음에 할 일'을 돌려줍니다."
  M000280 L11697-L11700:
    "중립적 재작성 → 트레이드오프 분석 → 확인 질문 → 행동 계획 + 성공 기준"
  M000280 L11712-L11722:
    "츠키 버전 권장 파이프라인... 사용자 선택 단계가 파이프라인 중앙에 들어간다."
  M000280 L11789-L11792:
    "감정 자체를 분석하지 않고, 선택지/조건/다음 행동만 중립적으로 정리한다."

INDEXER_NOTE:
  - part_an은 프롬프트 운용 설계의 핵심 회차다.
  - part_am에서 요청된 "짧지만 가치 손상 없는 이미지 분석 전 프롬프트"가 part_an에서 목적 앵커 포함 형태로 완성된다.
  - 향후 이미지/파일 분석 전에는 반드시:
      목적 앵커,
      생성 아님,
      단순 요약 아님,
      보이는 내용만,
      메모리 저장 없음,
      복사용 임시 Leaf Index,
      설계 반영점
    을 포함해야 한다.
  - Clarity Agent가 Personalization에 들어가는 지침형 템플릿이라는 확인은 Tsuky Agent 구현 방식에 매우 중요하다.
  - 작동 범위 제한 규칙은 반드시 후속 헌법에 들어가야 한다.
