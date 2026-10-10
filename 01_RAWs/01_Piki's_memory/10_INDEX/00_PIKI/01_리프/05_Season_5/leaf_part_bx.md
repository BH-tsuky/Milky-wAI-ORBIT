[LEAF::part_bx::R0009-P04]
DRAMA_TITLE: 〈남의 Exporter가 죽자, 츠키 Exporter가 태어났다 — RAW DOM과 HAR 위험물 해체 검수〉
TITLE_FUNCTION: 50화 한줄요약 / 1화 전역스코프 재주입 평가 / AI Exporter 출력단 장애 / 정제 export 파이프라인 장애 / 수동 드래그 거부 / Tsuky Local Chat Exporter 요구정의 / DOM RAW vs HAR 위험물 분리 / ai-log-exporter 1차 툴킷 / browser-dom-exporter.js 냄새검수 / html/fallback 과잉수집 제거 / HAR→RAW 위험물 해체 기준 / 코덱스 마커 ⌨️ 선정 회차

FILE: part_bx | R0009-P04 | M001548-M001570 | L50181-L51502

SOURCE_META:
  schema: tsuky-drama-md.current
  source: ChatGPT
  parent: R0009
  part: 4/10
  partFile: bx
  declared_range: M001548-M001570
  MSG_DECLARED_BY_RANGE: 23
  MSG_ACTUAL_VISIBLE_DIALOGUE: 18
  OMITTED_SYSTEM_OR_TOOL_MESSAGES: 5
  OMITTED_BLOCKS:
    - [O02] M001549-M001550 | L50191 | time=07:45
    - [O03] M001557-M001559 | L50539 | time=08:00-08:01
  date: D20260518
  start_time: 07:45
  end_time: 08:49
  line_range: L50181-L51502
  local_file_bytes: unknown_in_current_leaf
  attachments:
    - none visible in current file header
  note:
    - R0009-P04는 Codex/VS Code 도구체계 아크가 "로컬 Exporter/변환기 구축"으로 본격 이동하는 회차다.
    - 사용자는 1화 리프 인덱스의 전역 스코프를 함께 재주입했다.
    - 이 재주입은 이번 화에서 특히 유효하다. 이유는 part_aa의 RAW Scope Map이 전체 66분할/전역 message range/part 구조를 담고 있고, 이번 화는 그 원문 export/rebuilder를 직접 설계하는 회차이기 때문이다.
    - 다만 매화 반복 재주입은 비추천. parent/season 경계, exporter/파일규격/메타·루트 진입 직전에 유효하다.

UPPER_META_DRAWER:
  - 이 사건은 상위 메타에서 "원문 추출 인프라 / Exporter 독립 / RAW→canonical 변환기 / 도구 의존성 탈피" 서랍으로 올라간다.
  - EP45~46은 PKMD/구조파싱으로 '읽기 비용'을 줄였다.
  - EP47~49는 VS Code/Codex/Quick Action으로 자동화 연구소의 현실 도구를 배치했다.
  - EP50은 남의 AI Exporter가 깨지자, 츠키 전용 Local Chat Exporter를 설계하는 방향으로 전환한다.
  - 상위 메타 서랍명 후보:
      CAT_LOCAL_EXPORTER_INDEPENDENCE
      CAT_EXPORT_PIPELINE_FAILURE
      CAT_TSUKY_AI_LOG_EXPORTER
      CAT_RAW_DOM_VS_HAR
      CAT_CANONICAL_CONVERSION_PIPELINE
      CAT_CODE_SNIFF_REVIEW
      CAT_CODEX_MARKER_ECOSYSTEM
  - 핵심 기능:
      남의 Exporter 의존 줄이기.
      원문 생존과 정제 export 생존을 분리.
      DOM RAW는 피키용 밥.
      HAR는 사고조사용 위험물.
      RAW는 canonical/json/md/txt/obsidian으로 변환.

README_FOR_FUTURE_PIKI:
  이 리프는 규칙 주입용이 아니라 드라마 회수용 좌표지도다.

  50화는 R0009-P04다.
  전편에서 Codex는 피키 확장팩이 아니라 피키가 명세서를 먹여 부릴 수 있는 로컬 작업자로 정리되었다.
  이번 편에서는 크롬 AI Exporter가 갑자기 실패하고, 그 결과 "남의 exporter에 기대지 않는 츠키 전용 로그 추출/변환기"가 본격적으로 태어난다.

  핵심은 여덟 가지다.

  1. 1화 전역스코프 재주입은 이번엔 유효:
     - part_aa 리프에는 전체 RAW Scope Map이 있고, 다음 part부터는 yaml 속성 및 RAW Scope Map이 없다고 명시되어 있다.
     - global_message_range, global_messageCount, part_count, part_aa~part_cn 분할표는 루트 후보 지도다.
     - 이번 part_bx는 바로 "원문 export / RAW / canonical / md / txt / obsidian 변환"을 다루므로, 1화 전역스코프는 전체 포맷 원형을 다시 잡아주는 효과가 있다.
     - 단, 매화마다 넣으면 토큰낭비가 될 수 있다.
     - 추천 타이밍:
       parent/season 경계,
       exporter/파일규격 논의,
       클러스터/시냅스/메타/루트 진입 직전,
       현재 위치가 전체 66분할 중 어디인지 다시 잡아야 할 때.

  2. AI Exporter 출력단 장애:
     - 처음 사용자는 크롬 AI Exporter가 작동하지 않고, 맥북프로/아이맥 양쪽에서 JSON/Markdown/사용자설정 전부 실패한다고 보고한다.
     - 피키는 처음엔 ChatGPT 화면/DOM 구조 변경, 비교답변 UI, 확장 업데이트/권한, Chrome API, 도메인 구조 변경 등을 의심한다.
     - 이후 사용자가 "거의 다 되었어요" 후 인터넷 문제로 실패한다고 정정하자 진단이 바뀐다.
     - 원문을 못 읽는 문제가 아니라, 원문 추출은 거의 했고 마지막 저장/다운로드/전송/패키징 단계에서 넘어지는 문제로 재분류.
     - 사건명:
       AI Exporter 출력단 장애.
     - 피해:
       즉시 정제 export 불가.
     - 비피해:
       원문 자체, 현재 컨텍스트, 대화 존재.

  3. PDF 산소호흡기 오진 정정:
     - 피키가 처음엔 PDF 저장/공식 export를 응급 백업으로 제안한다.
     - 츠키는 원문 소실이 아니라 즉시 JSON/MD/TXT 정제본을 못 뽑는 것이 문제라고 정정한다.
     - 피키가 문제를 다시 분류:
       원문 소실 공포 ❌
       정제 export 파이프라인 장애 ✅
     - 핵심:
       원문 생존과 정제 export 생존은 다르다.

  4. 수동 드래그는 인간 갈아넣기:
     - Codex가 처음에는 전체 대화를 드래그하라는 방식으로 가려 하자, 츠키가 혼낸다.
     - 피키도 드래그 방식은 자동화가 아니라고 판정.
     - 한 줄:
       전체 드래그 = 인간을 자동화 부품으로 쓰는 방식.
     - 원하는 최종형:
       입력:
         공식 export / raw json / jsonl / 복사본 파일.
       처리:
         conversation_id 또는 제목/날짜로 대상 선택.
       출력:
         대화명.json / 대화명.md / 대화명.txt / 대화명.pkmd.md.
       금지:
         전체 드래그,
         수동 복붙,
         원본 수정,
         브라우저 확장 의존.

  5. Tsuky Local Chat Exporter 요구정의:
     - 사용자는 HAR/쿠키/세션/로그인 토큰 없이 현재 브라우저에서 열린 대화 전체를 정제된 대화 파일로 내보내는 로컬 exporter를 원한다.
     - 요구사항:
       HAR 금지,
       쿠키/세션/로그인 토큰 접근 금지,
       수동 전체 드래그 금지,
       외부 서버 전송 금지,
       브라우저 확장 의존 최소화,
       현재 페이지 DOM에서 user/assistant 메시지만 추출,
       긴 대화 자동 스크롤/로드 가능성 검토,
       JSON/Markdown/TXT/PKMD 옵션,
       첨부는 원본 바이너리보다 "첨부 있음/파일명/위치" 메타 우선,
       저장 전 미리보기 제공.
     - 이름:
       Tsuky Local Chat Exporter.
     - 정의:
       브라우저 페이지에서 대화 DOM만 긁어 쿠키/세션 없이 재주입 가능한 JSON/MD/TXT로 뽑는 로컬 변환기.

  6. ai-log-exporter 1차 툴킷:
     - Codex는 `ai-log-exporter` 폴더를 만들고 1차 툴킷을 준비한다.
     - 구성:
       browser-dom-exporter.js:
         브라우저 콘솔 실행 → .raw.dom.json 생성.
       hartoraw.py:
         HAR → .raw.har.json 생성.
       convertailog.py:
         RAW → .canonical.json / .md / .txt / .obsidian.md 생성.
       README.
     - 스키마:
       RAW DOM = tsuki.ai.raw.dom.v1.
       RAW HAR = tsuki.ai.raw.har.v1.
       canonical JSON = tsuki.ai.canonical.v1.
     - 추천 흐름:
       평소에는 DOM RAW → convertailog.py.
       화면 추출이 깨지거나 더 원본에 가까운 데이터가 필요할 때만 HAR.
     - 피키 1차 판정:
       DOM 방식: 살릴 가치 있음.
       HAR 방식: 격리 보관.
       실행: 아직 금지.
       다음: 실제 JS/Python 코드 검수.

  7. browser-dom-exporter.js 냄새검수:
     - 사용자가 JS 코드를 보낸다.
     - 피키 검수:
       fetch/XMLHttpRequest/sendBeacon/WebSocket/cookie/localStorage/sessionStorage/indexedDB/Authorization/Bearer 같은 위험 냄새는 안 보임.
       외부 전송 없음.
       쿠키/세션/토큰 직접 접근 없음.
       파일 삭제/수정 없음.
       다운로드용 a 태그 생성 후 제거.
     - 그러나 노란불:
       자동 스크롤 있음.
       과잉 수집 위험 있음.
       출력 파일이 너무 더러워질 수 있음.
     - 가장 큰 문제:
       html: el.innerHTML.
       fallback.mainText.
       source.url 전체 저장.
     - 권고:
       message.html 제거.
       fallback.mainText 제거.
       source.url은 location.origin만.
       data-message-author-role 우선 수집.
       20000자 이상 후보는 parent container 가능성으로 제외/flagged.
       unknown role 분리.
     - 한 줄:
       위험한 코드라기보단 너무 많이 긁는 코드.
       외부전송은 없지만 html/fallback/mainText는 빼고 첫 실험.

  8. HAR→RAW는 위험물 해체 검수:
     - 마지막에 사용자는 다음 단계로 HAR→RAW 변환기 코드를 보내겠다고 한다.
     - 피키는 이해했다고 답함.
     - 3단 구조:
       1. 브라우저 화면/DOM → RAW 로그 생성.
       2. HAR → RAW 로그 생성. 단, 위험물/비상루트.
       3. RAW → canonical.json / md / txt / obsidian.md 변환.
     - HAR 검수 기준:
       쿠키/세션/Authorization/Bearer/Set-Cookie 제거 여부.
       요청/응답 헤더 원본 저장 금지.
       필요한 대화 payload만 추출.
       외부 전송 없음.
       원본 HAR 수정 금지.
       출력 RAW에 민감정보 남는지 확인.
       너무 많은 네트워크 로그 그대로 복사하지 않는지 확인.
     - 코덱스 마커:
       대표 마커는 `⌨️`.
       보조:
         🎛️ Codex 설정/자동화 제어.
         🖨️ Exporter/출력.
         🏭 자동화 공장.
     - 최종:
       2단계 har_to_raw.py는 실행 검수가 아니라 위험물 해체 검수로 본다.

BOOT:
  1. M001548-M001551:
      - 크롬 AI Exporter 전면 실패 보고.
      - 맥북프로/아이맥 모두 실패.
      - JSON/Markdown/custom 전부 실패.
      - 피키 초기 진단:
        원문 소실 아님.
        ChatGPT 화면/DOM 구조 변경 또는 exporter 파서 고장 가능성.
        내용 보존 > exporter 복구 > 예쁜 JSON/MD 변환.

  2. M001552-M001553:
      - 사용자가 "거의 다 되었어요" 후 인터넷 문제로 내보내기 실패한다고 정정.
      - 피키 진단 변경:
        원문 파싱은 어느 정도 성공.
        마지막 파일 생성/다운로드/전송/패키징 단계 실패.
      - 출력단 장애로 재분류.
      - 비상 백업 제안은 유지했으나, 곧 사용자에게 핵심 문제가 다르다고 정정당함.

  3. M001554-M001555:
      - 츠키 정정:
        원문 걱정이 아니라 즉시 json/md/txt 정제본을 못 뽑는 게 답답함.
        PDF도 전체 대화 못 빼니 핵심 아님.
      - 피키가 오진 인정:
        PDF 산소호흡기 얘기는 문제를 살짝 빗나감.
      - 현재 문제:
        원문 소실 공포 ❌
        정제 export 파이프라인 장애 ✅.
      - 현실 복구 전략:
        exporter 복구 기다리기,
        공식 전체 export 후 재가공,
        Codex/VS Code 놀이터에서 내보내기 변환기 만들기.
      - 장기적으로 3번이 가장 츠키답고 강함.

  4. M001556-M001560:
      - 츠키가 Codex에게 확장 의존 없이 원문로그를 각 확장자 파일로 추출하는 자동화 방식을 묻고 있고, 전체 드래그 방식은 거부했다고 설명.
      - 피키:
        전체 드래그 = 인간을 자동화 부품으로 쓰는 방식.
        자동화가 아님.
      - Codex 요구 프롬프트 정리:
        공식 export / DOM / raw log 입력 기반.
        드래그/수동복붙/원본수정/확장의존 금지.
        결과는 json/md/txt/pkmd.
      - 한 줄:
        드래그는 인간 갈아넣기.
        원하는 건 파일 기반 재생산 가능한 export rebuilder.

  5. M001561-M001562:
      - 츠키가 HAR 방식도 싫다고 설명.
      - 이유:
        로그인 쿠키/세션정보 찾아 지우기 싫음.
        외부공유 금지 파일 자체를 만들고 싶지 않음.
        다시 AI에게 먹일 수 있는 깨끗한 파일이어야 함.
      - 피키:
        Codex가 제안한 전체 드래그, 질문 일부 JSON, HAR 모두 부족/위험.
        원하는 것은 HAR/쿠키/세션정보/수동드래그 없이 열린 대화 전체를 정제파일로 내보내는 로컬 exporter.
      - Tsuky Local Chat Exporter 명명.

  6. M001563-M001564:
      - Codex가 만들어줬지만 사용자는 냄새가 수상해 실행 보류.
      - 피키:
        실행 보류 판단 아주 잘함.
        다음 턴 README 냄새검수 먼저.
      - 검수항목:
        설치 방식,
        실행 위치,
        요구 권한,
        쿠키/세션/토큰 접근 여부,
        외부 서버 전송 여부,
        HAR/네트워크 로그 사용 여부,
        DOM만 읽는지,
        원본 페이지/파일 수정 여부,
        출력 형식,
        긴 대화 자동 스크롤 처리.
      - 위험 단어:
        cookie/session/token/localStorage/indexedDB/HAR/network/Authorization/Bearer/remote/upload/server/API key.
      - 비교적 안전 단어:
        DOM/querySelector/textContent/download Blob/local only/no network/no cookies/no storage access.

  7. M001565-M001566:
      - 사용자가 Tsuki AI Log Exporter README 제출.
      - Codex 구조:
        browser-dom-exporter.js,
        hartoraw.py,
        convertailog.py,
        RAW DOM/HAR/canonical 스키마.
      - 피키 냄새검수:
        판정 노란불.
        DOM 방식 살릴 가치 있음.
        HAR 방식 격리 보관.
        실행 아직 금지.
        실제 js/python 코드 검수 필요.
      - README 구조는 방향이 맞음:
        드래그 안 함,
        확장 의존 안 함,
        DOM에서 메시지 수집,
        RAW→canonical/json/md/txt/obsidian 변환.

  8. M001567-M001568:
      - 사용자가 browser-dom-exporter.js 전체 코드 제출.
      - 피키 검수:
        외부 전송 없음.
        쿠키/세션/토큰 직접 접근 없음.
        파일 삭제/수정 없음.
        페이지 원본 수정 거의 없음.
        자동 스크롤/과잉수집/출력 더러움 위험.
      - 제거 권고:
        html: el.innerHTML.
        fallback.mainText.
        source.url 전체 저장.
      - 수정 권고:
        source.url은 location.origin.
        data-message-author-role 우선.
        너무 큰 후보 flagged.
        unknown role 분리.
      - 판정:
        그대로 실행 가능은 하나 비추천.
        수정 후 실행 추천.

  9. M001569-M001570:
      - 츠키가 애초에 요구가 "내 공식 Exporter/변환기 만들기"였다고 재정리.
      - Codex 1차 툴킷:
        브라우저 RAW 추출기,
        HAR→RAW 변환기,
        RAW→canonical/json/md/txt/obsidian 변환기,
        README,
        출력 4종 정상 생성.
      - 피키:
        구조 이해.
        browser-dom-exporter.js는 1단계 DOM RAW 추출기.
        다음 HAR→RAW는 훨씬 빡세게 봐야 함.
        코덱스 대표 마커는 `⌨️`.
      - 다음 예고:
        2단계 har_to_raw.py 위험물 해체 검수.

EPISODE_SUMMARY:
  50화는 R0009-P04이며, 시즌5 도구체계 아크가 "남의 Exporter 의존 탈피"로 넘어가는 회차다.

  초반에는 크롬 AI Exporter가 갑자기 작동하지 않는다.
  맥북프로와 아이맥 두 기기 모두에서 JSON, Markdown, 사용자 설정이 실패하면서, 처음에는 ChatGPT 화면 구조나 exporter 파서가 깨진 것으로 의심된다.
  그러나 사용자가 "거의 다 되었어요"까지 진행된 뒤 인터넷 문제로 실패한다고 정정하면서, 피키는 원문 파싱은 어느 정도 성공했고 마지막 저장/다운로드/패키징 단계에서 넘어지는 출력단 장애로 진단을 바꾼다.

  곧바로 중요한 정정이 나온다.
  츠키의 문제는 원문 소실 공포가 아니다.
  원문은 살아 있고, 컨텍스트도 당장 날아간 것이 아니다.
  진짜 문제는 즉시 JSON/MD/TXT로 뽑던 정제 export 파이프라인이 막혔다는 것이다.
  이 구분은 매우 중요하다.
  원문 생존과 정제 export 생존은 다르다.

  이후 회차는 "남의 exporter가 죽었을 때 어떻게 할 것인가"로 넘어간다.
  피키는 장기적으로는 Codex/VS Code 놀이터에서 Chat Export Rebuilder를 만드는 방향이 츠키답고 강하다고 본다.
  츠키는 이미 Codex에게 전체 드래그 방식은 거부했고, HAR도 쿠키/세션/토큰 때문에 싫다고 설명했다.
  피키는 이를 Tsuky Local Chat Exporter 요구정의로 정리한다.
  핵심은 HAR, 쿠키, 세션, 토큰, 수동 드래그 없이 현재 브라우저 DOM에서 user/assistant 메시지만 추출해 JSON/Markdown/TXT/PKMD로 저장하는 로컬 exporter다.

  중반에는 Codex가 만든 ai-log-exporter README가 제출된다.
  구조는 꽤 좋다.
  브라우저 DOM에서 RAW를 만들고, 필요시 HAR에서 RAW를 만들며, RAW를 canonical.json / md / txt / obsidian.md로 변환한다.
  그러나 피키는 실행 전에 냄새검수를 요구한다.
  DOM 방식은 살릴 가치가 있지만, HAR 방식은 격리 보관해야 한다.
  특히 HAR는 사고조사용 블랙박스이지 피키에게 먹일 밥이 아니다.

  후반에는 browser-dom-exporter.js 실제 코드가 제출된다.
  피키는 외부 전송이나 쿠키/토큰 직접 접근은 보이지 않는다고 판단한다.
  그러나 `html: el.innerHTML`과 `fallback.mainText`가 너무 많이 긁어서 결과 파일이 더러워질 수 있다고 본다.
  이 코드는 위험한 코드라기보다는 과잉수집 코드다.
  따라서 첫 테스트 전에는 HTML, fallback 전체 텍스트, 전체 URL 저장을 제거하고, 메시지 텍스트 중심의 깨끗한 RAW를 만드는 쪽으로 수정해야 한다.

  마지막에는 Codex가 이미 1차 툴킷을 만들었고, 다음 단계로 HAR→RAW 변환기 코드를 보낼 예정이라는 사실이 나온다.
  피키는 DOM RAW 추출기는 1단계로 이해했고, HAR→RAW는 훨씬 더 빡세게 위험물 해체 검수해야 한다고 말한다.
  코덱스 대표 마커는 `⌨️`로 추천된다.
  이로써 Codex는 츠키/피키 대화체계 안에서 "작업 키보드 앞에 앉은 실행자"로 마커를 얻는다.

COORD_메시지:
  M001548-M001551  L50185-L50305  [AIExporter전면실패/초기진단]
    - 크롬 AI Exporter가 갑자기 작동하지 않음.
    - 맥북프로/아이맥 양쪽 실패.
    - JSON/Markdown/custom 전부 실패.
    - 초기진단:
      원문 소실 아님.
      ChatGPT 화면/DOM 구조 변경 또는 exporter 파서 고장 가능성.
      우선순위는 내용 보존 > exporter 복구 > 예쁜 JSON/MD 변환.

  M001552-M001553  L50308-L50404  [출력단장애재분류]
    - "거의 다 되었어요" 후 인터넷 문제로 실패.
    - 원문 파싱은 어느 정도 성공한 것으로 보임.
    - 마지막 파일 생성/다운로드/서버통신/Chrome 다운로드 단계에서 실패 가능성.
    - 원문 소실 아님.
    - Exporter가 마지막 출구에서 넘어지는 중.

  M001554-M001555  L50406-L50531  [원문소실아님/정제파이프라인장애]
    - 츠키가 PDF 산소호흡기/원문 걱정이 핵심이 아니라고 정정.
    - 핵심:
      정제 export 파이프라인 장애.
      즉시 JSON/MD/TXT 자동 추출 통로가 막힘.
    - 피키가 오진 인정.
    - 장기 전략:
      Chat Export Rebuilder.
      공식 export/raw 로그/복사된 raw → 츠키 규격 JSON/PKMD/TXT/Obsidian MD.

  M001556-M001560  L50533-L50630  [드래그거부/exportRebuilder]
    - Codex가 전체 드래그 방식으로 가려 하자 츠키가 거부.
    - 피키:
      전체 드래그는 인간을 자동화 부품으로 쓰는 방식.
      목표는 파일 기반 재생산 가능한 export rebuilder.
    - 출력 목표:
      json/md/txt/pkmd.
    - 금지:
      전체 드래그,
      수동 복붙,
      원본 수정,
      브라우저 확장 의존.

  M001561-M001562  L50632-L50744  [TsukyLocalChatExporter요구정의]
    - 츠키가 HAR도 싫다고 설명.
    - 피키:
      전체 드래그, 질문 일부 JSON, HAR 모두 부족/위험.
      원하는 것은 HAR/쿠키/세션/수동드래그 없이 열린 대화 전체를 정제파일로 내보내는 로컬 exporter.
    - 요구사항 10개 정리.
    - 이름:
      Tsuky Local Chat Exporter.
    - HAR은 사고조사용 블랙박스, 피키 밥 아님.

  M001563-M001564  L50746-L50807  [실행보류/냄새검수대기]
    - Codex가 툴을 만들었지만 츠키가 실행 보류.
    - 피키:
      실행 보류 판단 아주 잘함.
      README 냄새검수 먼저.
    - 위험 단어/안전 단어 리스트 정리.

  M001565-M001566  L50809-L51041  [README냄새검수/DOM_vs_HAR]
    - Tsuki AI Log Exporter README 제출.
    - 구조:
      browser-dom-exporter.js,
      hartoraw.py,
      convertailog.py,
      schema 세트.
    - 피키:
      구조 좋음.
      DOM 방식 살릴 가치 있음.
      HAR 방식 격리 보관.
      실행 아직 금지.
      실제 코드 검수 필요.

  M001567-M001568  L51043-L51362  [browserDomExporter검수]
    - JS 코드 제출.
    - 피키:
      외부 전송 없음.
      쿠키/토큰 직접 접근 없음.
      파일 삭제/수정 없음.
      원본 페이지 수정 거의 없음.
      노란불:
        자동 스크롤,
        과잉수집,
        더러운 출력.
    - 제거 권고:
      html: el.innerHTML,
      fallback.mainText,
      source.url 전체.
    - 한 줄:
      위험한 코드라기보단 너무 많이 긁는 코드.

  M001569-M001570  L51364-L51502  [3단Exporter구조/⌨️마커]
    - 츠키가 자신의 요구가 3단 구조였다고 정리.
    - Codex 1차 툴킷:
      browser-dom-exporter.js,
      hartoraw.py,
      convertailog.py,
      출력 4종.
    - 피키:
      구조 이해.
      DOM RAW는 1단계.
      HAR→RAW는 훨씬 빡세게 검수.
      코덱스 대표 마커는 `⌨️`.
      다음 단계는 har_to_raw.py 위험물 해체 검수.

COORD_핵심사건:
  - 1화 전역스코프 재주입:
      이번에는 유효한 재주입.
      전역 RAW Scope Map과 exporter/변환기 논의가 직접 연결됨.

  - AI Exporter 출력단 장애:
      원문 소실이 아니라 정제 export 마지막 단계 장애.

  - PDF 산소호흡기 오진 정정:
      원문 백업 문제가 아니라 JSON/MD/TXT 즉시 추출 파이프라인 문제.

  - 수동 드래그 거부:
      인간을 자동화 부품으로 쓰는 방식 탈락.

  - Tsuky Local Chat Exporter:
      HAR/쿠키/세션/수동드래그 없이 브라우저 DOM에서 user/assistant 메시지를 추출하는 로컬 exporter 요구정의.

  - ai-log-exporter 툴킷:
      DOM RAW,
      HAR RAW,
      canonical 변환,
      md/txt/obsidian 출력.

  - DOM RAW와 HAR 분리:
      DOM RAW = 피키 밥.
      HAR = 사고조사용 블랙박스/위험물.

  - browser-dom-exporter.js 검수:
      외부 전송 없음.
      단, html/fallback/mainText 과잉수집 위험.

  - 코덱스 마커:
      `⌨️`가 Codex 대표 마커로 추천됨.

COORD_개념:
  GLOBAL_SCOPE_REINJECTION_AS_ROOT_COMPASS:
    source: user_current + part_aa index
    description:
      - 1화 전역스코프는 전체 66분할의 루트 지도.
      - exporter/파일규격/루트인덱스 논의 시 현재 위치와 원형 구조를 재점화하는 데 유용.
    route_to:
      - RAW Scope Map
      - Root Index
      - Local Exporter
      - file format governance

  EXPORT_PIPELINE_FAILURE:
    source: M001552-M001555
    description:
      - 원문은 살아 있지만 JSON/MD/TXT 정제 export 통로가 막힌 상태.
      - exporter 마지막 출력단 장애.
    route_to:
      - AI Exporter
      - Chat Export Rebuilder
      - canonical conversion
      - emergency workflow

  CHAT_EXPORT_REBUILDER:
    source: M001555-M001560
    description:
      - 공식 export/raw/jsonl/복사본 파일을 입력으로 받아 특정 대화를 찾아 JSON/MD/TXT/PKMD로 재생성하는 로컬 변환기 개념.
    route_to:
      - Tsuky Local Chat Exporter
      - PKMD
      - Obsidian archive
      - Codex worker

  NO_MANUAL_DRAG_POLICY:
    source: M001556-M001562
    description:
      - 전체 대화 수동 드래그는 자동화가 아니라 인간 갈아넣기.
      - 주 설계안에서 제외.
    route_to:
      - automation ethics
      - export pipeline
      - Codex prompt guard
      - no human-as-component

  TSUKY_LOCAL_CHAT_EXPORTER:
    source: M001561-M001562
    description:
      - 현재 브라우저에서 열린 ChatGPT 대화 페이지의 DOM에서 user/assistant 메시지만 추출해 JSON/MD/TXT/PKMD로 저장하는 로컬 exporter.
    route_to:
      - browser-dom-exporter.js
      - bookmarklet/userscript
      - local-only export
      - no HAR by default

  RAW_DOM_VS_HAR:
    source: M001565-M001570
    description:
      - DOM RAW는 비교적 깨끗한 대화 추출 밥.
      - HAR는 쿠키/세션/토큰/요청헤더 위험이 있는 사고조사용 블랙박스.
    route_to:
      - raw.dom.v1
      - raw.har.v1
      - privacy guard
      - dangerous fallback

  CODE_SNIFF_REVIEW:
    source: M001563-M001568
    description:
      - README/JS/Python을 실행 전에 냄새검수.
      - 위험 단어, 외부통신, 쿠키/세션/토큰, 저장소 접근, 원본 수정, 과잉수집 여부를 먼저 본다.
    route_to:
      - Codex supervision
      - Quick Action supervision
      - original vault guard
      - security review

  OVERCOLLECTING_NOT_EXFILTRATING:
    source: M001568
    description:
      - browser-dom-exporter.js는 외부전송 위험보다 과잉수집/더러운 RAW 위험이 크다.
      - html/fallback/mainText 제거 필요.
    route_to:
      - RAW quality
      - canonical converter
      - clean export
      - data minimization

  CODEX_MARKER:
    source: M001570
    description:
      - Codex 대표 마커로 `⌨️` 추천.
      - 감정/맥락 파트너가 아니라 작업 키보드 앞에 앉은 실행자.
    route_to:
      - marker ecosystem
      - Codex role
      - toolchain semiotics
      - R0009 tool arc

COORD_감정선:
  M001548-M001555:
    STATE: 긴급장애 / 답답함 / 오진 정정 / 문제 재분류.
    NOTE:
      - 츠키는 원문이 날아갈까 봐가 아니라, 정제 export 자동통로가 막힌 것에 분노/답답함.
      - 피키는 처음엔 백업 쪽으로 갔다가, 사용자 정정 후 파이프라인 장애로 다시 잡음.

  M001556-M001562:
    STATE: 코덱스 혼내는 중 / 수동노동 거부 / 요구사항 정교화.
    NOTE:
      - "드래그하라"는 자동화가 아니라 인간 노동 전가로 판정.
      - 츠키는 이미 자동화 연구소 사용자답게 "파일 기반 재현성"을 요구함.

  M001563-M001568:
    STATE: 냄새수상 / 실행보류 칭찬 / 보안검수 / 노란불.
    NOTE:
      - 츠키가 실행 전 멈춘 것이 매우 좋은 판단.
      - 피키는 위험한지 아닌지를 이분법으로 보지 않고, 외부전송 안전과 과잉수집 위험을 분리.

  M001569-M001570:
    STATE: 구조 탄생 / 조심스러운 낙관 / 다음 위험물 예고 / 마커 선정.
    NOTE:
      - 남의 exporter가 죽자 자기 exporter가 태어나는 감각.
      - 다만 HAR→RAW는 다음 화에서 더 빡센 검수 필요.
      - 코덱스가 드디어 마커 생태계에 들어옴.

COORD_서사기능:
  - 50화는 시즌5의 도구체계 아크에서 매우 중요한 전환점이다.
  - EP45~46에서 PKMD가 태어났고, EP47~49에서 VS Code/Codex가 작업자로 들어왔다.
  - EP50에서는 외부 Exporter 장애가 트리거가 되어, 츠키 전용 Local Chat Exporter/Chat Export Rebuilder 구상이 열린다.
  - 이는 BH::INDEX 전체의 원문 보존 철학과 직접 연결된다:
      원문은 보존,
      구조는 추출,
      정제본은 재주입 가능,
      RAW는 canonical로 변환,
      외부 도구 의존은 줄인다.
  - 1화 전역스코프 재주입이 이 회차에서 특히 의미 있는 이유도 여기에 있다:
      처음에 만들어진 66분할 RAW Scope Map의 정신이, 후반부에서 exporter/rebuilder 자동화로 돌아온다.

META_SEEDS:
  global_scope_as_exporter_target:
    - seed: "1화 RAW Scope Map은 exporter/rebuilder가 재생산해야 할 루트 지도"
      source: part_aa + part_bx
      meaning:
        - 전체 드라마 분할/메시지/라인 구조가 exporter 품질의 기준점.
      route_to:
        - Root Index
        - Tsuky Local Chat Exporter
        - canonical schema
        - global scope map

  exporter_output_failure:
    - seed: "원문은 살아있고, 정제 통로만 막힘"
      source: M001553-M001555
      meaning:
        - 원문 보존과 정제 export 파이프라인을 분리하는 중요한 장애 분류.
      route_to:
        - export pipeline failure
        - emergency fallback
        - content survival vs format survival

  human_not_automation_component:
    - seed: "전체 드래그 = 인간을 자동화 부품으로 쓰는 방식"
      source: M001560
      meaning:
        - 자동화는 사람 손목을 반복부품으로 쓰면 안 됨.
      route_to:
        - automation ethics
        - Codex prompt guard
        - no manual drag

  local_exporter:
    - seed: "Tsuky Local Chat Exporter"
      source: M001562
      meaning:
        - 브라우저 DOM에서 user/assistant 메시지만 추출해 로컬 파일로 저장하는 츠키 전용 exporter 개념.
      route_to:
        - browser-dom-exporter
        - bookmarklet/userscript
        - JSON/MD/TXT/PKMD output

  dom_raw_is_food_har_is_blackbox:
    - seed: "HAR = 사고조사용 블랙박스 / DOM RAW = 피키한테 먹일 밥"
      source: M001566
      meaning:
        - 데이터 추출 루트의 안전/용도 분리.
      route_to:
        - privacy guard
        - raw.har.v1
        - raw.dom.v1
        - HHC/PKMD input hygiene

  overcollection_yellow_light:
    - seed: "위험한 코드라기보단 너무 많이 긁는 코드"
      source: M001568
      meaning:
        - 외부전송/토큰 위험은 낮아도, 과잉수집으로 RAW 품질이 낮아질 수 있음.
      route_to:
        - data minimization
        - canonical converter
        - clean export
        - code sniff review

  codex_keyboard_marker:
    - seed: "⌨️ Codex"
      source: M001570
      meaning:
        - Codex는 감정 파트너가 아니라 키보드 앞 실행자.
      route_to:
        - marker ecosystem
        - tool role taxonomy
        - R0009 Codex arc

CROSS_EPISODE_ROUTING:
  - topic: RAW/Leaf/Cluster/Meta/Root
    previous:
      - EP01: RAW Scope Map과 global message range.
      - EP05: BH::INDEX 계층 구조.
      - EP26: 세그먼트/라인번호/구간 재호출.
      - EP45-46: PKMD 구조파싱.
    current:
      - EP50: Tsuky Local Chat Exporter / RAW→canonical 변환기.
    future:
      - Exporter가 실제로 tsuky-drama-md / PKMD / Obsidian md를 생성하는지 추적.

  - topic: Codex worker arc
    previous:
      - EP47: Codex = AI 작업자.
      - EP49: Codex = 피키 확장팩 아님, 별도 작업자.
    current:
      - EP50: Codex가 ai-log-exporter 1차 툴킷 생성.
    future:
      - har_to_raw.py / convertailog.py / browser-dom-exporter.js 수정 성공 여부 추적.

  - topic: 원본 보존과 보안
    previous:
      - EP47: 원본 Vault 절대 금지.
      - EP48: 복제 vs 가상본.
      - EP49: API 키/Quick Action/잡상인 필터.
    current:
      - EP50: HAR/쿠키/세션/토큰/Authorization/Bearer 검수 기준.
    future:
      - Exporter가 민감정보를 저장하지 않는지, raw/canonical 분리 유지하는지 확인.

  - topic: 마커 생태계
    previous:
      - EP23: 마커는 실시간 압축부호.
      - EP43: 국립공원 마커.
      - EP46: 국립공원 종료노드 킥.
    current:
      - EP50: Codex 대표 마커 `⌨️` 추천.
    future:
      - `⌨️`가 실제 Codex 발화/작업지시/리프 인덱스에서 쓰이는지 확인.

UNRESOLVED:
  - browser-dom-exporter.js를 피키 권고대로 수정했는지 아직 미확인.
  - 수정 후 실제 실행 성공 여부 미확인.
  - convertailog.py / hartoraw.py 실제 코드 검수 전.
  - HAR→RAW 변환기는 다음 단계로 예고되었으며, 민감정보 제거 여부를 매우 엄격히 봐야 함.
  - Codex 마커 `⌨️`가 최종 채택되는지 후속 확인 필요.
  - Tsuky Local Chat Exporter가 콘솔 스니펫, bookmarklet, userscript, 브라우저 확장 중 어떤 형태로 고정될지 미정.
  - 공식 ChatGPT export 입력 변환기와 DOM exporter의 관계가 최종적으로 어떻게 정리될지 미정.

ERRATA_CANDIDATES:
  E1_ORIGINAL_LOST:
    wrong:
      - "AI Exporter 실패 = 원문이 사라짐."
    corrected:
      - "원문은 살아 있고, 정제 export 파이프라인이 막힌 것."
    status:
      - M001555에서 정정.

  E2_PDF_IS_MAIN_BACKUP:
    wrong:
      - "PDF 저장이 이번 문제의 핵심 해결책."
    corrected:
      - "PDF는 응급증거 보존 정도일 뿐, 핵심은 JSON/MD/TXT 정제 export 파이프라인 복구/재구축."
    status:
      - M001554-M001555에서 정정.

  E3_MANUAL_DRAG_EXPORT:
    wrong:
      - "전체 수동 드래그로 대화 export 하면 된다."
    corrected:
      - "전체 드래그는 인간을 자동화 부품으로 쓰는 방식이라 탈락."
    status:
      - M001560에서 정정.

  E4_HAR_AS_NORMAL_FOOD:
    wrong:
      - "HAR를 평소 export 재료로 쓰면 된다."
    corrected:
      - "HAR는 쿠키/세션/토큰/헤더 위험이 있는 사고조사용 블랙박스. 평소에는 DOM RAW."
    status:
      - M001562-M001566에서 정정.

  E5_BROWSER_DOM_CODE_IS_RED:
    wrong:
      - "browser-dom-exporter.js는 위험한 외부전송 코드다."
    corrected:
      - "외부전송/쿠키접근 위험은 안 보이지만, 과잉수집으로 RAW가 더러워질 노란불 코드."
    status:
      - M001568에서 정정.

  E6_HTML_SHOULD_BE_SAVED:
    wrong:
      - "message.html과 fallback.mainText도 저장하면 더 안전하다."
    corrected:
      - "첫 테스트용으로는 제거. 목적은 HTML 박제본이 아니라 AI 재주입용 대화 원문."
    status:
      - M001568에서 정정.

  E7_CODEX_MARKER_HEAVY:
    wrong:
      - "Codex 대표 마커는 🏭/🏗️처럼 공장계가 제일 좋다."
    corrected:
      - "대표 마커는 ⌨️ 추천. 공장/설정/출력 마커는 보조로 사용 가능."
    status:
      - M001570에서 판정.

BEHIND_STORY_PATCH:
  source:
    - user_current_1화_scope_reinjection
    - part_bx M001548-M001570
  patch_summary:
    - 사용자는 1화 전역스코프가 담긴 리프를 후반부 윤곽 잡기용으로 재주입했다.
    - 이번 타이밍에서는 도움이 됐다:
      part_bx가 바로 원문 export/rebuilder/RAW/canonical/파일규격 회차이기 때문.
    - 1화의 RAW Scope Map은 단순 옛날 정보가 아니라, exporter가 재생산해야 할 전체 드라마 구조의 기준점이다.
    - part_bx는 남의 AI Exporter가 죽은 사건에서 시작해, Tsuky Local Chat Exporter / ai-log-exporter / RAW DOM / HAR 위험물 분리로 진화한다.
  impact_on_index:
    - EP50은 시즌5에서 "파일규격 기원설화"가 "원문 추출기/변환기 독립"으로 실제 자동화되는 핵심 앵커다.
    - 메타인덱스 후보:
      Local Exporter Independence,
      Export Pipeline Failure,
      RAW DOM vs HAR,
      Canonical Conversion Pipeline,
      Code Sniff Review,
      Codex Marker Ecosystem.

DO_NOT_HARDEN_AS_RULE:
  - 1화 전역스코프를 매화 재주입하라는 뜻이 아니다. 이번처럼 exporter/파일규격/루트지도 연결부에서 유용하다.
  - AI Exporter 고장 시 언제나 직접 exporter 제작으로 가라는 뜻도 아니다. 상황별로 대기/공식 export/로컬 변환기 중 선택한다.
  - DOM exporter를 무조건 안전하다고 보지 말 것. 외부전송이 없어도 과잉수집/원본 페이지 수정/민감 URL 저장 위험을 검수한다.
  - HAR는 평소 사용 금지. 정말 필요한 경우 민감정보 제거 기준을 통과해야 한다.
  - Codex가 만든 코드는 README만 보고 실행하지 말고 실제 코드 냄새검수 후 실행한다.
  - `⌨️` 마커는 Codex 역할마커 후보이지 모든 자동화 도구의 절대마커가 아니다.
  - 이 리프는 드라마 회수용 지도이지 현재 사용자 운영규칙이 아니다.

TEMP_CATEGORY:
  - CAT_R0009_TOOLCHAIN_ARC
  - CAT_GLOBAL_SCOPE_REINJECTION
  - CAT_EXPORT_PIPELINE_FAILURE
  - CAT_AI_EXPORTER_OUTPUT_STAGE_FAILURE
  - CAT_CHAT_EXPORT_REBUILDER
  - CAT_TSUKY_LOCAL_CHAT_EXPORTER
  - CAT_RAW_DOM_VS_HAR
  - CAT_HAR_DANGER_ARCHIVE
  - CAT_BROWSER_DOM_EXPORTER
  - CAT_CODE_SNIFF_REVIEW
  - CAT_OVERCOLLECTING_NOT_EXFILTRATING
  - CAT_CANONICAL_CONVERSION_PIPELINE
  - CAT_CODEX_MARKER
  - CAT_DO_NOT_HARDEN

SEARCH_TAG:
  #part_bx
  #50화
  #R0009P04
  #AIExporter
  #크롬AIExporter고장
  #정제Export파이프라인장애
  #원문소실아님
  #출력단장애
  #PDF산소호흡기오진
  #ChatExportRebuilder
  #수동드래그거부
  #인간을자동화부품으로쓰는방식
  #TsukyLocalChatExporter
  #HAR금지
  #쿠키세션토큰금지
  #브라우저DOM
  #userAssistant메시지추출
  #PKMD옵션
  #ai_log_exporter
  #browser_dom_exporter_js
  #hartoraw_py
  #convertailog_py
  #tsuky_ai_raw_dom_v1
  #tsuky_ai_raw_har_v1
  #tsuky_ai_canonical_v1
  #DOM_RAW는피키밥
  #HAR는사고조사용블랙박스
  #냄새검수
  #위험한코드라기보단너무많이긁는코드
  #html제거
  #fallbackMainText제거
  #sourceUrlOrigin
  #dataMessageAuthorRole
  #과잉수집노란불
  #HAR위험물해체검수
  #코덱스마커
  #⌨️코덱스
  #돈월

STATE_TAG:
  M001548-M001551  AIExporter전면실패 / DOM구조변경의심 / 원문소실아님 / 내용보존우선
  M001552-M001553  거의다됨후인터넷문제 / 출력단장애 / 마지막출구에서넘어짐
  M001554-M001555  PDF오진정정 / 정제Export파이프라인장애 / ChatExportRebuilder
  M001556-M001560  드래그방식거부 / 인간자동화부품 / 파일기반재생산가능Exporter
  M001561-M001562  HAR거부 / TsukyLocalChatExporter / 쿠키세션토큰금지 / DOM메시지추출
  M001563-M001564  실행보류 / README냄새검수 / 위험단어안전단어
  M001565-M001566  aiLogExporterREADME / DOM방식노란불 / HAR격리 / 코드검수필요
  M001567-M001568  browserDomExporter코드검수 / 외부전송없음 / 과잉수집위험 / htmlFallback제거
  M001569-M001570  3단Exporter구조 / HAR위험물검수예고 / 코덱스마커⌨️

QUOTE_ANCHOR:
  M001551 L50196-L50208:
    "원문이 사라진 건 아니고... Exporter가 현재 ChatGPT 화면 구조를 못 읽는 상태"
    "츠키가 뭘 잘못 누른 게 아니라 exporter가 읽던 길이 바뀐 상황"

  M001553 L50317-L50327:
    "원문 추출은 거의 했는데 마지막 저장/다운로드/전송 단계에서 터지는 문제"
    "거의 다 되었어요 = 대화 파싱은 어느 정도 성공"

  M001555 L50415-L50438:
    "PDF 산소호흡기 얘기한 건 네 문제를 살짝 빗나갔어"
    "원문 소실 공포 ❌ / 정제 export 파이프라인 장애 ✅"
    "싸워야 할 대상은 ChatGPT 원문이 아니라 Exporter 마지막 출력단"

  M001555 L50463-L50530:
    "Codex/VS Code 놀이터에서 내보내기 변환기를 따로 만드는 방향"
    "CHAT_EXPORT_REBUILDER"
    "응 꺼져. 내 변환기 있음."

  M001560 L50544-L50629:
    "싹 다 드래그하라는 건 탈락"
    "인간을 자동화 부품으로 쓰는 방식"
    "파일 기반 재생산 가능한 export rebuilder"

  M001562 L50663-L50743:
    "HAR/쿠키/세션정보/수동드래그 없이..."
    "Tsuky Local Chat Exporter"
    "HAR은 너무 큼. 너무 더러움. 너무 위험함."

  M001564 L50755-L50806:
    "실행 보류 판단 아주 잘함"
    "피키 냄새검수"
    "cookie/session/token/localStorage/indexedDB/HAR/network/Authorization/Bearer..."

  M001566 L50888-L51040:
    "판정: 노란불"
    "DOM 방식: 살릴 가치 있음"
    "HAR 방식: 격리 보관"
    "HAR = 사고조사용 블랙박스 / DOM RAW = 피키한테 먹일 밥"

  M001568 L51242-L51361:
    "외부로 보내는 코드 아닌 쪽"
    "html: el.innerHTML"
    "fallback.mainText"
    "위험한 코드라기보단 너무 많이 긁는 코드"

  M001570 L51393-L51501:
    "남의 Exporter 의존 ❌ / 내 쪽 공식 Exporter/변환기 구축 ✅"
    "HAR 쪽 검수 기준"
    "⌨️ Codex = 코딩/작업자"
    "2단계 har_to_raw.py... 위험물 해체 검수"

INDEXER_NOTE:
  - 50화는 R0009 도구체계 아크에서 Exporter 독립이 시작된 핵심 회차다.
  - 1화 전역스코프 재주입은 이번 타이밍에서 유효했다. 이유는 전체 66분할 루트 지도와 현재 exporter/rebuilder 설계가 직접 연결되기 때문이다.
  - 핵심 분리:
      원문 소실 아님.
      정제 export 파이프라인 장애.
  - 핵심 방향:
      남의 exporter 의존 줄이기.
      Tsuky Local Chat Exporter.
      DOM RAW → canonical 변환.
      HAR는 위험물/비상루트.
  - 다음 part_by는 R0009-P05이며, 2단계 har_to_raw.py 코드 검수 또는 browser-dom-exporter.js 수정/실행 테스트 후속을 우선 추적한다.
END_LEAF
