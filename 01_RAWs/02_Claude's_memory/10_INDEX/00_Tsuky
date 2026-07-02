# Tsukiya-소개 Sv0.2 Split Plan, 40 Parts

- source: `03_출력/Tsukiya-소개_Sv0.2.md`
- basis: `02_작업중/Tsukiya-소개_Sv0.2_single-message-sizes.md`
- split_rule: physical split across the full message stream; do not split inside a message; R boundaries are reference points, not hard boundaries.
- target_bounds: 74000-110007 rendered bytes per part
- byte_basis: sum of rendered TsukyMD message-block bytes from the single-message size table; final file wrapper/scope metadata may add a small amount.
- note: Very short R sections may be grouped with neighboring R sections, matching the previous P0012 split-plan style.

## Summary

- part_count: 40
- visibleMessageCount: 318
- renderedMessageBytes_total: 3660498
- min_part_bytes: 75619
- max_part_bytes: 110007
- avg_part_bytes: 91512
- parts_crossing_R_boundary: 6
- max_parts_per_single_R: 7 (R0004)

## Split Table

| part | R scope | R range | Message range | Msg count | Lines | Chars | Bytes | Source line range | R boundary crossed |
| --- | --- | --- | --- | ---: | ---: | ---: | ---: | --- | --- |
| part_aa | R0001-P01 | R0001 | M000001-M000014 | 14 | 1117 | 50606 | 93973 | 14-1143 | no |
| part_ab | R0001-P02, R0002-P01 | R0001-R0002 | M000015-M000021 | 7 | 863 | 42241 | 81768 | 1145-2017 | yes |
| part_ac | R0002-P02 | R0002 | M000022-M000026 | 5 | 1080 | 57899 | 110007 | 2019-3102 | no |
| part_ad | R0002-P03 | R0002 | M000027-M000031 | 5 | 851 | 46291 | 90313 | 3104-3958 | no |
| part_ae | R0002-P04 | R0002 | M000032-M000036 | 5 | 764 | 41323 | 80415 | 3960-4727 | no |
| part_af | R0003-P01 | R0003 | M000037-M000045 | 9 | 1190 | 56674 | 105812 | 4733-5930 | no |
| part_ag | R0003-P02 | R0003 | M000046-M000051 | 6 | 1089 | 52611 | 98230 | 5932-7025 | no |
| part_ah | R0003-P03 | R0003 | M000052-M000057 | 6 | 821 | 41614 | 78732 | 7027-7854 | no |
| part_ai | R0004-P01 | R0004 | M000058-M000063 | 6 | 1095 | 56557 | 108031 | 7860-8959 | no |
| part_aj | R0004-P02 | R0004 | M000064-M000071 | 8 | 1095 | 53282 | 106144 | 8961-10062 | no |
| part_ak | R0004-P03 | R0004 | M000072-M000077 | 6 | 739 | 39773 | 77416 | 10064-10807 | no |
| part_al | R0004-P04 | R0004 | M000078-M000082 | 5 | 843 | 44788 | 87135 | 10809-11655 | no |
| part_am | R0004-P05 | R0004 | M000083-M000086 | 4 | 691 | 38678 | 76059 | 11659-12352 | no |
| part_an | R0004-P06 | R0004 | M000087-M000092 | 6 | 831 | 42783 | 83962 | 12354-13189 | no |
| part_ao | R0004-P07 | R0004 | M000093-M000099 | 7 | 1000 | 48987 | 96904 | 13191-14196 | no |
| part_ap | R0005-P01 | R0005 | M000100-M000104 | 5 | 916 | 48561 | 98144 | 14202-15121 | no |
| part_aq | R0005-P02 | R0005 | M000105-M000107 | 3 | 854 | 45090 | 91042 | 15123-15978 | no |
| part_ar | R0005-P03 | R0005 | M000108-M000112 | 5 | 847 | 43638 | 87167 | 15980-16830 | no |
| part_as | R0005-P04 | R0005 | M000113-M000134 | 22 | 761 | 48264 | 93485 | 16832-17615 | no |
| part_at | R0005-P05 | R0005 | M000135-M000142 | 8 | 664 | 51056 | 84303 | 17617-18287 | no |
| part_au | R0005-P06 | R0005 | M000143-M000147 | 5 | 970 | 57385 | 106411 | 18289-19262 | no |
| part_av | R0006-P01 | R0006 | M000148-M000155 | 8 | 765 | 51818 | 92685 | 19268-20039 | no |
| part_aw | R0006-P02 | R0006 | M000156-M000159 | 4 | 624 | 43412 | 75619 | 20041-20667 | no |
| part_ax | R0007-P01 | R0007 | M000160-M000168 | 9 | 999 | 59521 | 105454 | 20673-21679 | no |
| part_ay | R0007-P02 | R0007 | M000169-M000173 | 5 | 849 | 47683 | 82070 | 21681-22533 | no |
| part_az | R0008-P01 | R0008 | M000174-M000178 | 5 | 536 | 40203 | 85354 | 22539-23078 | no |
| part_ba | R0008-P02 | R0008 | M000179-M000183 | 5 | 1068 | 52596 | 96015 | 23080-24151 | no |
| part_bb | R0008-P03, R0009, R0010-P01 | R0008-R0010 | M000184-M000192 | 9 | 585 | 41192 | 90146 | 24153-24755 | yes |
| part_bc | R0010-P02, R0011-P01 | R0010-R0011 | M000193-M000196 | 4 | 719 | 44185 | 87929 | 24757-25482 | yes |
| part_bd | R0011-P02, R0012, R0013-P01 | R0011-R0013 | M000197-M000202 | 6 | 722 | 42921 | 82915 | 25484-26218 | yes |
| part_be | R0013-P02 | R0013 | M000203-M000205 | 3 | 815 | 49706 | 97764 | 26220-27036 | no |
| part_bf | R0014, R0015-P01 | R0014-R0015 | M000206-M000209 | 4 | 841 | 51314 | 103188 | 27042-27891 | yes |
| part_bg | R0015-P02 | R0015 | M000210-M000214 | 5 | 719 | 44669 | 91048 | 27893-28615 | no |
| part_bh | R0016-P01 | R0016 | M000215-M000217 | 3 | 1139 | 55047 | 95110 | 28621-29761 | no |
| part_bi | R0016-P02, R0017, R0018-P01 | R0016-R0018 | M000218-M000248 | 31 | 786 | 48243 | 91590 | 29763-30586 | yes |
| part_bj | R0018-P02 | R0018 | M000249-M000261 | 13 | 1389 | 47563 | 97694 | 30588-31988 | no |
| part_bk | R0018-P03 | R0018 | M000262-M000267 | 6 | 1431 | 43887 | 87246 | 31990-33425 | no |
| part_bl | R0018-P04 | R0018 | M000268-M000282 | 15 | 1862 | 47197 | 89147 | 33427-35302 | no |
| part_bm | R0018-P05 | R0018 | M000283-M000299 | 17 | 1543 | 48036 | 91261 | 35304-36862 | no |
| part_bn | R0018-P06 | R0018 | M000300-M000318 | 19 | 1378 | 44366 | 82810 | 36864-38259 | no |

## R Split Count

| R | Part count | Physical parts |
| --- | ---: | --- |
| R0001 | 2 | part_aa, part_ab |
| R0002 | 4 | part_ab, part_ac, part_ad, part_ae |
| R0003 | 3 | part_af, part_ag, part_ah |
| R0004 | 7 | part_ai, part_aj, part_ak, part_al, part_am, part_an, part_ao |
| R0005 | 6 | part_ap, part_aq, part_ar, part_as, part_at, part_au |
| R0006 | 2 | part_av, part_aw |
| R0007 | 2 | part_ax, part_ay |
| R0008 | 3 | part_az, part_ba, part_bb |
| R0009 | 1 | part_bb |
| R0010 | 2 | part_bb, part_bc |
| R0011 | 2 | part_bc, part_bd |
| R0012 | 1 | part_bd |
| R0013 | 2 | part_bd, part_be |
| R0014 | 1 | part_bf |
| R0015 | 2 | part_bf, part_bg |
| R0016 | 2 | part_bh, part_bi |
| R0017 | 1 | part_bi |
| R0018 | 6 | part_bi, part_bj, part_bk, part_bl, part_bm, part_bn |
