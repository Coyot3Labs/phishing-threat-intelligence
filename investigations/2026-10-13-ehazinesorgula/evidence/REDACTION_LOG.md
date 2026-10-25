# Screenshot redaction and publication log

**Review date:** 25 October 2026 · **Scope:** 27 PNG publication copies linked to evidence IDs E01–E35. Raw originals, HAR and source-text files are not uploaded in this release.

## Method

1. Read each original locally and check its SHA-256 against the original evidence inventory.
2. Crop irrelevant or sensitive areas and cover remaining protected pixels with solid RGB black. All coordinates in the manifest refer to the original image and use half-open boxes: `[left, top, right, bottom]`.
3. Flatten to an opaque RGB raster and re-encode as PNG without original metadata. Retained pixels outside declared masks are unchanged; there is no resize, blur, generated text or generative reconstruction. E12 is a reviewed re-encoding without crop or pixel masks.
4. Verify every masked rectangle is fully black, every other retained pixel matches the source, and all original file hashes remain unchanged.
5. Inspect each rendered copy visually, including transparent backgrounds and mask edges. Check captions against what is actually retained. E20, E22 and E31 received additional margin masks during review.

Secrets, national-ID-shaped inputs, person/contact/bank/payment values, analyst user/host/path context and live network-address strings are omitted. Defanged network context is supplied in text; it is not inserted into the screenshot as fabricated output. Static code field names and source filenames are not secret values.

## Coverage and limits

All 27 source PNGs have a publication copy. Some copies retain only limited status or code excerpts. E17 does not identify its uncertain query name; E21 shows three example 403 statuses only. Neither image establishes shutdown, file existence or origin infrastructure. Unmasked text in retained code/response excerpts remains in its original language.

The main report contains eight selected figures. [INDEX.md](INDEX.md) contains all 27 images and per-file edits/limits. [DERIVATIVES.json](DERIVATIVES.json) contains original and publication SHA-256 values, byte sizes, dimensions, exact crop/mask boxes and verification flags. Original hashes also remain unchanged in [evidence_index.csv](../evidence_index.csv). The root [SHA256SUMS.txt](../SHA256SUMS.txt) covers all publication files except itself.

These are publication derivatives of supplied historical artifacts. Redaction does not establish original acquisition authenticity, independent domain provenance, successful identity lookup, completed payment, current availability or a common operator.

| Evidence | Transform | Published dimensions | Opaque masks |
|---|---|---|---|
| E01 | Cropped + masked | 965 × 362 | 5 |
| E02 | Masked (full frame) | 982 × 701 | 11 |
| E04 | Cropped + masked | 980 × 705 | 1 |
| E05 | Cropped + masked | 785 × 612 | 1 |
| E10 | Cropped + masked | 1022 × 138 | 6 |
| E11 | Cropped + masked | 539 × 378 | 10 |
| E12 | Re-encoded only | 673 × 421 | 0 |
| E13 | Cropped | 453 × 115 | 0 |
| E14 | Cropped + masked | 349 × 469 | 1 |
| E15 | Cropped | 575 × 187 | 0 |
| E16 | Cropped + masked | 299 × 256 | 3 |
| E17 | Cropped + masked | 490 × 257 | 5 |
| E18 | Masked (full frame) | 289 × 65 | 2 |
| E19 | Masked (full frame) | 971 × 58 | 4 |
| E20 | Cropped + masked | 950 × 49 | 4 |
| E21 | Cropped | 111 × 49 | 0 |
| E22 | Cropped + masked | 772 × 696 | 19 |
| E23 | Cropped + masked | 885 × 505 | 13 |
| E24 | Masked (full frame) | 677 × 633 | 8 |
| E25 | Cropped + masked | 974 × 422 | 3 |
| E26 | Cropped + masked | 949 × 240 | 3 |
| E27 | Cropped | 638 × 130 | 0 |
| E28 | Cropped + masked | 735 × 534 | 6 |
| E29 | Cropped + masked | 727 × 520 | 16 |
| E31 | Cropped + masked | 964 × 62 | 6 |
| E33 | Cropped | 806 × 51 | 0 |
| E35 | Cropped | 968 × 67 | 0 |
