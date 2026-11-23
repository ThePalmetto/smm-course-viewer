# Validation evidence and scope

## Original independent Option A verification (historical baseline)

A new disposable checkout started at upstream f807f0247bac4c553288700bf7c08dd8502eead0. All 17 actual merges were performed in the documented order. Three were clean; fourteen had exactly the recorded conflicts. Every intermediate tree matched. Compatibility and the final safety patch then yielded c75546d5456ba655c7a1afa59ddc31dc80186347.

| Actual executed collection | Passed | Failed | Skipped |
|---|---:|---:|---:|
| Primary regressions | 35,559 | 0 | 0 |
| Supplemental artwork/custom-renderer checks | 5,392 | 0 | 0 |
| Loading lifecycle | 576 | 0 | 0 |
| Total | 41,527 | 0 | 0 |

All process statuses were zero; no cancellations. All 192 formerly failing artwork-loading mixed scenes recovered. Healthy comparisons: 3,160 pipe/wing + 13,056 all-object + 960 mixed = 17,176 unchanged. Repaired integration parity additionally covers all 1,152 primary mixed scenes and 576 lifecycle recordings.

Primary coverage includes Groups A/B/C/D0/D1/D2, final pipe-wing calibration, all-object comparisons, combined scenes, Unicode/parser, goals, cannons, tracks, coasters, lava, depth and rotation. Historical standalone controls remain part of the matrix; not every case is a separate assertion on every current branch.

Supplemental checks cover pending/failed/missing/successful atlases, actual supplied-theme identity, later ready invocations and independent custom artwork. Lifecycle checks cover cached failure, background-first atlas failure and simultaneous background/atlas failure. Later terrain draws, canvas state balances, and duplicate callbacks do not redraw scenes.

Nine JavaScript syntax checks, the 115-object parser smoke test, source/asset hashes, clean tree, all PR ancestors and diff checks also passed on the replayed checkout. No production or test expectations changed during that independent verification.

## Manual browser visual acceptance

**Overall manual browser visual acceptance: PASS.**

I visually inspected the complete collection of previously compiled SMM Course Viewer test courses in the independently merged Option A viewer. I compared the rendering with that of my previously approved enhanced viewer.

I observed no differences. All inspected rendering features, object positions, rotations, artwork and layering appeared correct.

Tested Option A reference: `test/option-a-final-verification@e14a6c1d5956b15cbfdaf00bd4bd1713a5dfaae9`, tree `c75546d5456ba655c7a1afa59ddc31dc80186347`. Comparison reference: `compare/enhanced@138004b530435efe423d9ed7065093101645963f`.

This records my manual acceptance, not automated verification. It does not establish exhaustive coverage of every possible course, pixel-perfect automated comparison, or completed failure-injection browser testing.

## Refreshed PR #14 integration verification

The refreshed verification branch is
`test/option-a-refresh-pr14`, commit
`10948310b1b3ba09e6f0cd689b5151ee73f08b8d`,
tree `ac33cc4c42aeb540a567ac01f31b964339a70994`.

The updated PR #14 source is
`18904496cf9278a312df35f08bc495b8a8cc723f`.
The refreshed application differs from the original independently tested
tree in exactly two files:

- `layout/draw/custom/smb1/buzzy-shelmet-black.png`
- `layout/draw/custom/smb3/buzzy-shelmet-black.png`

A complete independent 17-PR merge rehearsal passed all 19 tree
checkpoints, including compatibility and artwork safety. A separate
portable online replay fetched the published GitHub references and
reproduced the exact refreshed final tree without borrowing local
Git objects. Both corrected PNGs passed structural and CRC checks.
JavaScript syntax checks and conflict-marker checks also passed.

The original 41,527 automated checks and rendering-parity recordings
were performed against the original application tree, not the refreshed
one. The complete regression suite and refreshed browser visual
comparison have not been rerun.

## Publication/package checks

The testing branch retains the exact replay commit and source tree. The publication check verifies ancestry, tree/file/asset hashes, guard patch identity, syntax/parser checks and clean state. These publication checks are separate from my manual browser acceptance above. The automated regression suites were not rerun during this documentation update.

The compact package retains the documented conflict resolutions, updated intermediate tree pins and small result summaries. The PR #14 resolution patch differs from the original only in the updated Git conflict-marker commit SHA. Full harness fixtures and raw logs remain in preserved original evidence rather than this Git documentation branch. They are required for a new full 41,527-case rerun. Node's existing test/test.js remains available in the application checkout.

The refreshed portable online and offline replay scripts have both been executed successfully. Each independently reconstructed all 17 PR merges, applied the documented compatibility and safety patches, and reproduced the exact refreshed application tree `ac33cc4c42aeb540a567ac01f31b964339a70994`. The offline result additionally passed verification of all 233 tracked file hashes and all 17 PR ancestors. These replay checks do not constitute a new 41,527-case regression run or browser visual sign-off.

After replay or cloning the browser branch:

```bash
python3 maintainer-handoff/verify-tree.py --checkout /absolute/path/to/new/application
# In the application checkout:
node --check draw/Draw.js
node test/test.js
git diff --check HEAD^ HEAD
git status --porcelain
```

## Test adapters and retained limitations

The old broken-atlas baseline was retained as a reproduction control. Recovery assertions now require scene completion, no invalid drawing, later terrain, balanced state and no duplicate render instead of matching the baseline exception. A historical healthy-geometry helper was corrected to mark its intended healthy images complete; its geometry assertions were unchanged, and explicit pending/failed tests remain. Those adapter changes preceded the independent run and are not new publication changes.

Player/type-69 xY versus yT remains a pre-existing issue with 192 separate expected-failure diagnostics; those are not hidden primary failures or skipped cases. Synthetic winged empty-Shelmet/Skewer combinations remain unresolved. Accepted coaster midpoint behavior is unchanged. Public metadata does not establish review approval, CI or branch protection. My manual acceptance of healthy browser rendering is recorded above; failure-injection browser testing is not reported complete.
