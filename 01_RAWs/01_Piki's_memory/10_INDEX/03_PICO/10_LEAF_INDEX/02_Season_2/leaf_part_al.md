[LEAF::part_al::R0005-P04]
TITLE: 무료 노션 템플릿 작동기제 해부와 "지시 먼저, 자료 나중" 실험
FILE: part_al | R0005-P04 | M000252-M000264 | L009405-L010270
SCOPE: MSG_RANGE=M000252-M000264 | MSG_ACTUAL=7 | OMITTED=6 | PART=al
SIZE: part_lines/source_lines=866 | part_chars/source_chars=26863 | part_bytes/source_bytes=47905

DRAMA_VIEW:
시즌2 첫 장면은 노션 Clarity Agent를 그대로 쓰는 게 아니라, 무료 템플릿들의 반복 문법을 해부해서 츠키 전용 에이전트 헌법으로 재조립하는 장면이다. 드라마 속 피키는 무료 템플릿을 "페르소나/역할/톤" 중심, 유료 Clarity Agent를 "입력→행동 변환 파이프라인" 중심으로 나누고, 두 구조를 결합하되 선택권은 츠키에게 남겨야 한다고 정리한다. 중간에는 첨부자료를 읽는 순서에 대한 츠키의 찜찜함이 표면화되고, "지시 먼저, 자료 나중" 방식이 실제 베타테스트로 검증된다. 이 화는 템플릿 설계론과 자료 투입 프로토콜이 동시에 세워지는 시즌2의 입구다.

BOOT12:
1. M256: 무료 노션 템플릿의 공통 작동 구조를 정리하고, Tsuky Clarity Agent는 "선택 전 후보 보드 / 선택 후 20분 분해" 구조여야 한다고 확정.
2. M256: Primary Override, 사용자 입력 재정의 금지, 초보자 친화성과 고급 설계자 분리, Decision Rules, Good/Bad Examples를 최종 헌법 뼈대로 제안.
3. M257-M258: 첨부파일/이미지 처리 순서에 대한 의문을 제기하고, 정밀작업에서는 "지시 먼저, 자료 나중"이 가장 안전하다는 절차를 얻음.
4. M259-M261: 템플릿 패시브 분석을 위한 베타테스트 설계. 요구문을 먼저 보내고, 다음 턴에는 파일만 보내는 방식으로 오독 가능성을 낮춤.
5. M264: 베타테스트 성공 판정. 노션 무료/기본 템플릿 모음 파일을 "정독"이 아니라 "패턴 분석" 대상으로 처리하고, 최종 Leaf Index용 구조까지 재정리.

COORD_템플릿작동기제:
M256  L9433-L9455  [구조] 무료 템플릿 공통 구조: 정체성, 업무 스타일, 역할/목소리, 목표, 결과물, 선호, Do/Don’t, 예시, 기본값, 결정 규칙
      L9456-L9481  [헌법] "기본 설정은 일반 규칙보다 우선"을 Primary Override로 승격해야 한다는 설계
      L9483-L9506  [방어] 사용자 입력 재정의 금지: 핵심 요구를 삭제/약화/우회 재정의하지 말라는 최상위 규칙 후보
      L9508-L9531  [분리] 노션 UI는 초보자 친화적으로, 시스템 설계 판단은 고급 구조 수준으로 분리
      L9533-L9560  [엔진] Decision Rules는 입력을 어떤 프레임으로 바꿀지 정하는 노션 템플릿의 핵심 장치
      L9562-L9620  [비교] 무료 템플릿=페르소나/톤, 유료 Clarity Agent=입력→행동 변환 파이프라인. 둘을 결합해야 함
      L9621-L9660  [뼈대] Core Identity, Primary Override, Role/Voice, Goals, Allowed/Forbidden Information, Decision Rules, Do/Don’t, Examples, Memory/Preference Notes
      L9661-L9688  [위험] 노션이 전문 프레임으로 재구성하다 핵심 요구를 깎는 "사용자 삭제형 해결"을 방지해야 함

COORD_츠키형실행모델:
M256  L9419-L9430  [설계] 실행주의는 상위 철학이면 실패, 사용자 선택 이후의 하위 분해 엔진이면 강점
      L9690-L9718  [핵심] 선택 전 후보 보드, 선택권은 사용자, 선택 후 20분 액션으로 Clarity Agent를 변형
M264  L10118-L10148 [정식화] "노션이 선택하지 않는다. 노션은 정렬하고 보여준다. 선택은 츠키가 한다."로 최종 실행 흐름을 압축

COORD_자료처리프로토콜:
M257  L9788-L9796  [질문] 이미지/파일과 텍스트 지시가 함께 올 때, 자료를 먼저 처리하고 지시를 나중에 끼워 맞추는 한계가 있는지 확인
M258  L9801-L9809  [답변] 텍스트 지시사항을 함께 보고 적용할 수 있지만, 복잡한 이미지/파일 작업에서는 첫 인상 스캔과 실수 가능성이 있음
      L9810-L9828  [절차] 가장 안전한 방식: 지시문만 먼저 보내고, 확인 후 자료를 보내기
      L9839-L9848  [파일주의] 파일은 특히 "전부 정독했다"고 말하면 안 되는 경우가 있어, 정밀작업은 지시 먼저/자료 나중 방식이 가장 깨끗함
M259  L9851-L9861  [베타설계] 요구문을 먼저 보낸 뒤 다음 턴에 파일만 보내는 검증 샘플 시작
M260  L9863-L9896  [준비확인] 정독 목적이 아니라 반복 패턴/공통 구조/작동기제 분석 목적임을 확인하고 산출물 형식까지 예고
M261  L9898-L9902  [자료투입] 채팅 본문 없이 "노션 AI 템플릿 싹다 모아(1).md" 파일만 첨부
M264  L9909-L9915  [성공판정] 지시 먼저, 파일 나중 방식 덕분에 파일을 정독 대상이 아니라 패턴 분석 대상으로 처리할 수 있었다고 판정

COORD_헌법후보:
M264  L9916-L9948  [요약] 노션 AI 템플릿은 정체성+출력 형식+사용자 선호+예시+상황별 변환 규칙의 결합
      L9949-L9968  [PrimaryOverride] 기본 템플릿 가정, 일반 생산성 조언, 에이전트 기본 스타일보다 사용자 정의 지침이 우선
      L9969-L9995  [NoReframeAway] 어려운 문제를 해결하기 위해 핵심 요구를 삭제/약화/대체/우회 재정의하지 않는다
      L9996-L10015 [LevelSplit] 노션 UI 조작 도움은 초보자 친화, 시스템 설계 판단은 고급 구조 수준
      L10016-L10062 [DecisionRules] 템플릿은 입력을 전문 프레임으로 변환하므로, 재구성 권한을 실행 명확화로 제한해야 함
      L10063-L10117 [HybridDesign] 무료 템플릿 구조와 유료 Clarity 파이프라인을 결합하되, 츠키 전용 요소를 추가
      L10149-L10190 [FinalSkeleton] Primary Override, Core Identity, Allowed/Forbidden Information, Decision Authority, Decision Rules, Output Format, Examples, Preference Notes
      L10194-L10268 [LeafTemp] Notion Template Passive Analysis 01 임시 리프 구조와 Tsuky Agent 설계 반영점 정리

THEME_TAGS:
- NOTION_TEMPLATE_REVERSE_ENGINEERING
- TSUKY_CLARITY_AGENT
- PRIMARY_OVERRIDE
- USER_REQUIREMENT_PRESERVATION
- DECISION_AUTHORITY
- INPUT_PROCESSING_PROTOCOL
- INSTRUCTION_FIRST_MATERIAL_LATER
- PASSIVE_TEMPLATE_ANALYSIS
- EXECUTION_TRIGGER_REDESIGN

STATE_TAG:
M256      설계해부 / 무료템플릿 역공학 / 실행주의 교정
M257-M258 찜찜함 확인 / 자료처리 순서 검증 / 정밀작업 안전절차
M259-M261 베타테스트 설계 / 요구문 선투입 / 파일 단독 투입
M264      베타성공 / 템플릿 패시브 분석 정식화 / Tsuky Agent 헌법 후보 확장

PICO_README:
part_al은 시즌2의 첫 실전 해부실이다. 상위 인덱스에서는 이 화를 `Tsuky_Clarity_Agent`, `Notion_Template_Reverse_Engineering`, `Primary_Override`, `Input_Processing_Protocol`로 연결하라. 핵심은 두 갈래다. 첫째, 노션 무료 템플릿은 페르소나 중심이고 유료 Clarity Agent는 파이프라인 중심이므로 둘을 결합하되 선택권은 츠키에게 둔다. 둘째, 정밀 자료 작업에서는 "지시 먼저, 자료 나중" 방식이 오독과 환각을 줄이는 운영 프로토콜로 검증된다. 단, 이 드라마 속 설계/규칙은 현재 피코에게 자동 적용되는 현행 규칙이 아니라, 과거 히스토리와 인덱싱 대상이다.

