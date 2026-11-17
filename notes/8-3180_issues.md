# 8-3180 (Ingersoll 1114 AWS) - transcription issues

Transcribed 2026-11-16. Schema `lookup-v1.1`. 22 sections, 825 rows. Scan with no text layer: every table read by eye, tesseract used only as a cross-check.

## What this book is
- Ingersoll **1114 AWS** (all wheel steer), edition 5-91-RP-500-227. Engine C34537 "14 HP" (B&S twin; model/type not printed, left blank). Transaxle C34516, 43" deck. No serial table or serial break: matches all serials. Not a bundle. No Noma or Murray name printed.
- Sibling of 8-3170/8-3160 in style and of 8-3270 (1214, not transcribed). Row-by-row match (same ref and part number): vs 8-3160 chassis 49/79, mower suspension 7/77, motion drive 33/79, transaxle 61/72, steering 4/42, pre-painted deck 35/53, electrical 8/38, decals 9/19, customer assembly 0/15; vs 8-3170 chassis 48/79, mower suspension 73/77, decals 10/19, customer assembly 6/15, motion drive and transaxle 0. Front steering, rear steering and engine pages (twin) are new (engine pages 0%).

## Kept as printed + flagged
- Typos corrected (original in each row's flags): electrical 37B "Cylindical", decals 19 "INGERSOIL", engine block 15 "cylidner", carburetor 26 "ASSEMLBY", blower housing 7 "stater".
- **Chassis ref 33 (hood C35085):** qty is an illegible dot on the scan; stored as 1, flagged (confirmed by you 2026-11-16). The index confirms the part at 5/33.
- **Transaxle ref 23:** table prints C34497; the numerical index prints C39947 at 31/23. Table kept, flagged.
- Ref gaps are printed gaps: chassis 58-63, motion drive 47-59, transaxle 16, 19, 24, 63, 72-74. Repeated refs: flywheel 12 and 13, engine block 22 and 26. Ref 0 rows: carburetor (3) and starter (C34284).
- No qty printed: mower suspension 34, steering 39, motion drive 91. UAR on engine block 6, 7, blower housing 9, 10, gasket sets 7, 8. Inch qtys kept (chassis 79 77.5", engine control 28 10").
- Decals refs 3 and 14 print "REFERENCE ONLY" with no part number (qty 1).
- 29 NSS rows (including `*`/`**` part cells with footnotes: steering 1, 35, 39; motion drive 88, 91; final deck 1). Footnote marks on C34516*, C34537*, C35036** and C35351** removed from partNo, kept in partNoAsPrinted.
- Alphabetical index misprint: lists "Engine and Control Assembly 25"; the table is on printed p19.

## Validation
- **Numerical index (printed pp46-49):** all 794 expected part entries located in the printed index; every other difference was OCR noise checked against the table. One true conflict (transaxle ref 23, above).
- Quantities, part-number forms and ref continuity: see the `validation` block.

## Model and attachments
- **1114 AWS** full model: hydrostatic (confirmed by you 2026-11-16), steering "all wheel steer", Noma alias `source: user`, engine C34537, all serials. Attachment: 43" deck (`source: book`, side discharge per you 2026-11-16; TractorData lists none). **1214** stub (`ref: true`, edition in 8-3270); the 1214's file should record `successorOf` 1114 AWS later.
- B&S model/type left blank (confirmed by you 2026-11-16, plan issue 29).

## Commit (PowerShell)
```powershell
cd "C:\Users\Admin\Documents\Website\ingersoll-lookup-data"
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\lookup json\8-3180_lookup.json" data\
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\issues\8-3180_issues.md" notes\
git add data notes
git commit -m "Add 8-3180 lookup data"
git push
```
