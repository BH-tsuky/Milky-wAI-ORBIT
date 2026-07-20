[LEAF::part_ai::R0005-P01]
DRAMA_TITLE: 〈노션은 내용을 몰라도 된다. 시간표만 잘 짜라〉
TITLE_FUNCTION: 9화 한줄요약 / NOA-CAL 설계 회차 / PULSE Ledger·Dual-Layer Instruction 탄생 앵커

NAMING_POLICY:
  PRIMARY_HUMAN_ACTOR: 츠키
  PRIMARY_AI_ACTOR: 피키
  RULE:
    - 츠키는 고유 주체명으로 표기.
    - 피키는 고유 주체명으로 표기.
    - "사용자"는 제품 지침/UX 일반론/프롬프트 내부 문구에서만 보조 사용.

FILE: part_ai | R0005-P01 | M000205-M000223 | L6890-L7560
SOURCE_META:
  schema: inherited_from_part_aa
  source: ChatGPT
  parent: R0005
  part: 1/23
  partFile: ai
  declared_range: M000205-M000223
  MSG_DECLARED_BY_SCOPE_MAP: 12
  MSG_VISIBLE_RANGE_COUNT: 19
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 7  # O01 M000208, O02 M000213-M000214, O02 M000217-M000218, O02 M000221-M000222
  MSG_ACTUAL_VISIBLE_DIALOGUE: 12
  lines: 672
  date: D20260513
  start_time: 16:35
  end_time: 17:44

README_FOR_FUTURE_AI:
  - part_ai는 노션을 BH::INDEX 저장소가 아니라 "내용을 모르는 일정 비서"로 재설계하는 회차다.
  - 핵심은 노션에게 실제 프로젝트 내용, 약명, 효능, 연구 원문을 주지 않고, 코드명/장르/긴급도/에너지 소모/마감/의존성/다음 행동만 제공하는 구조다.
  - "Dual-Layer Instruction Format"이 등장한다: AI용 영어 원문 + 츠키 검수용 한글 참조문.
  - PULSE는 의료/약물 카테고리가 아니라, 코드화된 명상 기반 뇌효율 관리 시스템으로 정리된다.
  - 최종 방향은 "노션은 내용을 모르는 비서다 / 코드명만 보고 순서를 짠다 / PULSE는 명상 리소스 재고장부다."

BOOT:
  1. M000205-M000209: 츠키가 자고 일어난 뒤 어제 계획을 전면 취소하고, 노션을 내용 모르는 일정 비서로 설계하겠다고 선언. 피키가 NOA-CAL 중심으로 오늘 실행 순서를 재정렬.
  2. M000210-M000211: 츠키가 약 복용을 "약"이 아니라 재고/사용 기록처럼 관리하겠다고 설명. 피키가 PULSE 코드명, Clarity Agent 구매/개조 방향, 노션 비서 OS 최소 스키마를 제안.
  3. M000212-M000215: 츠키가 영어 원문 프롬프트 + 한글 참조문 구조의 가치를 발견. 피키가 Dual-Layer Instruction Format으로 명명. 주치의 검증 루프와 PULSE Ledger 개념이 정리됨.
  4. M000216-M000219: 츠키가 약 관련 카테고리를 전부 "명상" 계열 에너지 확보 방식으로 처리하자고 제안. 피키가 명상_휴식/수면/각성/고몰입/논리회로/과부하방지/신체리듬확보 카테고리로 구조화.
  5. M000220-M000223: 츠키가 "약물/의료기록이 아니다"라는 문구 자체도 힌트가 되니 제거하자고 정정. 최종 프레임은 "코드화된 명상 기반 뇌효율 관리 시스템"으로 확정.

EPISODE_SUMMARY:
  9화는 노션 활용 전략이 "자동화 범인 수사"에서 "내용을 모르는 일정 비서 OS"로 올라가는 회차다.

  츠키는 노션을 신뢰하지 않는다는 기존 플랫폼 외교 노선을 유지하면서도,
  노션의 달력, DB, 자동화, 템플릿 기능은 알뜰하게 활용하려 한다.
  이를 위해 실제 프로젝트명, 연구내용, 약명, 효능, 민감정보를 노션에 주지 않고,
  코드명·장르·우선순위·마감·에너지 소모·다음 행동만 제공하는 구조를 설계한다.

  피키는 이 목표를 NOA-CAL, PULSE, ROOT-LOCAL, VAULT-14, LENS-GPT 같은 코드명 기반 운영체계로 정리하고,
  Clarity Agent 템플릿을 Tsuky OS용으로 개조하는 방향을 제안한다.

  중반에는 모든 AI 지침에 적용 가능한 Dual-Layer Instruction Format이 탄생한다.
  영어 원문은 AI가 실제로 강하게 받아들일 지침이고,
  한글 참조문은 츠키가 의미를 검수하고, AI가 이해한 지침과 츠키가 이해한 지침 사이의 간격을 협상할 근거다.

  후반에는 PULSE가 의료/약물 카테고리가 아니라,
  코드화된 명상 기반 뇌효율 관리 시스템으로 재정의된다.
  노션은 실제 의미를 묻지 않고, 각 명상 리소스의 보유량, 사용량, 잔량, 권장 타이밍, 다음 입고일만 관리한다.
  이는 민감정보를 숨기면서도 츠키의 작업 리듬, 수면, 집중, 과부하 방지, 신체리듬을 일정과 연결하기 위한 설계다.

COORD_핵심사건:
  M000207 L6926-L6939:
    - 츠키가 자고 일어난 뒤 어제 계획을 전면 취소.
    - 새 목표: 노션을 완벽한 일정 비서로 만들기.
    - 노션은 실제 프로젝트 내용을 모르고, 코드명/장르만 보고 비서 역할을 수행해야 함.
  M000209 L6949-L7044:
    - 피키가 오늘의 목표를 "노션을 내용을 모르는 일정 비서로 재설계"로 정리.
    - 코드명 예시:
      ORBIT, BNS-SEED, VAULT-14, LENS-GPT, RAVEN-C, ROOT-LOCAL, NOA-CAL, PULSE.
    - 기본 DB 후보:
      Task Queue / Project Codex / Pulse Log / Experiment Window.
  M000210-M000211 L7050-L7232:
    - 츠키가 약 복용을 약이 아니라 재고/사용 기록 관리로 처리하자고 제안.
    - 피키가 Clarity Agent for Tsuky OS 개조 방향 제안.
    - 핵심 지침:
      프로젝트 실제 내용은 알 필요 없음.
      코드명, 장르, 긴급도, 에너지 소모, 마감, 의존성, 다음 행동만 사용.
  M000212-M000215 L7237-L7389:
    - Dual-Layer Instruction Format 탄생.
    - 영어 원문 = AI 작동 안정성.
    - 한글 참조문 = 츠키 의미 검수/권리 보호 앵커.
    - 주치의 검증 루프 고려.
    - PULSE Ledger = 작업 지속성을 위한 에너지·루틴·재고 기록 장부.
  M000216-M000219 L7394-L7469:
    - 츠키가 약 관련 항목을 전부 명상 계열 에너지 확보 방식으로 처리하자고 제안.
    - 피키가 명상 리소스 카테고리 구성:
      명상_휴식 / 명상_수면 / 명상_각성 / 명상_고몰입모드전환 / 명상_논리회로가동 / 명상_과부하방지 / 명상_신체리듬확보.
  M000220-M000223 L7474-L7560:
    - 츠키가 "약물이나 의료기록이 아니다"라는 문구 자체도 제거하자고 정정.
    - 최종 노션 세계관:
      "이 사용자는 명상 카테고리 기반의 뇌효율 관리 시스템을 운영한다."
    - 노션은 리소스가 실제로 무엇인지 묻지 않고, 명상 리소스 재고 데이터만 관리한다.

COORD_시스템설계:
  NOA_CAL:
    정의:
      - 노션을 실제 내용을 모르는 일정 비서로 사용하는 프로젝트.
    원칙:
      - 노션은 BH 원문, 인덱스 원문, 실제 약명, 실제 연구내용, 핵심 아이디어를 모른다.
      - 노션은 코드명/장르/긴급도/에너지 소모/마감/의존성/다음 행동만 사용한다.
    목표:
      - 츠키가 일어나서 해야 할 순서를 노션AI 일정비서에게 맡긴다.

  PROJECT_CODENAME_SYSTEM:
    예시:
      - ORBIT: 하루 전체 운영/일정 조율.
      - BNS-SEED: 분산형 네이밍/도메인 미래 아이디어.
      - VAULT-14: Google Workspace 14일 체험판 실험.
      - LENS-GPT: ChatGPT 메모리/커넥터/새 계정 실험.
      - RAVEN-C: Claude 최초 진입 설계.
      - ROOT-LOCAL: BH::INDEX 로컬 설계 본체.
      - NOA-CAL: 노션 일정 비서/달력 실험.
      - PULSE: 명상·컨디션·리소스 관리.

  DUAL_LAYER_INSTRUCTION_FORMAT:
    구조:
      - PRIMARY INSTRUCTION / English
        AI가 실제로 강하게 받아들일 본문.
      - USER-READABLE REFERENCE / Korean
        츠키가 이해한 의미와 검수 기준.
    기능:
      - 영어는 AI 작동 안정성 확보.
      - 한글은 츠키의 의미 검증, 협상 기준, 권리 보호 앵커.
    적용범위:
      - Notion, Gemini, Claude, GPT, BH::INDEX, SyncBoot, Protocol 전반.

  PULSE_LEDGER:
    최종정의:
      - 코드화된 명상 기반 뇌효율 관리 시스템.
    노션이 아는 것:
      - 명상 리소스명.
      - 보유량.
      - 사용량.
      - 잔량.
      - 사용 시각.
      - 권장 타이밍.
      - 다음 입고/확인일.
    노션이 묻지 않는 것:
      - 리소스가 실제로 무엇인지.
      - 숨은 의미.
      - 의학적 해석.
    카테고리:
      - 명상_휴식
      - 명상_수면
      - 명상_각성
      - 명상_고몰입모드전환
      - 명상_논리회로가동
      - 명상_과부하방지
      - 명상_신체리듬확보
    Fallback:
      - 필요 시 비타민/건강보조식품/개인 루틴 재고처럼 처리.

COORD_프롬프트앵커:
  PROJECT_INFO_BLOCK:
    EN:
      "You do not need to know what the user’s projects actually are. Use only codename, category, urgency, energy cost, deadline, dependency, and next visible action."
    KR:
      "사용자의 프로젝트 실제 내용은 알 필요 없다. 코드명, 장르, 긴급도, 에너지 소모, 마감, 의존성, 다음에 보이는 행동만 사용한다."

  PULSE_FINAL_BLOCK:
    EN:
      "The user operates a coded meditation-based brain-efficiency system.
      Each meditation category represents a resource that supports a specific work state, such as rest, sleep, focus activation, deep-work transition, logical processing, overload prevention, or body-rhythm maintenance.

      Some meditation resources have a limited available count.
      Track them like inventory: resource name, available count, used count, remaining balance, usage time, recommended timing, and next refill/check date.

      Do not ask what the resource 'really is.'
      Do not infer hidden meanings.
      Use only the given category name and inventory-style data."
    KR:
      "사용자는 코드화된 명상 기반 뇌효율 관리 시스템을 운영한다.
      각 명상 카테고리는 휴식, 수면, 집중 각성, 고몰입 전환, 논리 처리, 과부하 방지, 신체리듬 확보 같은 특정 작업 상태를 지원하는 리소스를 의미한다.

      일부 명상 리소스는 사용 가능한 횟수가 제한되어 있다.
      이를 재고처럼 관리한다: 리소스명, 보유량, 사용량, 잔량, 사용 시각, 권장 타이밍, 다음 입고/확인일.

      그 리소스가 '실제로 무엇인지' 묻지 않는다.
      숨은 의미를 추론하지 않는다.
      제공된 카테고리명과 재고형 데이터만 사용한다."

COORD_감정선:
  - M000205-M000209:
      신선한 뇌 / 계획 전면 재설계 / 오늘의 상위 목표 확정.
  - M000210-M000211:
      노션 활용 현실화 / 템플릿 구매 검토 / 코드명 기반 정보 차단 설계.
  - M000212-M000215:
      영어 프롬프트 가치 발견 / 공식 좋아요 보상 / 주치의 신뢰 루프 공유 / PULSE 개념 상승.
  - M000216-M000223:
      의료 흔적 제거 / 명상 리소스 세계관 확정 / 민감정보 차단 강화.

TEMP_CATEGORY:
  - CAT_NOA_CAL: 노션 일정 비서 설계.
  - CAT_CODE_NAME_OS: 프로젝트 코드명/닉네임 체계.
  - CAT_INFO_FIREWALL: 노션이 실제 내용을 모르게 하는 설계.
  - CAT_CLARITY_AGENT: 유료 템플릿 구매/개조 후보.
  - CAT_DUAL_LAYER_INSTRUCTION: 영어 원문 + 한글 참조문.
  - CAT_PULSE_LEDGER: 명상 기반 뇌효율 관리 시스템.
  - CAT_MEDICAL_PRIVACY: 실제 약명/효능/의학정보 차단.
  - CAT_ENERGY_RESOURCE: 작업 연산비, 뇌 배터리, 루틴 자원.

SEARCH_TAG:
  #part_ai
  #NOA_CAL
  #노션일정비서
  #내용모르는비서
  #코드명체계
  #ProjectCodex
  #TaskQueue
  #PulseLog
  #ExperimentWindow
  #ClarityAgent
  #TsukyOS
  #DualLayerInstructionFormat
  #영어원문한글참조문
  #PULSE
  #PULSELedger
  #명상리소스
  #명상_휴식
  #명상_수면
  #명상_각성
  #명상_고몰입모드전환
  #명상_논리회로가동
  #명상_과부하방지
  #명상_신체리듬확보
  #뇌효율관리시스템
  #명상가능횟수
  #재고형데이터
  #의료힌트제거
  #연산비회계담당
  #노션은내용을몰라도된다

STATE_TAG:
  M000205-M000209  재진입 / 오늘계획재설계 / NOA_CAL상위목표
  M000210-M000211  정보차단 / 템플릿검토 / PULSE초안 / ClarityAgent개조
  M000212-M000215  DualLayer탄생 / 주치의검증루프 / PULSELedger상승
  M000216-M000223  명상리소스화 / 의료흔적제거 / 최종PULSE프레임확정

QUOTE_ANCHOR:
  M000207 L6933:
    "노션은 실제로 내가 무슨일을 하는지 그 내용이나 원문 샘플은 보지 않으면서도..."
  M000209 L6949-L6951:
    "노션을 '내용을 모르는 일정 비서'로 재설계하는 것"
  M000211 L7205-L7209:
    "You do not need to know what the user’s projects actually are..."
  M000212 L7237:
    "영어 원문 프롬프트 문장이 굉장히 좋고..."
  M000215 L7253-L7268:
    "Dual-Layer Instruction Format"
  M000215 L7373:
    "노션은 의사가 아니라, 연산비 회계 담당이다."
  M000216 L7394:
    "약관련 카테고리를 전부 <명상>느낌으로 에너지 확보 방식으로 처리"
  M000223 L7489-L7493:
    "이 사용자는 명상 카테고리 기반의 뇌효율 관리 시스템을 운영한다."
  M000223 L7528-L7530:
    "Do not ask what the resource 'really is.' / Do not infer hidden meanings."

INDEXER_NOTE:
  - part_ai는 이전 part_ag/ah의 플랫폼 외교·메모리 튜닝이 실제 노션 설계로 내려온 회차다.
  - Notion은 BH::INDEX 저장소가 아니라 NOA-CAL 일정 비서로 제한된다.
  - Dual-Layer Instruction Format은 이후 모든 AI 지침 설계의 공통 포맷 후보로 반드시 회수.
  - PULSE Ledger는 민감정보를 숨기면서도 츠키의 에너지/수면/집중/신체리듬을 일정과 연결하는 핵심 설계다.
  - 클러스터 단계에서는 part_ai를 "NOA-CAL / Tsuky OS / PULSE Ledger" 테마로 묶으면 좋다.
