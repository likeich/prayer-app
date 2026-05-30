# LXX USFM Changelog

Notes on local edits to the bundled Rahlfs LXX USFM set. Anything not
listed here matches the upstream source byte-for-byte.

## 2026-04-21

- **`32-OBAgrclxx.usfm`:** Added missing `\v 11` and `\v 17` markers.
  Upstream had verses 11 and 17 folded inline into verses 10 and 16 as
  continuation text (just the digit preceded by U+00A0 NBSP, no `\v`).
  Interlinear extraction saw verses 10+11 and 16+17 as single merged
  verses, producing oversized cell arrays and missing refs. Split into
  their own lines.

## 2026-04-20

- **Renamed `58-2ESgrclxx.usfm` → `16-EZRgrclxx.usfm`.** The file's
  content is the Greek of Ezra (Esdras B, 10 chapters), not the
  apocalyptic 2 Esdras / 4 Ezra that USFM code `2ES` conventionally
  denotes. The old filename + `\id 2ES` caused Ezra lookups by the
  canonical `EZR` bookId to miss in the LXX, and caused the same
  `2ES` bookId to point to two different books across translations
  (LXX Ezra vs. KJV/WEB 4 Ezra).
  - `\id 2ES` → `\id EZR`
  - `\h` / `\toc1` / `\toc2` / `\toc3` / `\mt1`: `ΕΣΔΡΑΣ Β` → `ΕΣΔΡΑΣ`

## Known gaps vs. the Orthodox OT canon

Books absent from this directory (present in the WEB/KJV sets):

- `55-MAN` — Prayer of Manasseh
- `56-PS2` — Psalm 151 as a standalone book. Psalm 151 **is** included
  inside `20-PSAgrclxx.usfm` as chapter 151; `OriginalLanguageRepository`
  translates `PS2` bookId lookups to `(PSA, 151)` at the LXX boundary.
- `59-4MA` — 4 Maccabees

The file `58-2ES` is intentionally not present after the rename above.
If a real 2 Esdras (4 Ezra) Greek source is ever added, it should
occupy that slot again.
