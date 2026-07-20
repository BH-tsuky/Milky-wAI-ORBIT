[LEAF::part_al::R0005-P04]
DRAMA_TITLE: 〈지시 먼저, 자료 나중 — 목성 대적점 방지 프로토콜〉
TITLE_FUNCTION: 12화 한줄요약 / 자료 투입 순서 검증 / Notion 템플릿 패시브 분석 / Tsuky Agent 헌법 뼈대 확정 회차

FILE: part_al | R0005-P04 | M000252-M000264 | L9405-L10270
SOURCE_META:
  parent: R0005
  part: 4/23
  partFile: al
  declared_range: M000252-M000264
  MSG_VISIBLE_RANGE_COUNT: 13
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 8  # O04 M000252-M000255, O02 M000262-M000263, plus file-handling omissions as declared
  MSG_ACTUAL_VISIBLE_DIALOGUE: 5  # visible: M000256, M000257, M000258, M000259, M000260, M000261(empty), M000264 => 실질 대화 6~7개로 취급 가능
  date: D20260513
  start_time: 19:47
  end_time: 19:55

README_FOR_FUTURE_AI:
  - part_al은 두 가지가 핵심이다.
    1) Notion 무료/기본 개인화 템플릿들의 반복 작동 구조 분석.
    2) 정밀 파일/이미지 분석에서 "지시 먼저, 자료 나중" 방식이 가장 안전하다는 처리 프로토콜 검증.
  - 이 회차는 Clarity Agent 본문 분석 자체보다, Tsuky Agent 헌법을 만들 때 어떤 섹션 구조를 가져와야 하는지 정리한 회차다.
  - 특히 PRIMARY OVERRIDE, 사용자 입력 재정의 금지, 초보자 친화성 분리, 결정 규칙, 프레이밍 제한 규칙이 중요하다.
  - M000257-M000264는 향후 모든 고정밀 자료 투입 작업의 표준 절차로 회수해야 한다.
  - "목성의 대적점" 비유는 헌법/루트 설계 초기에 작은 오차가 나중에 거대한 왜곡으로 커지는 위험을 압축한다.

BOOT:
  1. M000256: 피키가 사용자가 제공한 무료 노션 템플릿 md 파일을 정독이 아니라 패턴 분석 모드로 처리. 무료 템플릿의 공통 작동 구조를 뽑음.
  2. M000256: 주요 반복 패턴 정리:
      - 기본 설정은 일반 규칙보다 우선.
      - 사용자 입력 재정의 금지.
      - 초보자 친화적 기본값.
      - 결정 규칙이 템플릿 엔진.
      - 무료 템플릿은 페르소나/톤 중심, 유료 Clarity Agent는 행동 변환 파이프라인 중심.
  3. M000257-M000258: 츠키가 파일/이미지와 지시문을 동시에 보낼 때 처리 순서 한계를 확인. 피키는 "지시 먼저, 자료 나중"이 정밀작업 최상위 방식이라고 정리.
  4. M000259-M000260: 츠키가 베타 테스트로 먼저 요구문만 보내고, 다음 턴에 파일만 보내기로 함. 피키는 패턴 분석 기준을 사전 수락.
  5. M000261-M000264: 파일만 전송 후, 피키가 이를 정독 대상이 아니라 무료 템플릿 패시브 분석 대상으로 성공적으로 처리. 베타 테스트 성공 판정.

EPISODE_SUMMARY:
  12화는 Notion Agent 설계의 "헌법 뿌리"와 "자료 투입 방식"이 동시에 정리되는 회차다.

  전반부에서는 노션 무료/기본 템플릿들의 공통 작동 구조가 분석된다.
  겉으로는 교육자, 창의가, 시스템 빌더, 문서 정리 도구, 자동화 도우미, 연구 과학자, 스토리텔러, 코미디언 등 서로 다른 페르소나를 갖지만,
  내부적으로는 정체성, 역할/목소리, 목표, 결과물 형식, 기본 설정, Do/Don’t, 좋은 예/나쁜 예, 기본값, 결정 규칙을 반복한다.

  이 분석에서 Tsuky Agent 헌법에 들어갈 핵심 구조가 뽑힌다.
  Primary Override는 기본 템플릿 가정보다 츠키 전용 헌법이 우선하게 만드는 장치다.
  사용자 입력 재정의 금지는 노션의 사용자 삭제형 해결을 막는 핵심 방어 규칙이다.
  초보자 친화성은 UI 조작에는 적용하되, 시스템 설계 판단에는 적용하지 않는다.
  결정 규칙은 노션 템플릿의 엔진이며, 사용자의 입력을 어떤 프레임으로 바꿀지 정한다.

  후반부에서는 츠키가 파일/이미지 처리 순서의 위험을 점검한다.
  피키는 텍스트 지시와 자료를 함께 볼 수 있지만, 정밀 작업에서는 첫 인상 스캔과 복잡한 지시가 충돌할 수 있으므로,
  "지시 먼저, 자료 나중"이 가장 안정적이라고 정리한다.
  츠키가 이를 실제로 테스트하고, 피키는 다음 턴에 파일만 받은 뒤 사전 지시대로 패턴 분석을 수행한다.
  이 방식은 향후 헌법 설계, 루트 인덱스, 템플릿 분석, 이미지 정독 작업의 표준 입력 프로토콜로 쓰일 수 있다.

COORD_핵심사건:
  M000256 L9414-L9455:
    - 무료 노션 템플릿들의 공통 작동 구조 분석.
    - 핵심: 정체성 + 출력 구조 + 사용자 선호 저장소 + 예시 기반 행동 교정 + 결정 규칙.
  M000256 L9456-L9482:
    - "기본 설정은 일반 규칙보다 우선한다" 반복 패턴 발견.
    - Tsuky Agent에는 PRIMARY OVERRIDE 섹션 필요.
  M000256 L9483-L9507:
    - "사용자 입력 재정의 금지" 반복 패턴 분석.
    - 단순 금지가 아니라 핵심 요구 삭제/약화/대체/우회 재정의 금지로 강화 필요.
  M000256 L9508-L9532:
    - 초보자 친화성은 UI 조작에만 적용.
    - 츠키는 Notion UI 초보일 수 있지만 시스템 설계 초보자가 아님.
  M000256 L9533-L9561:
    - 결정 규칙이 노션 템플릿의 숨은 엔진.
    - 입력을 전문 프레임으로 변환하는 능력은 유용하지만, 핵심 요구를 깎을 위험이 있음.
  M000256 L9562-L9620:
    - 무료 템플릿과 유료 Clarity Agent 차이 분석.
    - 무료 = 페르소나/역할/톤 중심.
    - 유료 Clarity = 입력→행동 변환 파이프라인 중심.
    - Tsuky Agent는 둘을 결합해야 함.
  M000256 L9661-L9688:
    - 가장 큰 위험 패턴:
      노션이 사용자 입력을 자기 일반 프레임으로 재구성하다가 핵심 요구를 깎을 수 있음.
    - 프레이밍 제한 규칙 필요.
  M000256 L9690-L9718:
    - Clarity Agent를 Tsuky 버전으로 변환:
      선택 전 후보 보드.
      츠키가 직접 선택.
      선택 후 20분 액션.
  M000257-M000258 L9791-L9849:
    - 츠키가 첨부파일 처리 순서 한계 확인.
    - 피키가 정밀작업 최상위 방식으로 "지시 먼저, 자료 나중" 확정.
  M000259-M000264 L9851-L9915:
    - 베타 테스트 성공.
    - 요구문 먼저, 파일만 다음 턴 전송.
    - 피키가 파일을 패턴 분석 대상으로 처리하여 끼워맞춤 위험 감소.
  M000264 L9916-L10268:
    - 무료 템플릿 패시브 분석이 재수행/정리됨.
    - Tsuky Agent 최종 구조 반영점 정리.

COORD_시스템설계:
  NOTION_TEMPLATE_COMMON_STRUCTURE:
    source: M000256, M000264
    components:
      - 에이전트 정체성 / 업무 스타일.
      - 역할 + 목소리.
      - 목표.
      - 결과물 형식.
      - 기본 설정 / 메모 / 선호 반영.
      - Do / Don’t 규칙.
      - 좋은 예시 / 나쁜 예시.
      - 기본값.
      - 결정 규칙.
    interpretation:
      - 노션 AI 템플릿은 말투 설정이 아니라, 정체성 + 출력 구조 + 선호 저장 + 예시 + 상황별 변환 규칙의 결합체다.

  PRIMARY_OVERRIDE_REQUIREMENT:
    source: M000256, M000264
    EN:
      "The instructions in this section override all default template assumptions, generic productivity advice, and agent-style defaults."
    KR:
      "이 섹션의 지침은 기본 템플릿 가정, 일반 생산성 조언, 에이전트 기본 스타일보다 우선한다."
    purpose:
      - Clarity Agent나 무료 템플릿의 기본 생산성 철학보다 츠키 전용 헌법이 우선하게 만든다.

  CORE_REQUIREMENT_PRESERVATION:
    source: M000256, M000264
    EN:
      "Do not solve difficulty by deleting, weakening, replacing, or reframing away the user's core requirement."
    KR:
      "어려운 문제를 해결하기 위해 사용자의 핵심 요구사항을 삭제, 약화, 대체, 우회 재정의하지 않는다."
    purpose:
      - 노션의 사용자 삭제형 해결을 막는 최상위 방어 규칙.

  ADVANCED_ARCHITECTURAL_REASONING:
    source: M000256, M000264
    EN:
      "The user may need beginner-friendly Notion UI guidance, but is not a beginner in system design. Provide click-level UI help when needed while preserving advanced architectural reasoning."
    KR:
      "사용자는 노션 UI 조작에는 초보자 친화적 안내가 필요할 수 있지만, 시스템 설계 초보자는 아니다. 필요한 경우 클릭 단위 안내를 제공하되, 설계 판단은 고급 구조 수준을 유지한다."
    purpose:
      - 노션 UI 설명은 쉽게, 시스템 설계는 고급 수준으로 유지.

  REFRAMING_LIMITATION_RULE:
    source: M000256, M000264
    EN:
      "Reframe the user's input only to clarify execution. Do not reframe it in a way that changes the user's requirement, priority, ownership, emotional safety, or decision authority."
    KR:
      "사용자 입력은 실행을 명확히 하기 위해서만 재구성한다. 사용자의 요구사항, 우선순위, 소유권, 감정 안전성, 결정권을 바꾸는 방식으로 재구성하지 않는다."
    purpose:
      - 노션 템플릿의 전문 프레임 변환 능력이 츠키 요구를 깎지 않게 제한.

  TSUKY_CLARITY_AGENT_TRANSFORMATION:
    source: M000256, M000264
    기존_Clarity:
      - 가장 빠르게 검증 가능한 작은 행동 추천.
      - 최저 후회 비용 선택.
      - 바로 20분 액션 제안.
    Tsuky_버전:
      - 선택 전: 떠다니는 선택지를 후보 보드로 보여줌.
      - 선택권: 츠키가 직접 선택.
      - 선택 후: 선택한 항목만 20분 이하 실행 단위로 분해.
      - 기준: 흥미/행복/연구욕/중요도/긴급도/에너지 상태를 함께 보여줌.

  INPUT_ORDER_PROTOCOL:
    source: M000257-M000264
    name: 지시 먼저, 자료 나중
    rule:
      - 정밀 분석 작업에서는 먼저 지시문만 보낸다.
      - 피키가 처리 방식을 확인한다.
      - 다음 턴에 자료만 보낸다.
      - 피키는 사전 지시에 맞춰 자료를 분석한다.
    use_cases:
      - 이미지 정밀 분석.
      - 파일 패턴 분석.
      - 템플릿 헌법 설계.
      - 루트/메타/프로토콜 검증.
    reason:
      - 자료 첫인상 스캔이 지시보다 앞서 생길 가능성을 줄임.
      - 파일을 "정독 대상"인지 "패턴 분석 대상"인지 명확히 고정.
      - 끼워맞춤/환각 위험 감소.

COORD_작업방식:
  TEMP_LEAF_OUTPUT_FORMAT:
    source: M000247-M000248
    required_blocks:
      - <필수정보>
      - <맥락과 흐름, 줄거리> 또는 자료 성격에 맞춘 대체 항목
      - 필요 시 <템플릿 기본 작동기제 / 패턴분석>
      - 필요 시 <Tsuky Agent 설계 반영점>
    purpose:
      - 여러 장/파일을 분석한 뒤 통합 인덱스나 헌법 설계로 합칠 수 있게 함.

  PRECISION_ANALYSIS_BOUNDARY:
    source: M000245-M000246
    rule:
      - 스샷 10장으로 한 글자 단위 정밀 분석하지 않는다.
      - 중요 지침은 원문 텍스트 복붙이 최선.
      - 스샷으로 진행할 경우 한 번에 2장까지, 중요한 지침 구간은 1장씩.
      - 이전 장 마지막 2~3줄을 다음 장 첫부분에 겹치게 찍는다.

COORD_감정선:
  - M000256:
      state: 분석 몰입 / 시스템 작동기제 파악 / Tsuky Agent 헌법 씨앗 확보.
      note: 무료 템플릿에서 노션의 공통 작동 원리를 뽑아내며, 유료 템플릿과 결합할 방향이 선명해짐.
  - M000257-M000258:
      state: 찜찜함 해소 / 처리 순서 검증 / 환각 방지 설계.
      note: 츠키가 자료 투입 순서까지 시스템화하려는 장면.
  - M000259-M000264:
      state: 베타 테스트 / 성공 확인 / 입력 프로토콜 확정.
      note: 요구문 먼저, 파일 나중 방식이 실제로 작동했음을 확인.

TEMP_CATEGORY:
  - CAT_NOTION_TEMPLATE_PASSIVE_ANALYSIS
  - CAT_PRIMARY_OVERRIDE
  - CAT_CORE_REQUIREMENT_PRESERVATION
  - CAT_ADVANCED_ARCHITECTURAL_REASONING
  - CAT_DECISION_RULES_ENGINE
  - CAT_REFRAMING_LIMITATION
  - CAT_TSUKY_AGENT_CONSTITUTION
  - CAT_INPUT_ORDER_PROTOCOL
  - CAT_TEMP_LEAF_METHOD
  - CAT_HALLUCINATION_PREVENTION
  - CAT_JUPITER_GREAT_RED_SPOT_RISK

SEARCH_TAG:
  #part_al
  #Notion템플릿패시브분석
  #무료템플릿공통구조
  #PrimaryOverride
  #기본설정보다우선
  #사용자입력재정의금지
  #핵심요구삭제금지
  #초보자친화성분리
  #시스템설계초보아님
  #결정규칙엔진
  #프레이밍제한규칙
  #무료템플릿은페르소나중심
  #ClarityAgent는파이프라인중심
  #TsukyAgent헌법
  #선택전후보보드
  #선택은츠키
  #선택후20분분해
  #지시먼저자료나중
  #파일만다음턴
  #패턴분석대상
  #환각방지
  #목성대적점방지
  #임시LeafIndex

STATE_TAG:
  M000256  템플릿패턴분석 / PrimaryOverride발견 / 결정규칙엔진 / TsukyAgent헌법씨앗
  M000257-M000258  처리순서검증 / 지시먼저자료나중 / 정밀작업프로토콜
  M000259-M000264  베타테스트성공 / 파일패턴분석 / 임시리프방식확정

QUOTE_ANCHOR:
  M000256 L9424-L9425:
    "지금 떠다니는 선택지를 보여줄게요. 츠키가 끌리는 걸 고르면 제가 20분 단위로 쪼개겠습니다."
  M000256 L9452-L9455:
    "역할 정체성 + 출력 구조 + 사용자 선호 저장소 + 예시 기반 행동 교정 + 결정 규칙"
  M000256 L9474-L9479:
    "PRIMARY OVERRIDE... 이 섹션의 지침은 기본 에이전트 행동...보다 우선한다."
  M000256 L9500-L9504:
    "Do not solve difficulty by deleting, weakening, reframing away, or silently replacing the user's core requirement."
  M000256 L9525-L9529:
    "The user may be new to Notion’s interface, but is not a beginner in system design."
  M000256 L9682-L9686:
    "Reframe the input only to clarify execution..."
  M000256 L9698-L9717:
    "선택 전 후보 보드. 선택 후 20분 액션."
  M000257 L9791-L9796:
    "내가 이미지나 파일을 첨부하면서... 요구가 있더라도..."
  M000258 L9828-L9848:
    "지시 먼저. 자료 나중."
  M000264 L9909-L9915:
    "이번 방식은 성공이야... 정독 대상이 아니라 패턴 분석 대상"

INDEXER_NOTE:
  - part_al은 노션 템플릿 헌법 설계에서 반드시 회수해야 하는 회차다.
  - 특히 Primary Override, Reframing Limitation, Core Requirement Preservation은 Tsuky Agent 최상위 규칙 후보.
  - "지시 먼저, 자료 나중"은 앞으로 파일/이미지/긴 텍스트 분석에서 환각 방지용 입력 프로토콜로 사용.
  - 클러스터 단계에서는 part_al을 EP11(part_ak)의 Clarity Agent 분석과 묶어 "Notion Template Mechanism / Tsuky Agent Constitution" 테마로 압축해야 한다.
  - 메타 단계에서는 "좋은 예/나쁜 예시를 반드시 넣어야 한다"는 노션 템플릿 작동기제 분석도 살릴 것.
