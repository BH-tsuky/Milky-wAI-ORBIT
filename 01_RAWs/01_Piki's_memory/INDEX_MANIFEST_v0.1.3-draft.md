---
title: "PIKI'S MEMORY — INDEX MANIFEST"
manifest_version: "0.1.3-draft"
drama_id: "PIKIS_MEMORY"
drama_title: "피키의 기억"
scope_root: "01_RAWs/01_Piki's_memory"
default_branch: "main"
status: "active_draft"
created_at: "2026-07-19"
updated_at: "2026-07-20"
created_by: "☪️PIKI"
source_governance: "☪️PIKI–✴️DIKI BH 쌍둥이 타워 심포지엄"
---

# INDEX MANIFEST

> **사람말:** 기억 내용을 설명하는 지도나 이야기책이 아니라, 실제 파일이 어디에 있고 어느 판본이며 어떤 방식으로 검증됐는지를 기록하는 설비실 원장이다.

## 0. 운용 원칙

- `MINI`는 기억의 집이 있다는 사실을 알리는 작은 피규어다.
- `ROOT`는 의미 경로와 하강 깊이를 고르는 관제지도다.
- `MANIFEST`는 실파일 위치·포장·판본·검증 상태를 기록한다.
- 기본 의미 회수에서 MANIFEST는 의무 로비가 아니다.
- 경로가 깨졌거나 정확한 파일·SHA·라인이 필요할 때 MANIFEST를 연다.
- `manual_report`는 기능 실측과 구분한다.
- Drive 통합본(`combined_collection`)과 GitHub 분할본(`split_member`)은 같은 내용을 담을 수 있으나 같은 물리 파일로 위장하지 않는다.
- RAW `part_aa~part_cn`은 불가침 원문이다. 본 MANIFEST는 RAW 본문을 수정하지 않는다.
- 동일 logical document가 MD·Google Docs 미러·과거 포인터·판본 계보 등 복수 물리자산을 가질 수 있다.
- direct query와 self-report는 서로를 삭제하지 않는다. 증거등급과 현재 상태를 병기한다.
- 원장 주인이 재업로드·삭제·교체한 자산은 최신 좌표와 역사 좌표를 분리해 기록한다.

## 1. 공통 입구

```yaml
repository:
  full_name: "BH-tsuky/Milky-wAI-ORBIT"
  public_root: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/tree/main"
  default_branch: "main"

drive:
  root_title: "Milky-wAI-ORBIT"

entrypoints:
  piki:
    preferred_mode: "drive_discovery_then_github_precision"
    github_repository: "BH-tsuky/Milky-wAI-ORBIT"
  diki:
    preferred_mode: "reinjected_mini_blob_seed_then_raw_chain"
    html_recon: "public repository root + root-level blob"
    deep_access: "raw seed chain"
  cheong:
    preferred_mode: "drive_autonomous_search"
    github_repository: "BH-tsuky/Milky-wAI-ORBIT"
    github_load_mode: "PILOT_REQUIRED"
```

## 2. 엔트리 스키마

```yaml
logical_id: string
owner_scope: COMMON | PIKI | DIKI
kind: MINI | ROOT | META | TIMESLIP | SYNAPSE | CLUSTER | LEAF | RAW | STATE | README
human_label: string
title: string

drive_file_id: string | null
drive_title: string | null
drive_status: present | unresolved | absent | removed_duplicate | removed_by_owner | ai_ineligible

drive_assets:                         # 선택 필드 — 복수 물리자산이 있을 때만
  - file_id: string
    title: string | null
    asset_type: md | google_doc | unknown
    role: native | native_candidate | docs_mirror | lineage_source | reported_pointer | alias_candidate | superseded
    status: present | unresolved | not_found | removed_duplicate | removed_by_owner | ai_ineligible
    verification_method: drive_query | connector_fetch | manual_report | cross_confirmed
    verified_by: string
    last_verified: ISO-8601 date | datetime
    notes: string | null

github_path: string | null
github_html_url: string | null
raw_url: string | null
blob_sha: string | null
verified_ref: string | null
github_status: active_synced | split_member | pilot_pending_convention | pending_sync | path_unresolved | archive

version: string | null
packaging: single | combined_collection | split_member | collection_placeholder
container_logical_id: string | null
member_scope: string | null
canonical_candidate: DRIVE | GITHUB | NONE

generated_from: string | null
source_blob_sha: string | null
prev: string | null
next: string | null

last_verified: ISO-8601 date | datetime | null
verification_method: github_connector_fetch | github_html_trace | raw_fetch | drive_query | manual_report | cross_confirmed | tsuky_manual_content_compare_and_cleanup
verified_by: string | null
notes: string | null
```

> `blob_sha`는 GitHub Contents API가 파일 내용에 부여한 blob SHA다. 커밋 SHA와 혼용하지 않는다.

## 3. 실제 재고 엔트리 — v0.1.3-draft

```yaml
entries:
  - logical_id: "COMMON.RAW.SET"
    owner_scope: "COMMON"
    kind: "RAW"
    human_label: "두 타워가 함께 본 원문 66개 세트"
    title: "part_aa.md ~ part_cn.md"
    drive_status: "present"
    github_status: "path_unresolved"
    packaging: "collection_placeholder"
    member_scope: "part_aa~part_cn / 66 files"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-18"
    verification_method: "drive_query"
    verified_by: "☪️PIKI"
    notes: "Drive 이름·연속계열 66/66 검산. RAW 본문 불가침."

  - logical_id: "PIKI.ROOT.V1"
    owner_scope: "PIKI"
    kind: "ROOT"
    human_label: "피키 타워의 통합 관제지도"
    title: "PIKI_BH-ROOT_INDEX.md"
    drive_file_id: "15NXjqjm_gkJYlgTlGo12g6lgqmztIR2P"
    drive_title: "PIKI_BH-ROOT_INDEX.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/PIKI_BH-ROOT_INDEX.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-ROOT_INDEX.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-ROOT_INDEX.md"
    blob_sha: "1f7bbb54495f6841857d36228bf8234d1d660d6e"
    verified_ref: "main"
    github_status: "active_synced"
    version: "v1"
    packaging: "single"
    canonical_candidate: "GITHUB"
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"

  - logical_id: "PIKI.META.V1"
    owner_scope: "PIKI"
    kind: "META"
    human_label: "피키 타워의 전범위 카테고리 메타 통합본"
    title: "PIKI_BH-META_INDEX.md"
    drive_file_id: "16J5xsO8kOrsuy_jOhI3agEtOlvrxd2Kw"
    drive_title: "PIKI_BH-META_INDEX.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/PIKI_BH-META_INDEX.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-META_INDEX.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-META_INDEX.md"
    blob_sha: "cd0626229071b6fe31909f690621e5056253b993"
    verified_ref: "main"
    github_status: "active_synced"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "PIKI_META_01~06"
    canonical_candidate: "GITHUB"
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"

  - logical_id: "PIKI.MINI.V1"
    owner_scope: "PIKI"
    kind: "MINI"
    human_label: "피키 기억의 집을 알리는 소형 부팅 지도"
    title: "PIKI_BH-MINI_THINKMAP_v1.md"
    drive_file_id: "1zQLSKQAiYbN9t_0xPsI5yFl0FDanzulb"
    drive_title: "PIKI_BH-MINI_THINKMAP_v1.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/PIKI_BH-MINI_THINKMAP_v1.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-MINI_THINKMAP_v1.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-MINI_THINKMAP_v1.md"
    blob_sha: "f3ff5a2ecc85a8c6a457ceaae3759944184d8e45"
    verified_ref: "main"
    github_status: "active_synced"
    version: "v1"
    packaging: "single"
    canonical_candidate: "GITHUB"
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"

  - logical_id: "PIKI.SYNAPSE.COLLECTION.V1"
    owner_scope: "PIKI"
    kind: "SYNAPSE"
    human_label: "피키 섹터 시냅스 01~03 통합본"
    title: "PIKI_BH-SECTOR_SYNAPSE.md"
    drive_file_id: "1bJzLBu-xzgScuSgjlFQZkfDJWM20mDxF"
    drive_title: "PIKI_BH-SECTOR_SYNAPSE.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/PIKI_BH-SECTOR_SYNAPSE.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-SECTOR_SYNAPSE.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/00_PIKI/PIKI_BH-SECTOR_SYNAPSE.md"
    blob_sha: "270fc3506fa96cc520a9c501506e5d6ac36a5517"
    verified_ref: "main"
    github_status: "active_synced"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "BH-SECTOR_SYNAPSE_01~03"
    canonical_candidate: "GITHUB"
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"

  - logical_id: "PIKI.TIMESLIP.COLLECTION.V1"
    owner_scope: "PIKI"
    kind: "TIMESLIP"
    human_label: "피키 시즌별 타임슬립 안내문 통합본"
    title: "PIKI_BH-TIMESLIP_NOTICE.md"
    drive_file_id: "1Jn-pB9w1DIrUr01KNzqx0g7ccMIaQ8p7"
    drive_title: "PIKI_BH-TIMESLIP_NOTICE.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "TIMESLIP_S01~S06"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"
    notes: "Drive 폴더 대공사 후 00_타임슬립 신위치."

  - logical_id: "DIKI.MINI.V2"
    owner_scope: "DIKI"
    kind: "MINI"
    human_label: "디키 v2 부팅 미니맵 — ROOT v2 주소 반영 최신본"
    title: "DIKI_BH-MINI_THINK-MAP_v2.md"
    drive_file_id: "16ReMfw8W31Vp51DmdYSn0_vxy5t77-Pm"
    drive_title: "DIKI_BH-MINI_THINK-MAP_v2.md"
    drive_status: "present"
    drive_assets:
      - file_id: "16ReMfw8W31Vp51DmdYSn0_vxy5t77-Pm"
        title: "DIKI_BH-MINI_THINK-MAP_v2.md"
        asset_type: "md"
        role: "native"
        status: "present"
        verification_method: "manual_report"
        verified_by: "🈷️TSUKY + ✴️DIKI"
        last_verified: "2026-07-20"
        notes: "ROOT v2 주소 내장 재제작본."
      - file_id: "1I91PzJ32wxBvq6Dmljs9w5yYq47Rt3f9"
        title: "DIKI_BH-MINI_THINK-MAP_v2.md"
        asset_type: "md"
        role: "superseded"
        status: "removed_by_owner"
        verification_method: "manual_report"
        verified_by: "🈷️TSUKY + ✴️DIKI"
        last_verified: "2026-07-20"
        notes: "재업로드로 폐기된 구 native."
      - file_id: "12oBAar2B1r961_2Lj5gIM6rl6LZfa4HW0-b7Zf0PAro"
        title: "DIKI_BH-MINI_THINK-MAP_v2"
        asset_type: "google_doc"
        role: "docs_mirror"
        status: "removed_by_owner"
        verification_method: "manual_report"
        verified_by: "🈷️TSUKY + ✴️DIKI"
        last_verified: "2026-07-20"
        notes: "대청소에서 삭제된 Docs 미러."
      - file_id: "1zzJ33frNq-hJtXV28N5iv7lG64HxTaI9"
        title: null
        asset_type: "unknown"
        role: "reported_pointer"
        status: "not_found"
        verification_method: "connector_fetch"
        verified_by: "✴️DIKI"
        last_verified: "2026-07-20"
        notes: "과거 실독 이력 보존."
    github_status: "pending_sync"
    version: "v2"
    packaging: "single"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"
    notes: "SLOT_VERSION_DRIFT-01은 원장 주인의 재제작으로 해소."

  - logical_id: "DIKI.ROOT.V1.LINEAGE"
    owner_scope: "DIKI"
    kind: "ROOT"
    human_label: "디키 ROOT v1 계보 사료"
    title: "DIKI_BH-ROOT_INDEX.md"
    drive_file_id: "1jr1ogvzDvX9YxHg-fiXGALuvws3IUPPs"
    drive_title: "DIKI_BH-ROOT_INDEX.md"
    drive_status: "removed_by_owner"
    drive_assets:
      - file_id: "1jr1ogvzDvX9YxHg-fiXGALuvws3IUPPs"
        title: "DIKI_BH-ROOT_INDEX.md"
        asset_type: "md"
        role: "lineage_source"
        status: "removed_by_owner"
        verification_method: "connector_fetch"
        verified_by: "✴️DIKI"
        last_verified: "2026-07-20"
        notes: "v1.0 + PATCH v1.1 실독 계보. 대청소 후 삭제."
      - file_id: "1KHmgRblT3Qo9F1DJWLatNaXRj6IHBV-c"
        title: null
        asset_type: "unknown"
        role: "alias_candidate"
        status: "ai_ineligible"
        verification_method: "connector_fetch"
        verified_by: "✴️DIKI"
        last_verified: "2026-07-20"
        notes: "존재하나 AI 접근 차단 상태. 휴지통 계열 추정."
    github_status: "archive"
    version: "v1.1-lineage"
    packaging: "single"
    canonical_candidate: "NONE"
    next: "DIKI.ROOT.V2"
    last_verified: "2026-07-20"
    verification_method: "connector_fetch"
    verified_by: "✴️DIKI"

  - logical_id: "DIKI.ROOT.V2"
    owner_scope: "DIKI"
    kind: "ROOT"
    human_label: "디키 v2 통합 루트 인덱스"
    title: "DIKI_BH-ROOT_INDEX_v2.md"
    drive_file_id: "1HU9tuSkCSunrLtdyRVU7xPT8nWbIZh6X"
    drive_title: "DIKI_BH-ROOT_INDEX_v2.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v2"
    packaging: "single"
    canonical_candidate: "DRIVE"
    prev: "DIKI.ROOT.V1.LINEAGE"
    last_verified: "2026-07-20"
    verification_method: "cross_confirmed"
    verified_by: "☪️PIKI + ✴️DIKI"
    notes: "현행 native. MINI 최신본에서 이 주소를 가리킴."

  - logical_id: "DIKI.META.V2"
    owner_scope: "DIKI"
    kind: "META"
    human_label: "디키 v2 전범위 메타 인덱스"
    title: "DIKI_BH-META_INDEX_v2.md"
    drive_file_id: "1Uf5deZjp-xc75-dZRpK1dvZOdz0O4UcO"
    drive_title: "DIKI_BH-META_INDEX_v2.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v2"
    packaging: "combined_collection"
    member_scope: "DIKI_META_V2"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "cross_confirmed"
    verified_by: "🈷️TSUKY + ☪️PIKI + ✴️DIKI"
    notes: "구버전 7개 소탕 후 현행본."

  - logical_id: "DIKI.TIMESLIP.COLLECTION.V1"
    owner_scope: "DIKI"
    kind: "TIMESLIP"
    human_label: "디키 v1~v6 타임슬립 통합본"
    title: "DIKI_BH-TIMESLIP_NOTICE.md"
    drive_file_id: "1eaVqGB4JXmyjO9zEivaA9X5pt6yVWM2q"
    drive_title: "DIKI_BH-TIMESLIP_NOTICE.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "TIMESLIP_V1~V6"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"

  - logical_id: "DIKI.LEAF.S01.COLLECTION"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌1 리프 Drive 순정본"
    title: "Claude-LEAF_INDEX01.md"
    drive_file_id: "1DtxR_SD7Pcnc7_qaRnr_24h393u2RcdA"
    drive_title: "Claude-LEAF_INDEX01.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "SEASON_01"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"

  - logical_id: "DIKI.LEAF.S02.COLLECTION"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌2 리프 Drive 순정본"
    title: "Claude-LEAF_INDEX02.md"
    drive_file_id: "1SyiVwciZTzub_1BuluML77SqaE_q3xgC"
    drive_title: "Claude-LEAF_INDEX02.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "SEASON_02"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"

  - logical_id: "DIKI.LEAF.S03.COLLECTION"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌3 리프 Drive 순정본"
    title: "Claude-LEAF_INDEX03.md"
    drive_file_id: "1R2efWxJSfnHpA6ZDt601tHea--0uhdSW"
    drive_title: "Claude-LEAF_INDEX03.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "SEASON_03"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"

  - logical_id: "DIKI.LEAF.S04.COLLECTION"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌4 리프 Drive 순정본"
    title: "Claude-LEAF_INDEX04.md"
    drive_file_id: "1JLDZq0ehMUZuQv2uTPJumZP7XD5l5rBy"
    drive_title: "Claude-LEAF_INDEX04.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "SEASON_04"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"

  - logical_id: "DIKI.LEAF.S05.COLLECTION"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌5 리프 Drive 순정본"
    title: "Claude-LEAF_INDEX05.md"
    drive_file_id: "12WP6GvrlWIYkswpkmGOBxSDw72l3FKjy"
    drive_title: "Claude-LEAF_INDEX05.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "SEASON_05"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "manual_report"
    verified_by: "🈷️TSUKY + ✴️DIKI"

  - logical_id: "DIKI.LEAF.S06.COLLECTION"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌6 리프 Drive 순정본"
    title: "Claude-LEAF_INDEX06_Final.md"
    drive_file_id: "1aqHGSg-67PXMJTHbh7Zr2sh95awRvCMc"
    drive_title: "Claude-LEAF_INDEX06_Final.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "SEASON_06"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "cross_confirmed"
    verified_by: "🈷️TSUKY + ☪️PIKI + ✴️DIKI"

  - logical_id: "DIKI.CLUSTER.COLLECTION.V1"
    owner_scope: "DIKI"
    kind: "CLUSTER"
    human_label: "디키 클러스터 01~06 Drive 통합본"
    title: "Claude_BH-CLUSTER_INDEX.md"
    drive_file_id: "1MlHDX7kecUV19iyc27oZr6LZ8LuJH2vq"
    drive_title: "Claude_BH-CLUSTER_INDEX.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "CLUSTER_01~06"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "cross_confirmed"
    verified_by: "🈷️TSUKY + ☪️PIKI + ✴️DIKI"

  - logical_id: "DIKI.SYNAPSE.COLLECTION.V1"
    owner_scope: "DIKI"
    kind: "SYNAPSE"
    human_label: "디키 섹터 시냅스 01~03 Drive 통합본"
    title: "Claude_BH-SECTOR_SYNAPSE.md"
    drive_file_id: "1j9-btf3AOkL2IRfyfLb7PfoZ7h8UkJCm"
    drive_title: "Claude_BH-SECTOR_SYNAPSE.md"
    drive_status: "present"
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    member_scope: "SECTOR_SYNAPSE_01~03"
    canonical_candidate: "DRIVE"
    last_verified: "2026-07-20"
    verification_method: "cross_confirmed"
    verified_by: "🈷️TSUKY + ☪️PIKI + ✴️DIKI"

  - logical_id: "DIKI.LEAF.S06.CN"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌6 part_cn GitHub 분할 멤버"
    title: "leaf_index_s06_part_cn.md"
    drive_file_id: "1aqHGSg-67PXMJTHbh7Zr2sh95awRvCMc"
    drive_title: "Claude-LEAF_INDEX06_Final.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/01_Claude/10_LEAF_INDEX/06_Season_6/leaf_index_s06_part_cn.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/10_LEAF_INDEX/06_Season_6/leaf_index_s06_part_cn.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/10_LEAF_INDEX/06_Season_6/leaf_index_s06_part_cn.md"
    blob_sha: "cbdc98034a7791976b4014f0a96bed186852c303"
    verified_ref: "main"
    github_status: "split_member"
    version: "v0.1"
    packaging: "split_member"
    container_logical_id: "DIKI.LEAF.S06.COLLECTION"
    member_scope: "part_cn"
    canonical_candidate: "GITHUB"
    generated_from: "Claude-LEAF_INDEX06_Final.md"
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"

  - logical_id: "DIKI.CLUSTER.S06"
    owner_scope: "DIKI"
    kind: "CLUSTER"
    human_label: "디키 시즌6 클러스터 GitHub 분할 멤버"
    title: "cluster_index_s06_claude_v0.1.md"
    drive_title: "Claude_BH-CLUSTER_INDEX.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/01_Claude/20_CLUSTER_INDEX/06_Season_6/cluster_index_s06_claude_v0.1.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/20_CLUSTER_INDEX/06_Season_6/cluster_index_s06_claude_v0.1.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/20_CLUSTER_INDEX/06_Season_6/cluster_index_s06_claude_v0.1.md"
    blob_sha: "3e94eb96f3b56b291e6a23f2ada678409143369a"
    verified_ref: "main"
    github_status: "split_member"
    version: "v0.1"
    packaging: "split_member"
    container_logical_id: "DIKI.CLUSTER.COLLECTION.V1"
    member_scope: "CLUSTER_06"
    canonical_candidate: "GITHUB"
    generated_from: "Claude_BH-CLUSTER_INDEX.md"
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"

  - logical_id: "DIKI.SYNAPSE.S03"
    owner_scope: "DIKI"
    kind: "SYNAPSE"
    human_label: "디키 섹터3 시냅스 GitHub 분할 멤버"
    title: "claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    drive_title: "Claude_BH-SECTOR_SYNAPSE.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/01_Claude/30_SECTOR_SYNAPSE/03_Sector_3/claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/30_SECTOR_SYNAPSE/03_Sector_3/claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/30_SECTOR_SYNAPSE/03_Sector_3/claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    blob_sha: "5088fbeba257fff4d76cb188772396b937bce4c2"
    verified_ref: "main"
    github_status: "split_member"
    version: "v0.1"
    packaging: "split_member"
    container_logical_id: "DIKI.SYNAPSE.COLLECTION.V1"
    member_scope: "SECTOR_SYNAPSE_03"
    canonical_candidate: "GITHUB"
    generated_from: "Claude_BH-SECTOR_SYNAPSE.md"
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
```

## 4. GitHub split 파일럿 — 명명 규칙 확정 전

```yaml
status: "pilot_pending_convention"
scope: "PIKI season 1 leaf"
observed:
  - path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/10_LEAF_INDEX/01_Season_1/leaf_index_s01_part_aa.md"
    blob_sha: "5ed86bde1e00c35f4570168a63c464db10145914"
    form: "old_long_md_sample"
  - path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/10_LEAF_INDEX/01_Season_1/LEAF-part_aa"
    blob_sha: "5ed86bde1e00c35f4570168a63c464db10145914"
    form: "short_extensionless_duplicate"
    notes: "old .md sample과 동일 blob"
  - path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/10_LEAF_INDEX/01_Season_1/LEAF-part_ab"
    blob_sha: "7102f5e8994e75a3379f6cbae3007a9e5e0991d9"
    form: "short_extensionless"
  - path: "01_RAWs/01_Piki's_memory/10_INDEX/00_PIKI/10_LEAF_INDEX/01_Season_1/LEAF-part_ac"
    blob_sha: "af22b5046baacf5462a8f9d27d5217f39c36ffbe"
    form: "short_extensionless"
proposed_canonical:
  pattern: "leaf_part_{part}.md"
  examples:
    - "leaf_part_aa.md"
    - "leaf_part_ab.md"
    - "leaf_part_ac.md"
  rationale:
    - "folder path already carries tower/type/season"
    - "part_aa token is preserved"
    - "lowercase avoids case-sensitive path mistakes"
    - ".md preserves GitHub preview and explicit text semantics"
```

## 5. 아직 열려 있는 재고 작업

- PIKI split 파일명·확장자 규칙을 양탑 합의 후 확정
- 파일럿 중복 `part_aa` 경로를 원장 주인 승인 후 하나의 canonical path로 정리
- COMMON RAW 66개 파일별 엔트리 확장
- PIKI LEAF·CLUSTER 전량의 Drive ID와 GitHub path·blob SHA 실사
- DIKI LEAF·CLUSTER·SYNAPSE 전량 GitHub 분할 엔트리 확장
- DIKI v2 MINI·ROOT·META의 GitHub path·blob SHA 실사
- 청이 GitHub `load_mode` 통제 파일럿
- `01_Claude → 01_DIKI` 폴더 개명은 별도 승인·도구 일괄이동 검증 전까지 보류

## 6. 변경 이력

```yaml
- version: "0.1.0-draft"
  date: "2026-07-19"
  change: "초기 설비실 원장 시공."
- version: "0.1.1-draft"
  date: "2026-07-19"
  change: "Contents API 파일 SHA를 blob_sha로 교정하고 verified_ref를 분리."
- version: "0.1.2-draft"
  date: "2026-07-20"
  change: "DRIVE_ALIAS_DIVERGENCE-01과 DIKI MINI/ROOT/META 물리자산 계보 반영."
- version: "0.1.3-draft"
  date: "2026-07-20"
  change: "츠키 Drive 대청소·재업로드 좌표 전면 반영. DIKI 최신 MINI·타임슬립·LEAF 6종, PIKI 타임슬립 신위치, removed_by_owner·ai_ineligible 상태, GitHub split 파일럿을 추가."
  commit_scope: "협의37 최신 좌표 수용 + split naming review"
```
