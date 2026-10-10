[LEAF::part_bx::R0009-P04]
FILE: part_bx | R0009-P04 | M001548-M001570 | L050181-L051503 | MSG_ACTUAL=18 | OMITTED=5
TITLE: AI Exporter 장애와 Tsuky Local Chat Exporter 노란불 검수

DRAMA_REVIEW:
49화가 Codex를 "피키와 분리된 로컬 실행자"로 세운 회차였다면, 50화는 그 실행자가 곧장 실전 위기 앞에 끌려 나오는 회차다. 기존 AI Exporter가 갑자기 죽었고, 츠키에게 중요한 건 화면에 남아 있는 원문 자체가 아니라 그 원문을 깨끗한 JSON/MD/TXT/옵시디언 재료로 회수하는 자동화 파이프라인이었다. 여기서 피키가 처음엔 "raw가 사라진 게 아니다" 쪽으로 문제를 잡았다가, 츠키의 교정 뒤에 바로 "clean export pipeline obstruction"으로 진단을 재정렬하는 장면이 좋다. 이 드라마답게, 오답을 맞고 끝나는 게 아니라 오답을 발판으로 문제정의가 더 정확해진다.

중반부는 진짜 츠키식 인프라 연구의 냄새가 난다. "드래그 올"은 자동화가 아니라 인간을 자동화 부품으로 쓰는 말이라서 기각되고, 남의 확장 프로그램이 아니라 츠키 쪽 공식 Exporter/변환기 체계를 만들자는 3단 구조가 나온다. DOM RAW, HAR RAW, canonical/json/md/txt/obsidian 변환이라는 뼈대가 잡히지만, HAR는 쿠키와 세션 토큰이 섞일 수 있는 위험물로 격리된다. 후반부의 코드 검수는 피키가 잡상인 필터 역할을 제대로 하는 장면이다. `fetch`, `cookie`, `localStorage`, `Authorization` 같은 위험 냄새는 없지만, `innerHTML`, `fallback.mainText`, 전체 URL 저장, 부모 컨테이너 과잉수집 가능성 때문에 "실행 가능하지만 그대로는 비추천"이라는 노란불 판정이 나온다.

BOOT5:
1. M1548-M1555: AI Exporter가 "almost done" 뒤 실패하는 상황을 raw 소실이 아니라 clean export 파이프라인 장애로 재정의
2. M1556-M1562: Codex식 "drag all" 제안을 기각하고, DOM/HAR/RAW 변환기 기반의 츠키 공식 Exporter 구조로 방향 전환
3. M1563-M1566: `Tsuki AI Log Exporter` README와 `browser-dom-exporter.js`를 대상으로 실행 전 냄새검수 수행
4. M1567-M1568: DOM RAW 코드에서 외부전송은 없지만 `html`, `fallback.mainText`, 전체 URL, 넓은 selector가 과잉수집 위험으로 판정
5. M1569-M1570: 3단 요구 구조와 Codex 마커 후보가 정리되고, 다음 단계 `har_to_raw.py`는 "위험물 해체 검수"로 예고

COORD_Exporter장애/문제재정의:
M1548  L050185-L050189  [장애발생] Chrome AI Exporter가 맥북/아이맥 양쪽에서 갑자기 실패 / JSON, Markdown, Custom 모두 출력 불가
O02   L050191-L050191  [생략] M1549-M1550 생략 / 장애 진단 중간 구간
M1551  L050193-L050306  [초기진단] 피키가 raw 소실은 아니며, ChatGPT DOM/UI 변경 또는 확장 저장 단계 문제일 수 있다고 보고 백업 우선/삭제금지로 안내
M1552  L050308-L050312  [증상상세] "almost done"까지 갔다가 인터넷 문제처럼 실패한다는 출력단 증상 확인
M1553  L050314-L050404  [출력단가설] 추출은 거의 끝나고 마지막 저장/download/server/Chrome download 단계에서 실패하는 것으로 진단
M1554  L050406-L050410  [츠키교정] raw가 사라진 게 아니라 깨끗한 JSON/MD/TXT를 즉시 얻지 못하는 것이 핵심이라고 문제정의 교정
M1555  L050412-L050531  [재정의] 피키가 "clean export pipeline obstruction"으로 정정 / 확장과 싸우지 말고 공식 export 또는 자체 rebuilder로 가자고 제안

COORD_자체Exporter/드래그기각:
M1556  L050533-L050537  [Codex제안] 츠키가 Codex에게 브라우저 AI 대화 자동 export를 요청했으나, Codex가 "drag all"류 제안을 해 혼남
O03   L050539-L050539  [생략] M1557-M1559 생략 / Codex 제안 중간 정리 구간
M1560  L050541-L050630  [인간자동화기각] "Drag all"은 자동화가 아니라 인간을 자동화 부품으로 쓰는 것이라 기각 / 공식 export ZIP 또는 raw log/json 기반 rebuilder 요구
M1561  L050632-L050636  [요구범위] HAR는 쿠키/세션 위험, 부분 DOM은 불충분, 수동복사는 금지 / 자기완결 exporter 요구
M1562  L050638-L050744  [전용Exporter요건] DOM 기반 추출, 긴 대화 auto-scroll, JSON/Markdown/TXT/PKMD 출력, 첨부 메타, preview, no token/session/HAR 기본금지 등 요건 정리

COORD_README/코드냄새검수:
M1563  L050746-L050750  [README대기] Codex가 1차 툴킷을 만들었지만 아직 실행 전이며, README부터 냄새검수하기로 함
M1564  L050752-L050807  [검수체크리스트] 설치 방식, 권한, cookie/session/token, 외부전송, HAR/network, DOM only, 원본수정 여부, output format, autoscroll 점검 기준 제시
M1565  L050809-L050883  [README구조] `Tsuki AI Log Exporter`: DOM RAW 추출기, HAR→RAW, RAW→canonical/json/md/txt/obsidian 변환기, schema 3종, HAR 외부공유 금지 안내
M1566  L050885-L051040  [노란불예고] DOM route는 보존 가치가 있고 HAR route는 격리해야 하며, 실제 코드에서 위험 키워드와 과잉수집을 먼저 확인해야 한다고 판정

COORD_DOM코드/노란불판정:
M1567  L051043-L051237  [DOM코드] `browser-dom-exporter.js` 전체 코드 제시 / querySelector 후보 수집, auto-scroll, Blob 다운로드, html/fallback/mainText/source.url 저장 포함
M1568  L051239-L051362  [안전판정] 외부전송, cookie/session/token 직접 접근, 파일 삭제/수정은 없어 보이나, 자동스크롤/과잉수집/더러운 출력 위험으로 노란불
M1568  L051259-L051296  [삭제권고] `html: el.innerHTML`, `fallback.mainText`, 전체 `source.url` 제거 권고 / role, text, selectorHint, capturedAt, snapshots, title 유지
M1568  L051302-L051327  [컨테이너중복위험] 넓은 selector 때문에 메시지 하나가 아니라 부모 대화 컨테이너까지 message로 잡을 수 있는 위험 지적
M1568  L051329-L051361  [수정방향] data-message-author-role 우선, 20000자 이상 후보 제외/flag, unknownMessages 분리, 원본 페이지 수정 없이 다운로드만 유지 제안

COORD_3단구조/다음검수:
M1569  L051364-L051388  [요구재확인] 츠키가 공식 Exporter → 복사 RAW → 3단 변환기 요구였고, Codex가 DOM RAW/HAR RAW/변환기 4종을 만들었다고 설명
M1569  L051371-L051387  [코덱스마커] 코덱스 마커 후보를 던지며, 다음엔 2단계 `har_to_raw.py` 코드를 보내겠다고 예고
M1570  L051390-L051502  [HAR검수준비] 피키가 3단 구조를 이해하고, HAR 변환기는 cookie/authorization/bearer/set-cookie/csrf/session/access_token 등을 훨씬 엄격하게 봐야 한다고 정리
M1570  L051449-L051501  [마커추천] Codex 대표 마커로 `⌨️` 추천 / 작업 키보드 앞 실행자라는 의미로 피키·츠키 마커와 구분

STATE_TAG:
M1548-M1555  Exporter장애 / 문제정의교정 / clean-export-pipeline / rebuilder전환
M1556-M1562  drag-all기각 / 공식Exporter구상 / DOM-HAR-RAW변환기 / 자기완결자동화
M1563-M1568  README검수 / DOM코드검수 / 외부전송없음 / 과잉수집노란불 / 수정후실행
M1569-M1570  3단구조확정 / HAR위험물검수예고 / Codex마커정리

TOPIC_TAG:
AI-Exporter, Tsuki-AI-Log-Exporter, browser-dom-exporter, HAR, raw-dom-json, canonical-json, obsidian-md, clean-export-pipeline, DOM-extraction, autoscroll, Blob-download, innerHTML, fallback-mainText, source-url, cookie-token-safety, Codex-marker

UPPER_INDEX_HINT:
- META_RAW_RECOVERY_INFRA: 기존 AI Exporter 장애가 츠키 전용 Exporter/변환기 구축 필요성을 폭발시킨다. 이후 RAW 자동화와 츠키MD 규격 연구의 직접 선행 사건.
- META_SAFETY_PROTOCOL: 실행 전 README/코드 냄새검수, 외부전송/쿠키/세션/HAR 격리, 원본 수정 금지, 과잉수집 제거는 도구 도입 안전 프로토콜의 핵심.
- META_AUTOMATION_PHILOSOPHY: "drag all" 기각은 인간을 자동화 부품으로 쓰지 않는다는 츠키식 자동화 철학을 선명하게 보여준다.
- META_CODEX_ROLE: Codex는 도구를 만들 수 있지만, 피키는 그 도구를 실행 전 검수하고 위험물을 분리하는 설계/문지기 역할을 맡는다.

UNRESOLVED:
- `browser-dom-exporter.js`는 외부전송 위험은 낮아 보이나, `innerHTML`, `fallback.mainText`, 전체 URL 저장, 넓은 selector 문제를 수정하기 전 실행은 비추천이다.
- `har_to_raw.py`는 아직 본문 검수 전이며, HAR 특성상 쿠키/세션/토큰/Authorization 처리 여부가 다음 화의 핵심 위험지점이다.
- Codex 대표 마커는 `⌨️` 추천으로 제시되었지만, 최종 확정 여부는 이후 츠키 선택을 봐야 한다.

PICO_README:
제50화는 AI Exporter 장애가 츠키 전용 로그 회수 인프라로 전환되는 회차다. 나중에 Tsuky AI Log Exporter, DOM RAW, HAR 위험, clean export pipeline, drag all 기각, `browser-dom-exporter.js`, 과잉수집 노란불, Codex 마커 `⌨️`를 말하면 이 화를 찾아라. 핵심은 "raw를 잃은 게 아니라 깨끗한 회수 파이프라인이 막혔고, 남의 확장 대신 츠키 쪽 공식 추출기/변환기를 만들자"이다.

