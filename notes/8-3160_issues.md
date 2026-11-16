# 8-3160 (Ingersoll Compact Tractor 1112, 5-91) - issues list

Transcribed 2026-11-16. 689 rows, 18 sections, all applying to model 1112, all serials. Schema `lookup-v1.1`.

## Needs a look (decision or confirmation)
1. **1112G alias** - the book prints only "1112" (cover, every page header, index) and has no ID table. `1112G` is stored as an inferred alias (plan decision 32). The 1112H is a stub (`seeAlso`, edition in 8-3170, not yet transcribed).
2. **Deck attachment** - the 39" SD deck pages are in this book, so the 1112 gets one `mid-mount deck` attachment (size 39", model 39SD, `source: book`, `verified: true`). "Mid-mount" is inferred from the lift/suspension pages. The registry lists no TractorData attachments for the 1112, so none were added. Tell me if you want a TractorData lookup.
3. **Probable misprints kept as printed** (each is flagged on its row): decal ref 7 prints **C36472** (index prints C35472); pre-painted deck ref 21 prints **C35798** for the same nut that is C34798 on every other page (index also prints C35798); carburetor refs 5 and 6 print qty **5** and **6** (spring and pin; zoom-checked); engine block ref 29 intake valve retainer qty 2.

## Index vs table (table kept, flagged)
- Engine block ref 35: table C33377 (zoom-checked), index prints **C33370** at 31/35.
- Decal ref 7: table C36472, index C35472.
- Ref 0 rows (C27255, C30422, C30424, C31978) are indexed with no ref number.
- Hardware 11-312 and 41-24 are printed 011- 312 and 041- 24 in the index (stored as in the table).
- Everything else (about 670 entries) matches in both directions.

## Kept as printed
- **Ref gaps not printed:** chassis 54-63, motion drive 45-59, transaxle 16, 19, 24, 63, flywheel/stator 2 and 6, carburetor 26, 27, 43.
- **No qty printed:** motion drive 89, 90, 91 (valve stem, rim, tire); transaxle 72 and 77; decal 3. Decal ref 3 is "REFERENCE ONLY" with no part number.
- **Inch quantities:** trim strip 77.5", gas line 6" (qtyNum null).
- **Typos:** "UIDE, BELT" (motion drive 25), "INGERSOIL" (decal 14), "1//4-20" (engine/control 21), "1/4-10X:75" (22).
- **Same part number, different descriptions:** C35150 is "ROD,ACTUATOR-SHORT" (mower suspension 54) and "BRACKET,SHIFT 5SP SF FEN HT" (motion drive 39); the index lists both.
- **Parts named only in notes (no row):** 113-120, 192-20 (engine block 16), 163-18, 192-18 (engine block 34), 113-102, 92-5 (flywheel 20, starter 14). `92-5` may be a truncated code, as in A1226.
- **NSS rows (11):** `*` and `**` part cells (motion drive 88/91, steering 1/31/35, final deck 1) with their footnotes, battery acid pack (customer 3), and four "use ..." screw rows (engine block 16/34, flywheel 20, starter 14).
- **Duplicate refs:** engine block 9, 18, 19, 21 (size or thickness options, flagged `alternative`); carburetor ref 0 is three different parts; electrical 35A/35B (spade or cylindrical fuse, footnote kept).
- **Indented sub-parts (23 rows)** flag the row they sit under; no new field.
- Engine make/spec: "12 HP B&S I/C" only; the Briggs model/type is not printed (left blank, issue 29 style).
- Table styles: tractor pages (pp5-29) are Murray-style listings with coded descriptions; engine pages (pp31-39) are typewriter-style with mostly C numbers and some BR numbers. No serial information anywhere, so the finder goes straight to the model.
