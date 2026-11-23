# Final technical status

## November 2026 PR #14 artwork refresh

PR #14 now includes corrected black Buzzy Shelmet PNGs for SMB1 and SMB3. The refreshed integration differs from the original verified application in exactly those two files.

A new independent replay completed all 17 PR merges, applied the documented conflict resolutions, and verified all 19 tree checkpoints. A separate portable replay using published GitHub references reproduced the exact current application tree.

Both corrected images passed PNG structure and CRC checks. JavaScript syntax checks passed, and no unresolved merge conflict markers were found.

The original 41,527 automated checks remain historical evidence for the original application tree. The complete regression suite and refreshed browser visual comparison have not been rerun against the corrected artwork.

## Approved references

| Reference | Commit |
|---|---|
| Upstream master | f807f0247bac4c553288700bf7c08dd8502eead0 |
| Fork master | 848a7f4584fd69405ca745ac1c97a0f3ced175fa |
| Published compare/enhanced | 138004b530435efe423d9ed7065093101645963f |
| Original independent Option A replay / testing branch | e14a6c1d5956b15cbfdaf00bd4bd1713a5dfaae9 |
| Refreshed Option A verification branch (`test/option-a-refresh-pr14`) | 10948310b1b3ba09e6f0cd689b5151ee73f08b8d |
| Updated PR #14 source | 18904496cf9278a312df35f08bc495b8a8cc723f |
| Original rehearsal compatibility commit | 392935f7f7ada15abb304058105f55d495580915 |

**Current Option A application tree:** ac33cc4c42aeb540a567ac01f31b964339a70994.

**Original independently tested tree:** c75546d5456ba655c7a1afa59ddc31dc80186347.

The actual independent replay started from pinned upstream and performed all 17 merges, not from the coordinated branch. Three merges were clean and fourteen required the supplied exact patches. Every intermediate tree matched. The compatibility layer and 19-line safety layer then produced the final tree.

The result contains all 17 pinned PR tips as ancestors, all 233 approved files and 173 PNGs, with no dirty/untracked files or conflict markers. Type-45 body calibration is supplied once by #21; compatibility supplies only the additional combined behavior; final artwork guards are supplied once by the last patch.

Actual fresh regression results on this independent replay: 35,559 primary + 5,392 artwork + 576 lifecycle = 41,527 passed, zero failed/skipped. All 192 previously failing artwork scenes recovered. The separate publication of this handoff does not represent a new full-suite run or browser sign-off.

Option A is technically ready with documented conflict resolutions on the pinned baseline. Complete the separate browser comparison before final visual sign-off. All 17 PRs were verified open at pinned tips; no claim is made about review approval, CI or live GitHub mergeability.

Retained limitations: upstream Player/type-69 xY versus yT typo (192 separate expected-failure diagnostics); unresolved synthetic winged empty-Shelmet/Skewer combinations; accepted skull-coaster curved midpoint behavior. No new surface-wing dispatch or speculative calibration was introduced.

Original rehearsal evidence, source patches, offline bundle and logs are preserved separately and unchanged. This is a compact copy-based handoff, not a replacement of the historical baseline evidence.
