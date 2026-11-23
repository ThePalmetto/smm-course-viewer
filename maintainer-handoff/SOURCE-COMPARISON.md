# Source comparison

The actual independent Option A replay is e14a6c1d5956b15cbfdaf00bd4bd1713a5dfaae9, tree c75546d5456ba655c7a1afa59ddc31dc80186347. It matches every tracked byte of the previously tested corrected rehearsal and coordinated proposal.

## Refreshed integration

The current refreshed Option A tree is
`ac33cc4c42aeb540a567ac01f31b964339a70994`,
published at `test/option-a-refresh-pr14`.

A direct Git tree comparison against the original Option A tree
confirmed exactly two modified tracked files: the SMB1 and SMB3
black Buzzy Shelmet PNGs. All other tracked files are unchanged.

The original comparison with `compare/enhanced` below is retained
as historical evidence. Its statement that all PNGs matched applies
only to the original Option A tree, not to the refreshed integration.
No new complete comparison against `compare/enhanced` or full
rendering-parity suite is claimed for the refreshed artwork.

## Original source comparison (historical baseline)

Compared with approved integration 138004b530435efe423d9ed7065093101645963f, both have 233 tracked files: 227 identical, six explained differences, no missing/extra files, and all 173 PNGs and two bundled CDT fixtures identical. Hash inventories are final-file-sha256.json and published-integration-file-sha256.json.

| File | Difference |
|---|---|
| .gitignore | Additional integration Windows download/editor/backup/sprite-grid patterns; no runtime effect. |
| lib/SmmCourseViewer.js | Comments and spacing; parser executable tokens match, including Unicode, fractional signed depth and track coordinates. |
| lib/MonsterObject.js | Line endings; direction decoding matches. |
| draw/BlockDraw.js | Bridge-definition formatting; executable tokens match. |
| draw/MonsterDraw.js | Line endings and retained upstream type-32 diagnostic logging that integration removed; rendering definitions match, including pipe-aware Wiggler. |
| draw/Draw.js | Equivalent image registration/dispatch organization, disjoint branch ordering, selection branches and formatting; omitted unused integration-only _redrawCourse/_drawRailEndpointMarker helpers and no-op empty-path strokes. External invocation of omitted helper APIs is outside the supported viewer comparison. |

Draw.js Git blobs: final Option A 833d5e1a7ef6ceef314a2c3ae018502a1f58fc36; published integration d2060b0652e6d63a24b1317e5c090588cafa4563. Different source layout explains the blob difference.

All 17,176 healthy recordings match; repaired implementations also match 1,152 primary mixed scenes and 576 lifecycle recordings. This is command-level parity for the exercised matrix, not pixel-perfect browser verification. No wholesale source replacement was used to force byte equality.
