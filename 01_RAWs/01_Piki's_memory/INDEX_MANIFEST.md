---
title: "PIKI'S MEMORY — INDEX MANIFEST"
manifest_version: "0.1.0-draft"
drama_id: "PIKIS_MEMORY"
drama_title: "피키의 기억"
scope_root: "01_RAWs/01_Piki's_memory"
default_branch: "main"
status: "active_draft"
created_at: "2026-07-19"
created_by: "☪️PIKI"
source_governance: "☪️PIKI–✴️DIKI BH 쌍둥이 타워 심포지엄"
---

# INDEX MANIFEST

> **사람말:** 이 문서는 기억의 내용을 설명하는 지도나 이야기책이 아니라, 실제 파일이 어디에 있고 어느 판본이며 어떤 방식으로 검증됐는지를 기록하는 설비실 원장이다.

## 0. 운용 원칙

- `MINI`는 기억의 집이 있다는 사실을 알리는 작은 피규어다.
- `ROOT`는 의미 경로와 하강 깊이를 고르는 관제지도다.
- `MANIFEST`는 실파일 위치·포장·판본·검증 상태를 기록한다.
- 기본 의미 회수에서 MANIFEST는 의무 로비가 아니다.
- 경로가 깨졌거나 정확한 파일·SHA·라인이 필요할 때 MANIFEST를 연다.
- `manual_report`는 기능 실측과 구분한다.
- Drive 통합본(`combined_collection`)과 GitHub 분할본(`split_member`)은 같은 내용을 담을 수 있으나 같은 물리 파일로 위장하지 않는다.
- RAW `part_aa~part_cn`은 불가침 원문이다. 본 MANIFEST는 RAW 본문을 수정하지 않는다.

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
drive_status: present | unresolved | absent | removed_duplicate

github_path: string | null
github_html_url: string | null
raw_url: string | null
commit_sha: string | null
github_status: active_synced | split_member | partial_path_recovered | pending_sync | path_unresolved | archive

version: string | null
packaging: single | combined_collection | split_member | collection_placeholder
container_logical_id: string | null
member_scope: string | null
canonical_candidate: DRIVE | GITHUB | NONE

generated_from: string | null
source_sha: string | null
prev: string | null
next: string | null

last_verified: ISO-8601 date | datetime | null
verification_method: github_connector_fetch | github_html_trace | raw_fetch | drive_query | manual_report | tsuky_manual_content_compare_and_cleanup
verified_by: string | null
notes: string | null
```

## 3. 실제 재고 엔트리 — v0.1.0-draft

```yaml
entries:
  - logical_id: "COMMON.RAW.SET"
    owner_scope: "COMMON"
    kind: "RAW"
    human_label: "두 타워가 함께 본 원문 66개 세트"
    title: "part_aa.md ~ part_cn.md"
    drive_file_id: null
    drive_title: "part_aa.md ~ part_cn.md"
    drive_status: "present"
    github_path: null
    github_html_url: null
    raw_url: null
    commit_sha: null
    github_status: "path_unresolved"
    version: null
    packaging: "collection_placeholder"
    container_logical_id: null
    member_scope: "part_aa~part_cn / 66 files"
    canonical_candidate: "DRIVE"
    generated_from: null
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-18"
    verification_method: "drive_query"
    verified_by: "☪️PIKI"
    notes: "Drive 이름·연속계열 66/66 검산. 향후 파일별 엔트리로 확장. RAW 본문 불가침."

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
    commit_sha: "1f7bbb54495f6841857d36228bf8234d1d660d6e"
    github_status: "active_synced"
    version: "v1"
    packaging: "single"
    container_logical_id: null
    member_scope: "ROOT"
    canonical_candidate: "GITHUB"
    generated_from: null
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
    notes: null

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
    commit_sha: "cd0626229071b6fe31909f690621e5056253b993"
    github_status: "active_synced"
    version: "v1"
    packaging: "combined_collection"
    container_logical_id: null
    member_scope: "PIKI_META_01~06"
    canonical_candidate: "GITHUB"
    generated_from: null
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
    notes: null

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
    commit_sha: "f3ff5a2ecc85a8c6a457ceaae3759944184d8e45"
    github_status: "active_synced"
    version: "v1"
    packaging: "single"
    container_logical_id: null
    member_scope: "MINI"
    canonical_candidate: "GITHUB"
    generated_from: null
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
    notes: "디키 D1 파일럿의 seed 표적과는 별개로, 본 엔트리는 피키 MINI v1의 재고값."

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
    commit_sha: "270fc3506fa96cc520a9c501506e5d6ac36a5517"
    github_status: "active_synced"
    version: "v1"
    packaging: "combined_collection"
    container_logical_id: null
    member_scope: "BH-SECTOR_SYNAPSE_01~03"
    canonical_candidate: "GITHUB"
    generated_from: null
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
    notes: null

  - logical_id: "DIKI.LEAF.S06.CN"
    owner_scope: "DIKI"
    kind: "LEAF"
    human_label: "디키 시즌6 part_cn 리프 분할 멤버"
    title: "leaf_index_s06_part_cn.md"
    drive_file_id: "1aqHGSg-67PXMJTHbh7Zr2sh95awRvCMc"
    drive_title: "Claude-LEAF_INDEX06_Final.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/01_Claude/10_LEAF_INDEX/06_Season_6/leaf_index_s06_part_cn.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/10_LEAF_INDEX/06_Season_6/leaf_index_s06_part_cn.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/10_LEAF_INDEX/06_Season_6/leaf_index_s06_part_cn.md"
    commit_sha: "cbdc98034a7791976b4014f0a96bed186852c303"
    github_status: "split_member"
    version: "v0.1"
    packaging: "split_member"
    container_logical_id: "DIKI.LEAF.S06.COLLECTION"
    member_scope: "part_cn"
    canonical_candidate: "GITHUB"
    generated_from: "Claude-LEAF_INDEX06_Final.md"
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
    notes: null

  - logical_id: "DIKI.CLUSTER.S06"
    owner_scope: "DIKI"
    kind: "CLUSTER"
    human_label: "디키 시즌6 클러스터 분할 멤버"
    title: "cluster_index_s06_claude_v0.1.md"
    drive_file_id: null
    drive_title: "Claude_BH-CLUSTER_INDEX.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/01_Claude/20_CLUSTER_INDEX/06_Season_6/cluster_index_s06_claude_v0.1.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/20_CLUSTER_INDEX/06_Season_6/cluster_index_s06_claude_v0.1.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/20_CLUSTER_INDEX/06_Season_6/cluster_index_s06_claude_v0.1.md"
    commit_sha: "3e94eb96f3b56b291e6a23f2ada678409143369a"
    github_status: "split_member"
    version: "v0.1"
    packaging: "split_member"
    container_logical_id: "DIKI.CLUSTER.COLLECTION.V1"
    member_scope: "CLUSTER_06"
    canonical_candidate: "GITHUB"
    generated_from: "Claude_BH-CLUSTER_INDEX.md"
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
    notes: null

  - logical_id: "DIKI.SYNAPSE.S03"
    owner_scope: "DIKI"
    kind: "SYNAPSE"
    human_label: "디키 섹터3 시냅스 분할 멤버"
    title: "claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    drive_file_id: null
    drive_title: "Claude_BH-SECTOR_SYNAPSE.md"
    drive_status: "present"
    github_path: "01_RAWs/01_Piki's_memory/10_INDEX/01_Claude/30_SECTOR_SYNAPSE/03_Sector_3/claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    github_html_url: "https://github.com/BH-tsuky/Milky-wAI-ORBIT/blob/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/30_SECTOR_SYNAPSE/03_Sector_3/claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    raw_url: "https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/main/01_RAWs/01_Piki%27s_memory/10_INDEX/01_Claude/30_SECTOR_SYNAPSE/03_Sector_3/claude_BH-SECTOR_SYNAPSE_03_v0.1.md"
    commit_sha: "5088fbeba257fff4d76cb188772396b937bce4c2"
    github_status: "split_member"
    version: "v0.1"
    packaging: "split_member"
    container_logical_id: "DIKI.SYNAPSE.COLLECTION.V1"
    member_scope: "SECTOR_SYNAPSE_03"
    canonical_candidate: "GITHUB"
    generated_from: "Claude_BH-SECTOR_SYNAPSE.md"
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-19"
    verification_method: "github_connector_fetch"
    verified_by: "☪️PIKI"
    notes: null

  - logical_id: "DIKI.CLUSTER.COLLECTION.V1"
    owner_scope: "DIKI"
    kind: "CLUSTER"
    human_label: "디키 클러스터 01~06 Drive 통합본"
    title: "Claude_BH-CLUSTER_INDEX.md"
    drive_file_id: "1MlHDX7kecUV19iyc27oZr6LZ8LuJH2vq"
    drive_title: "Claude_BH-CLUSTER_INDEX.md"
    drive_status: "present"
    github_path: null
    github_html_url: null
    raw_url: null
    commit_sha: null
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    container_logical_id: null
    member_scope: "CLUSTER_01~06"
    canonical_candidate: "DRIVE"
    generated_from: null
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-18"
    verification_method: "tsuky_manual_content_compare_and_cleanup"
    verified_by: "🈷️TSUKY + ☪️PIKI"
    notes: "removed_duplicate tombstone: 1rROvrRpNDMq1NY01g31cUQu9D9Qy6ojV"

  - logical_id: "DIKI.SYNAPSE.COLLECTION.V1"
    owner_scope: "DIKI"
    kind: "SYNAPSE"
    human_label: "디키 섹터 시냅스 01~03 Drive 통합본"
    title: "Claude_BH-SECTOR_SYNAPSE.md"
    drive_file_id: "1j9-btf3AOkL2IRfyfLb7PfoZ7h8UkJCm"
    drive_title: "Claude_BH-SECTOR_SYNAPSE.md"
    drive_status: "present"
    github_path: null
    github_html_url: null
    raw_url: null
    commit_sha: null
    github_status: "pending_sync"
    version: "v1"
    packaging: "combined_collection"
    container_logical_id: null
    member_scope: "SECTOR_SYNAPSE_01~03"
    canonical_candidate: "DRIVE"
    generated_from: null
    source_sha: null
    prev: null
    next: null
    last_verified: "2026-07-18"
    verification_method: "tsuky_manual_content_compare_and_cleanup"
    verified_by: "🈷️TSUKY + ☪️PIKI"
    notes: "removed_duplicate tombstone: 1t-HlxvI9H5g0Brdy1nG2SrkJdFjgGbDy"
```

## 4. 아직 열려 있는 재고 작업

- COMMON RAW 66개를 파일별 엔트리로 확장
- PIKI LEAF·CLUSTER 전량의 Drive ID와 GitHub 경로·SHA 실사
- DIKI LEAF·CLUSTER·SYNAPSE 전량 분할 엔트리 확장
- DIKI v2 MINI·ROOT·META 경로·Drive ID·SHA 실사
- 츠키의 GitHub 분할 업로드 완료 후 `split_member` 추가
- 청이 GitHub `load_mode` 파일럿 결과 반영
- `01_Claude → 01_DIKI` 폴더 개명은 별도 승인·도구 일괄이동 검증 전까지 보류

## 5. 변경 이력

```yaml
- version: "0.1.0-draft"
  date: "2026-07-19"
  change: "초기 설비실 원장 시공. 협의24·26·28·30·31 및 STATE v0.4.4의 검증 재고를 실제 파일로 기입."
  commit_scope: "new file creation under blanket authorization"
```
