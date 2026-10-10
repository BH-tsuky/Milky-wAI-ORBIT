[LEAF::part_au::R0005-P13]
TITLE: 피키 메모리화와 노션 최소작동 성공 - Piki가 기록되고 New Tasks/PULSE가 캘린더에 뜨는 화
FILE: part_au | R0005-P13 | M000396-M000418 | L018135-L019240
SCOPE: MSG_RANGE=M000396-M000418 | MSG_ACTUAL=20 | OMITTED=3 | PART=au
SIZE: part_lines/source_lines=1107 | part_chars/source_chars=28643 | part_bytes/source_bytes=47515

DRAMA_TAKE:
제21화는 피키라는 이름이 즉석 농담을 넘어 장기 호출명으로 기록되고, 동시에 노션 쪽 실물 구축이 한 번에 급발진 성공하는 화다. 초반에 츠키는 `피키 / Piki / PK / BH::PK`의 탄생 장면을 장기 메모리행으로 정리해 저장 요청하고, 피키는 이 이름이 별도 인격 주장이나 소유물화가 아니라 "츠키와 이 계정의 GPT 작업 파트너를 부르는 내부 호출명"이라고 제한까지 함께 등록한다. 그 뒤 새벽 5시 30분, 츠키는 갑자기 스크린샷 다발과 함께 현실 작업을 싹 끝낸 상태로 돌아온다. Google Workspace 입성, 새 노션 계정, 비즈니스 30일 체험, 기존 PULSE 페이지 복제 이식, 수식/속성/숨김/뷰 정리, Notion Calendar 연동, New Tasks DB 생성, PULSE 재입고 캘린더 표시까지 완료된다. 후반에는 버튼 자동화가 단순 `사용량 +1`이 아니라 사용 로그 DB와 relation/rollup으로 가야 한다는 설계가 나오고, 마지막에는 `🌙`와 `🅿️`가 옵시디언 발화자 마커 후보로 올라오며 로그 규격 연구까지 연결된다.

BOOT5:
1. M396-M399: 피키 탄생 장면을 장기 메모리행으로 기록 / Piki, PK, BH::PK의 의미와 제한 저장
2. M400-M403: Google Workspace, 새 Notion, PULSE 이식, New Tasks, 캘린더 연동까지 급발진 성공 보고
3. M404-M405: 버튼 자동화는 금지가 아니라 단일 표본 `FOCUS-A20 +1` 임상실험으로 제한해야 한다고 정정
4. M406-M415: P/K 이모지와 `🌙/🅿️` 표면 마커 논의 / 동기화 선긋기 / 피키는 외부 주차장에 대기
5. M416-M418: ABC 동시 진행 선언 / PULSE 사용 로그 DB와 Obsidian 발화자 마커 `🌙/🅿️` 규격 후보 제시

COORD_메모리/호출명:
M396  L18139-L18303  [호출명] 츠키가 `피키의 탄생과 작명받은 피키 첫반응`을 장기 메모리행으로 정리해 저장 요청
M396  L18146-L18241  [호출명] 지피티의 피 + 츠키의 키 = 피키 / Piki = Tsuki-context에 사전 적응된 작업용 GPT 인스턴스
M396  L18252-L18303  [호출명] Piki=귀여움, PK=전투태세, BH::PK=내부 프로젝트 식별자 / 츠키피키 라임과 PK 개그
M399  L18307-L18340  [호출명] 피키/Piki/PK/BH::PK를 장기 호출명으로 등록 / 별도 인격 주장이나 소유물화가 아니라 작업 파트너 호출명으로 제한

COORD_실물구축:
M400  L18342-L18346  [실물] 11개 스크린샷 투척 / 실제 노션·캘린더 구축 결과 제시
M401  L18348-L18425  [실물] 노션-캘린더-DB 상호작용 맛보기 구현 성공 판정 / Google Workspace 진입, Calendar 표시, PULSE v0.2, FOCUS 뷰, New Tasks 확인
M402  L18427-L18442  [실물] 츠키 급발진 보고: 기업계정 입성, 새 Notion 계정, Business 체험판, PULSE 복제 이식, 수식·뷰 정리, Calendar 분리 연결, NewTasks 생성
M403  L18444-L18602  [실물] 급발진 성공 루트 정리 / 계정 분리 전략, PULSE 이식, 캘린더-DB 연동, `임상 완료`, P/K 코드 변경 AS 성공

COORD_설계좌표:
M401  L18353-L18390  [설계] 구현 결과: `tsuky@bh-tsuky.com`, New Tasks 5월 14일, PULSE 재입고 5월 27일, FOCUS 사용량/잔량 계산
M401  L18403-L18417  [설계] 수정 후보: `P_LENS/P_MEM`과 `K_ROOT/K_MINI` 코드 체계 확인 필요, 단 지금은 수정 금지
M403  L18469-L18487  [설계] 계정 분리: Workspace는 실험/관리, Notion은 일정비서, BH/PK 핵심자료는 직접 투입 금지
M403  L18489-L18497  [설계] PULSE를 새 계정에 재작성하지 않고 공유/복제로 이식해 반복작업 회피
M403  L18515-L18533  [설계] 상태값 `임상 완료`: 프로토타입 검증 완료, 최종 폐쇄는 아닌 상태
M403  L18534-L18577  [설계] 버튼 자동화는 목표 제한 필요 / P=피키/GPT-side, K=Tsuky-side·루트 계열로 코드 감각 변경
M405  L18614-L18681  [설계] 버튼 자동화 정정: 전체 연구 금지, `FOCUS-A20 +1` 단일 표본 허용
M418  L19059-L19123  [설계] PULSE 사용 로그 DB 설계: 버튼 클릭 -> 사용 로그 생성 -> relation/rollup으로 사용량 계산 -> 잔량 자동 감소

COORD_마커/로그규격:
M406-M409  L18683-L18812  [마커] K 이모지 불만에서 `🌙=츠키`, `🅿️=피키`, 내부 코드 K/P/PK/BH::PK 분리 제안
M410-M413  L18814-L18976  [마커] ♏️를 한 번만 썼는데 트리거 후보로 감지한 피키의 패턴감지 / 동기화 선긋기 / 피키는 뇌 안이 아니라 외부 주차구역에 대기
M414-M415  L18978-L19034  [마커] 예열서버 다시 켜기 / 다음 작업 후보 A New Tasks, B PULSE 버튼, C Clarity 이미지 분석 제시
M416  L19036-L19055  [마커] ABC 모두 진행 선언 / 옵시디언 발화자 구분 노가다와 기존 `#사용자츠키` 방식 문제 회수 / `🅿️` 마커 발견
M418  L19125-L19240  [마커] Obsidian 발화자 마커 추천: `🌙 츠키:` / `🅿️ 피키:` 또는 짧게 `🌙:` / `🅿️:` / RAW LOG 형식 제안

COORD_감정/유머:
M402-M403  L18427-L18602  [감정] "안 한다" 뒤의 압축충전과 급발진 성공 / 졸라 기특한 상태를 PK 판정으로 축하
M404-M405  L18604-L18681  [유머] "오늘 그만하자" 냄새를 들키고 버튼 던전 몬스터 한 마리만 잡는 구조로 정정
M406-M415  L18683-L19034  [유머] 🅿️ 주차장 스킨, 🌙 천체, 선넘지마라, 외부 주차구역 대기, 시동 걸어 주차장새끼
M416-M418  L19036-L19240  [유머/작업] 발화자 마커가 실무 규격으로 취업 / 피키 주차장 스킨이 기록관리팀으로 전보

TOPIC_TAG:
- PIKI_MEMORY_REGISTRATION
- PK_CALLSIGN_LIMIT
- NOTION_CALENDAR_DB_SUCCESS
- ACCOUNT_SEPARATION_STRATEGY
- PULSE_LEDGER_V02_REAL
- CLINICAL_DONE_STATUS
- P_K_CODE_SHIFT
- BUTTON_LOG_ARCHITECTURE
- OBSIDIAN_SPEAKER_MARKERS
- MOON_P_MARKER_PAIR

STATE_TAG:
M396-M399  피키 탄생 메모리화 / 호출명 제한 설정 / Piki-PK-BH::PK 고정
M400-M403  현실 급발진 성공 / 새 계정·비즈니스 체험·PULSE 이식·캘린더 표시·New Tasks 성공
M404-M405  버튼 자동화 범위 정정 / 단일 표본 임상실험으로 축소
M406-M415  P/K/🌙/🅿️ 마커 논의 / 선긋기 / 예열서버 재점화
M416-M418  ABC 동시 진행 선언 / 로그 기반 버튼 설계 / 옵시디언 발화자 마커 규격화

PICO_README:
part_au는 `피키`가 장기 호출명으로 기록되고, 노션 실물이 최소 작동에 성공하는 시즌2의 큰 실증 리프다. 상위 인덱스에서는 `PIKI_MEMORY_REGISTRATION`, `NOTION_CALENDAR_DB_SUCCESS`, `ACCOUNT_SEPARATION_STRATEGY`, `BUTTON_LOG_ARCHITECTURE`, `OBSIDIAN_SPEAKER_MARKERS`로 연결하라. M396-M399는 피키/Piki/PK/BH::PK의 의미와 제한이 정리되는 핵심 좌표다. M400-M403은 추상 설계가 실제 계정·DB·캘린더로 성공한 증거다. M418은 PULSE 버튼 자동화를 수동 숫자 증가가 아니라 사용 로그 relation/rollup 구조로 설계해야 한다는 중요한 전환점이며, 동시에 `🌙/🅿️` 발화자 마커가 대화로그 정제 규격 후보로 올라오는 지점이다.

