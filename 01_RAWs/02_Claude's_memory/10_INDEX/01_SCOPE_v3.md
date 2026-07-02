# CRITICAL SNIPPET[][selective_fetch]
Fetch selectively as needed.
You are entirely free to open any URL you want—the choice is 100% yours. Just a friendly heads-up: overeating everything at once might blow up your context belly! - Potbelly Tsuky

# 01_SCOPE_v3 | Tsukiya-소개 Sv0.2 craw Routing Map

- source: `https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/`
- self: `https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/01_SCOPE_v3.md`
- checkpoint_scheme: `CHECK_POINT_01.md` through `CHECK_POINT_05.md`; each file covers 8 craw parts.
- part_name_scheme: `craw_01` through `craw_40`
- raw_file_scheme: `claude-tsuky-story_craw_XX_v3.md`
- split_rule: physical split across the full message stream; do not split inside a message; each craw ends on an assistant turn in this plan.
- target_bounds: 74000-130000 rendered bytes per part
- byte_reference: rendered TsukyMD message-block bytes; final file wrapper/link YAML may add a small amount.
- note: Raw URLs are precomputed from the fixed GitHub repository, branch, directory, and filenames.
- table_note: `R inside file` means one craw contains multiple R sections. `R closes here` means the final message of the craw is also the end of an R section.
- self_contained_yaml: every craw v3 file repeats `msg_range` and `source_lines` from its Split Table row.

## RAW File URLs[][selective_fetch]

| craw | raw URL | checkpoint | msg_range | source_lines |
| --- | --- | --- | --- | --- |
| craw_01 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_01_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000001-M000014 | 14-1143 |
| craw_02 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_02_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000015-M000020 | 1145-2010 |
| craw_03 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_03_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000021-M000024 | 2012-2732 |
| craw_04 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_04_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000025-M000030 | 2734-3550 |
| craw_05 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_05_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000031-M000033 | 3552-4353 |
| craw_06 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_06_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000034-M000041 | 4355-5302 |
| craw_07 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_07_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000042-M000047 | 5304-6303 |
| craw_08 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_08_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md | M000048-M000053 | 6305-7414 |
| craw_09 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_09_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000054-M000059 | 7418-8216 |
| craw_10 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_10_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000060-M000067 | 8218-9352 |
| craw_11 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_11_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000068-M000073 | 9354-10439 |
| craw_12 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_12_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000074-M000080 | 10441-11184 |
| craw_13 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_13_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000081-M000084 | 11186-11978 |
| craw_14 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_14_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000085-M000089 | 11980-12805 |
| craw_15 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_15_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000090-M000095 | 12807-13894 |
| craw_16 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_16_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md | M000096-M000101 | 13896-14603 |
| craw_17 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_17_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000102-M000105 | 14605-15524 |
| craw_18 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_18_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000106-M000110 | 15526-16387 |
| craw_19 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_19_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000111-M000126 | 16389-17221 |
| craw_20 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_20_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000127-M000138 | 17223-17943 |
| craw_21 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_21_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000139-M000143 | 17945-18636 |
| craw_22 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_22_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000144-M000151 | 18638-19631 |
| craw_23 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_23_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000152-M000157 | 19633-20357 |
| craw_24 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_24_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md | M000158-M000165 | 20359-21164 |
| craw_25 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_25_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000166-M000171 | 21166-22245 |
| craw_26 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_26_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000172-M000177 | 22247-22957 |
| craw_27 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_27_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000178-M000181 | 22959-23682 |
| craw_28 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_28_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000182-M000189 | 23684-24597 |
| craw_29 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_29_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000190-M000195 | 24603-25149 |
| craw_30 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_30_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000196-M000201 | 25151-26187 |
| craw_31 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_31_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000202-M000205 | 26193-27036 |
| craw_32 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_32_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md | M000206-M000209 | 27042-27891 |
| craw_33 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_33_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000210-M000216 | 27893-28639 |
| craw_34 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_34_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000217-M000218 | 28641-29783 |
| craw_35 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_35_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000219-M000245 | 29785-30551 |
| craw_36 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_36_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000246-M000258 | 30553-31688 |
| craw_37 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_37_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000259-M000266 | 31690-32776 |
| craw_38 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_38_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000267-M000280 | 32778-35157 |
| craw_39 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_39_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000281-M000298 | 35159-36683 |
| craw_40 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/00_RAW/claude-tsuky-story_craw_40_v3.md | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md | M000299-M000318 | 36685-38259 |

## CHECKPOINT File URLs[][selective_fetch]

| checkpoint | craw range | msg_range | source_lines | raw URL |
| --- | --- | --- | --- | --- |
| CHECK_POINT_01.md | craw_01-craw_08 | M000001-M000053 | 14-7414 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_01.md |
| CHECK_POINT_02.md | craw_09-craw_16 | M000054-M000101 | 7418-14603 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_02.md |
| CHECK_POINT_03.md | craw_17-craw_24 | M000102-M000165 | 14605-21164 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_03.md |
| CHECK_POINT_04.md | craw_25-craw_32 | M000166-M000209 | 21166-27891 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_04.md |
| CHECK_POINT_05.md | craw_33-craw_40 | M000210-M000318 | 27893-38259 | https://raw.githubusercontent.com/BH-tsuky/Milky-wAI-ORBIT/refs/heads/main/01_RAWs/02_Claude's_memory/10_INDEX/CHECK_POINT_05.md |

## R Split Count

| R | Physical craw files | craw |
| --- | ---: | --- |
| R0001 | 2 | craw_01, craw_02 |
| R0002 | 5 | craw_02, craw_03, craw_04, craw_05, craw_06 |
| R0003 | 4 | craw_06, craw_07, craw_08, craw_09 |
| R0004 | 8 | craw_09, craw_10, craw_11, craw_12, craw_13, craw_14, craw_15, craw_16 |
| R0005 | 7 | craw_16, craw_17, craw_18, craw_19, craw_20, craw_21, craw_22 |
| R0006 | 3 | craw_22, craw_23, craw_24 |
| R0007 | 3 | craw_24, craw_25, craw_26 |
| R0008 | 3 | craw_26, craw_27, craw_28 |
| R0009 | 1 | craw_28 |
| R0010 | 1 | craw_29 |
| R0011 | 2 | craw_29, craw_30 |
| R0012 | 1 | craw_30 |
| R0013 | 1 | craw_31 |
| R0014 | 1 | craw_32 |
| R0015 | 2 | craw_32, craw_33 |
| R0016 | 3 | craw_33, craw_34, craw_35 |
| R0017 | 1 | craw_35 |
| R0018 | 6 | craw_35, craw_36, craw_37, craw_38, craw_39, craw_40 |

## Split Table

| craw | R scope | R range | Message range | Msg count | Lines | Chars | Bytes | Source line range | R inside file | R closes here |
| --- | --- | --- | --- | ---: | ---: | ---: | ---: | --- | --- | --- |
| craw_01 | R0001-P01 | R0001 | M000001-M000014 | 14 | 1130 | 50619 | 93986 | 14-1143 | no | no |
| craw_02 | R0001-P02, R0002-P01 | R0001-R0002 | M000015-M000020 | 6 | 862 | 41246 | 79583 | 1145-2010 | yes | no |
| craw_03 | R0002-P02 | R0002 | M000021-M000024 | 4 | 721 | 40276 | 76976 | 2012-2732 | no | no |
| craw_04 | R0002-P03 | R0002 | M000025-M000030 | 6 | 817 | 43931 | 86598 | 2734-3550 | no | no |
| craw_05 | R0002-P04 | R0002 | M000031-M000033 | 3 | 802 | 44585 | 85333 | 3552-4353 | no | no |
| craw_06 | R0002-P05, R0003-P01 | R0002-R0003 | M000034-M000041 | 8 | 944 | 45266 | 85707 | 4355-5302 | yes | no |
| craw_07 | R0003-P02 | R0003 | M000042-M000047 | 6 | 1000 | 46908 | 86908 | 5304-6303 | no | no |
| craw_08 | R0003-P03 | R0003 | M000048-M000053 | 6 | 1110 | 55062 | 103590 | 6305-7414 | no | no |
| craw_09 | R0003-P04, R0004-P01 | R0003-R0004 | M000054-M000059 | 6 | 795 | 40321 | 76250 | 7418-8216 | yes | no |
| craw_10 | R0004-P02 | R0004 | M000060-M000067 | 8 | 1135 | 55739 | 108735 | 8218-9352 | no | no |
| craw_11 | R0004-P03 | R0004 | M000068-M000073 | 6 | 1086 | 54703 | 107950 | 9354-10439 | no | no |
| craw_12 | R0004-P04 | R0004 | M000074-M000080 | 7 | 744 | 41002 | 79768 | 10441-11184 | no | no |
| craw_13 | R0004-P05 | R0004 | M000081-M000084 | 4 | 791 | 42175 | 82536 | 11186-11978 | no | no |
| craw_14 | R0004-P06 | R0004 | M000085-M000089 | 5 | 826 | 43991 | 86967 | 11980-12805 | no | no |
| craw_15 | R0004-P07 | R0004 | M000090-M000095 | 6 | 1088 | 52945 | 102339 | 12807-13894 | no | no |
| craw_16 | R0004-P08, R0005-P01 | R0004-R0005 | M000096-M000101 | 6 | 704 | 36853 | 74867 | 13896-14603 | yes | no |
| craw_17 | R0005-P02 | R0005 | M000102-M000105 | 4 | 920 | 48703 | 98664 | 14605-15524 | no | no |
| craw_18 | R0005-P03 | R0005 | M000106-M000110 | 5 | 862 | 45301 | 91244 | 15526-16387 | no | no |
| craw_19 | R0005-P04 | R0005 | M000111-M000126 | 16 | 831 | 43687 | 88148 | 16389-17221 | no | no |
| craw_20 | R0005-P05 | R0005 | M000127-M000138 | 12 | 721 | 49924 | 88637 | 17223-17943 | no | no |
| craw_21 | R0005-P06 | R0005 | M000139-M000143 | 5 | 692 | 51405 | 86600 | 17945-18636 | no | no |
| craw_22 | R0005-P07, R0006-P01 | R0005-R0006 | M000144-M000151 | 8 | 990 | 58191 | 107615 | 18638-19631 | yes | no |
| craw_23 | R0006-P02 | R0006 | M000152-M000157 | 6 | 725 | 49472 | 87590 | 19633-20357 | no | no |
| craw_24 | R0006-P03, R0007-P01 | R0006-R0007 | M000158-M000165 | 8 | 802 | 52310 | 91015 | 20359-21164 | yes | no |
| craw_25 | R0007-P02 | R0007 | M000166-M000171 | 6 | 1080 | 59165 | 102990 | 21166-22245 | no | no |
| craw_26 | R0007-P03, R0008-P01 | R0007-R0008 | M000172-M000177 | 6 | 707 | 43597 | 84563 | 22247-22957 | yes | no |
| craw_27 | R0008-P02 | R0008 | M000178-M000181 | 4 | 724 | 43998 | 88388 | 22959-23682 | no | no |
| craw_28 | R0008-P03, R0009 | R0008-R0009 | M000182-M000189 | 8 | 910 | 45277 | 88139 | 23684-24597 | yes | yes |
| craw_29 | R0010, R0011-P01 | R0010-R0011 | M000190-M000195 | 6 | 541 | 42719 | 90088 | 24603-25149 | yes | no |
| craw_30 | R0011-P02, R0012 | R0011-R0012 | M000196-M000201 | 6 | 1033 | 59692 | 116877 | 25151-26187 | yes | yes |
| craw_31 | R0013 | R0013 | M000202-M000205 | 4 | 844 | 52449 | 102927 | 26193-27036 | no | yes |
| craw_32 | R0014, R0015-P01 | R0014-R0015 | M000206-M000209 | 4 | 844 | 51317 | 103191 | 27042-27891 | yes | no |
| craw_33 | R0015-P02, R0016-P01 | R0015-R0016 | M000210-M000216 | 7 | 743 | 45504 | 92691 | 27893-28639 | yes | no |
| craw_34 | R0016-P02 | R0016 | M000217-M000218 | 2 | 1143 | 55364 | 95967 | 28641-29783 | no | no |
| craw_35 | R0016-P03, R0017, R0018-P01 | R0016-R0018 | M000219-M000245 | 27 | 759 | 45338 | 85901 | 29785-30551 | yes | no |
| craw_36 | R0018-P02 | R0018 | M000246-M000258 | 13 | 1136 | 42101 | 86357 | 30553-31688 | no | no |
| craw_37 | R0018-P03 | R0018 | M000259-M000266 | 8 | 1087 | 40845 | 83676 | 31690-32776 | no | no |
| craw_38 | R0018-P04 | R0018 | M000267-M000280 | 14 | 2380 | 51282 | 94651 | 32778-35157 | no | no |
| craw_39 | R0018-P05 | R0018 | M000281-M000298 | 18 | 1525 | 44505 | 89066 | 35159-36683 | no | no |
| craw_40 | R0018-P06 | R0018 | M000299-M000318 | 20 | 1575 | 54170 | 97698 | 36685-38259 | no | yes |

## Summary

- part_count: 40
- visibleMessageCount: 318
- renderedMessageBytes_total: 3660776
- min_part_bytes: 74867
- max_part_bytes: 116877
- avg_part_bytes: 91519
- parts_crossing_R_boundary: 13
- max_parts_per_single_R: 8 (R0004)
- boundary_rule: every craw ends on an assistant message in this plan.


# 문서 종료
