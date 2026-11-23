# Separate WSL browser verification

Use a new directory. Existing viewer, test courses and stash remain untouched. No hosted-agent temporary path is needed.

```bash
git clone --single-branch --branch handoff/option-a-merge-package \
  https://github.com/ThePalmetto/smm-course-viewer.git \
  "$HOME/smm-option-a-handoff"
git clone --single-branch --branch test/option-a-refresh-pr14 \
  https://github.com/ThePalmetto/smm-course-viewer.git \
  "$HOME/smm-option-a-browser-refresh"
python3 "$HOME/smm-option-a-handoff/maintainer-handoff/verify-manifest.py"
python3 "$HOME/smm-option-a-handoff/maintainer-handoff/verify-tree.py" \
  --checkout "$HOME/smm-option-a-browser-refresh"
git -C "$HOME/smm-option-a-browser-refresh" rev-parse HEAD
# 10948310b1b3ba09e6f0cd689b5151ee73f08b8d
git -C "$HOME/smm-option-a-browser-refresh" rev-parse HEAD^{tree}
# ac33cc4c42aeb540a567ac01f31b964339a70994
```

Git clone refuses an existing nonempty destination; choose another new directory rather than deleting files. In a separate terminal:

```bash
python3 -m http.server 8008 --bind 127.0.0.1 \
  --directory "$HOME/smm-option-a-browser-refresh"
```

Port 8008 is an example; choose an unused port if necessary. If a separately verified reference viewer is running on port 8007, compare http://localhost:8007 with http://localhost:8008. Otherwise establish a known reference before comparing. Confirm the reference serves the intended approved version before drawing conclusions. Disable browser cache with DevTools open, hard-reload both, and match zoom/viewer scale. Select the same existing CDT through Browse; do not move, edit or overwrite it.

## Refreshed PR #14 artwork verification

The refreshed tree differs from the original independently tested tree only in the SMB1 and SMB3 black Buzzy Shelmet PNGs. Visually inspect both styles in themes that select the black artwork, checking their off-black color and surrounding sprite transparency. Record this as new visual verification, separate from the original 41,527 automated regression checks.

## Combined-feature checklist

- Tracks/coasters: straight, diagonal and curved geometry, caps, attached/free and both sizes; preserve accepted midpoint placement.
- Pipes/wings: all four directions, normal/enlarged, one/two wings, body and wing center/artwork angle, foreground pipe occlusion; include type-45 and Rocky Wrench with existing WU adjustment.
- Surface/themes/custom bodies: Spiny/Buzzy/Spike Top orientation and colors, empty Shelmets, Wiggler/Angry Wiggler and flower, Shoes/Stilettos and custom artwork fallback.
- Scene layers: goals/scenery and ordinary terrain; Castle lava passes; enlarged cannon mounts; switches and linked normal/P/key doors.
- Unicode titles where existing courses provide coverage.
- Repeated A -> B -> A loads, cold/warm cache; no stale background, duplicate drawing or late scene overwrite.
- Failed atlas: block *localhost:8008/layout/draw/monster/*.png* in DevTools, keep cache disabled, hard-reload and confirm requests fail. Later available terrain should render; unavailable dependent art is safely omitted; supported independent custom artwork should remain. Expected blocked-network messages are distinct from uncaught InvalidStateError/drawImage exceptions.
- Remove all blocks and hard-reload; healthy output should return and match the reference.

Record course, mode/theme, features, sizes/directions, cache/network condition, PASS/FAIL/NOT TESTED, actual differences and JavaScript errors. Mark missing course coverage Not tested. No synthetic surface-wing/Shelmet/Skewer behavior is required. Automated recordings are not pixel-perfect browser evidence.

```text
Option A tree:
Reference HEAD:
Browser/version:
Course | Mode/theme | Features | Cache/network | Result | Differences/errors
Failure blocks removed: yes/no
Overall visual result: PASS / FAIL / INCOMPLETE
```

Stop before edits to existing branches or PRs. This package does not claim the browser checks have already occurred.
