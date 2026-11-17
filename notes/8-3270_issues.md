# 8-3270 (Ingersoll 1214) - issues list

Transcribed 2026-11-17. File: `8-3270_lookup.json` (schema `lookup-v1.1`). 25 sections, 804 rows, all appliesTo 1214, no serial constraints (the book has no ID table, serial break or S/N note anywhere, so the 1214 matches all serials).

## Needs a decision
Nothing open. All index-versus-table items are decided (see below).

## Decided items applied
- Second round of index answers (user, 2026-11-17): fender p7 ref 9 is now C34808 (index; table printed C34803) and pre-painted deck p21 ref 4 is now 131-176 (index; table printed 113-176); governor p39 ref 27 stays C40890 (table; index prints C40980); flywheel p31 ref 21 .020" piston stays C34587 (table; the index prints C34586 twice). For the two changed rows `partNo` differs from `partNoAsPrinted`, which keeps the table print, and the row flags say so.
- Steering ref 14: the table prints no ref 14, the index lists C35396 at 11/14, and the user says it is a flat washer, qty 1. A row was added (`WASHER - flat`, description and qty from the user, flagged as not printed in the book), so steering now has 33 numbered refs with only ref 27 missing.
- Table row C35264 (motion drive shift ref 9) has no index entry; table kept.
- Driveline: gear drive (user, 2026-11-17), stored as `driveType` "gear".
- Deck discharge: side discharge (user, 2026-11-17); which side is not known, so it is in the deck's note and no side is recorded.
- Index conflicts decided 2026-11-17: chassis p5 ref 19 stays C31365 and ref 20 stays C31597 (table; the index prints C31395 and C31397). Fender p7 ref 18 is now C35386, flywheel p31 ref 2 is now C34618 and ref 4 is now C34651 (index values). For those three the table print (C35119, C40888, C40889) stays in `partNoAsPrinted` and the row flags, so `partNo` and `partNoAsPrinted` differ on them.
- Aliases "1214 AWS", "all wheel steer" and "Noma 1214 AWS" (source user); `successorOf` 1114 AWS (inferred); the 1114 AWS appears as a stub (its full record lives in 8-3180).
- Engine C42812: the book prints "14 hp Briggs & Stratton model 261777 type 0159", so it is in the engine's `appliesNote` (the schema has no model/type fields).
- Steering "all wheel steer" (the book prints Rear Wheel Steering Assembly, p13).
- 43" mid-mount deck (book, 8-3270, verified). No weight box or wheel weights are printed in this book.
- Typos corrected in the stored text, original in the flags: air cleaner ref 7 MAINIFOLD (MANIFOLD) and gasket kit ref 4 "fillter" (filter).

## Structure
- The book's table of contents lists 24 tables on pp5-43; the paint and oil tables (7 and 3 rows) are on the cover page and are stored as `paint_oil` (page "cover", refs restart at 1 for oil).
- Motion drive is two sections (shift p15, clutch p17), as printed. No customer assembly section in this book.
- Printed ref gaps: steering 27; transaxle 16, 19, 24, 63, 72-74. Repeated refs kept: steering 34 and 35, electrical 9, flywheel 18/21/22, cylinder 36. Ref 53A follows 53.
- 5 unnumbered rows stored with ref 0 (carburetor and starter header rows, three steering sub-rows under ref 31); 126 indented description rows carry the parent-ref flag; 62 NSS rows (`*`/`**` cells on steering and clutch carry the footnote text in their flags); 13 UAR; clutch ref 27 (TIRE **) has no qty; fender ref 16 trim strip qty 77.5 kept as printed.
- Footnote "*See engine section for repairs" on engine control ref 1 (C42812*).

## Diff against 8-3180 (same ref and part number)
- Transaxle: 72 of 72 rows identical (only the assembly number differs, C40667 here vs C34516).
- Rear steering: 37 of 49 rows identical. The 12 differences are hardware: this book uses hardware codes (113-110, 195-521, 131-176, 195-104, 129-289, 129-163, 192-21) where 8-3180 uses C numbers for the same sizes, plus C28226 (washer, ref 25) in place of C35214. 35 of 36 Case part numbers here also appear in 8-3180's rear steering.
- Final deck: 26 of 45 identical; refs 39-45 are new (chute, pivot rod, push nut, torsion spring, deck wheels, shoulder bolt, lock nut). Same hardware-code swap as above.
- Pre-painted deck: deck C35293 and blades C35315 match; the other rows are renumbered (25 more shared by part number).
- Carburetor 15 of 42, decals 7 of 18; the engine pages are otherwise different (single vs twin engine).

## Numerical index (printed pp44-47) cross-check
Full by-eye pass: all four index pages read from 200-dpi crops and typed out independently of the transcription (731 entries), then compared with the transcription in both directions on part number, page and ref. Every mismatch was re-checked at full zoom on both the index and the table and then decided by you (see above). After the changes the only differences left are the ones where the table value was kept: chassis 5/19 and 5/20, governor 27 and flywheel 21 (the index prints C34586 twice), plus the table row C35264 (15/9) that the index omits. The paint and oil parts (cover page) are not in the index.

## Commit commands (PowerShell)
Save `8-3270_lookup.json` to `C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\lookup json\` and this file (as `8-3270_issues.md`) to `...\Lookup Data\issues\`, then:

```powershell
cd "C:\Users\Admin\Documents\Website\ingersoll-lookup-data"
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\lookup json\8-3270_lookup.json" data\
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\issues\8-3270_issues.md" notes\
git add data notes
git commit -m "Add 8-3270 lookup data"
git push
```

(If the files were saved straight into the repo's `data\` and `notes\` folders, the two `Copy-Item` lines fail with "Cannot find path"; that is harmless and the `git` lines still commit them.)
