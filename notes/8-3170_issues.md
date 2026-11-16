# 8-3170 (Ingersoll 1112H) - transcription issues

Transcribed 2026-11-16. Schema `lookup-v1.1`. 19 sections, 720 rows. Scan with no text layer: every table read by eye, tesseract used only as a cross-check.

## What this book is
- Ingersoll **1112H** (hydrostatic), page headers "39" Lawn Tractor Model 1112H". Edition 5-91-RP-500-212, footers "April 1991". Engine C34536 "12 HP B&S I/C" (B&S model/type not printed). No serial table or serial break anywhere: matches all serials.
- Sibling of 8-3160 (1112): the chassis, steering, deck, electrical and all engine pages are largely the same part numbers; **motion drive and transaxle (Agri-Fab hydro) and the customer assembly differ, and the Hydrostatic Pump (p31) is new**. Row-by-row match with 8-3160 (same ref and part number): engine block, flywheel, counterweight, carburetor, governor, oil filler, starter all 100%; engine control 26/26; chassis 71/75; steering 37/38; pre-painted deck 50/52; final deck 40/42; electrical 35/36; mower suspension is the same parts with refs shifted (one extra row at ref 8); decals 9/20; customer assembly 0/8 (4 of 8 part numbers shared); motion drive 0/105; transaxle 0/64.
- Not a bundle.

## Decided by you (2026-11-16, applied in the file)
1. **Motion drive ref 27, screw (10-32X .25 ALSETCUPT, qty 2):** the table value **C35421** is kept. The numerical index prints C25421 at 13/27 (no C35421 line); the row's flag records this and your confirmation.
2. **Motion drive ref 42, C35006 (qty 1):** description corrected from "SCREW, 5/16-18 REGHEXCTRLK" to **"SCREW, 5/16-18X .75 HHC"**, the description used for C35006 elsewhere in this book and in 8-3160. The original text is in the row's flags.
3. **Hydrostatic pump (p31):** refs 1-9 are parts of the **ref 0 pump C35405**; their flag now says so. Refs 11-15 stay under ref 10 (bypass valve kit C35547). The table has no qty column, so the 17 rows have no qty (flagged).

## Kept as printed + flagged
- Typos corrected per your standing rule (original in each row's flags): engine control ref 21 "1//4-20X.50" to 1/4-20X.50; motion drive ref 42 description (item 2 above). No other description typos found. Electrical footnote prints "assymbly" (sic); stored as "assembly" in the footnote flag only.
- Motion drive ref 55 prints C34861 as "WASHER, REGSPLTLK .393-16X3.00" (the same part at ref 12 is .393X.68X.10); kept, flagged.
- Hardware codes **11-312** (governor ref 6) and **41-24** (carburetor ref 12) are stored as printed; the index prints them zero-padded (011- 312, 041- 24), as in 8-3160.
- Ref gaps are printed gaps: chassis 54-63, motion drive 66-69, transaxle 11, 50 and 62, flywheel 2 and 6, carburetor 26, 27 and 43. Repeated refs: engine block 9, 18, 19, 21 (size/thickness options), transaxle 28 and 49 (washer options, qty UAR on three rows), ref 0 on transaxle, pump, engine block and carburetor. Seven ref-0 parts (C34534, C35405, C35546, C30422, C27255, C30424, C31978) are in the index with no ref number.
- No qty printed: pump (all rows) and motion drive ref 104 (tire). Inch qtys kept: chassis ref 79 "77.5"" and engine control ref 17 "13"". Decals refs 3 and 14 print "REFERENCE ONLY" with no part number (qty 1).
- 27 NSS rows (6 are `*`/`**` part cells with footnotes: steering 1, 31, 35; motion drive 101, 104; final deck 1). Footnote marks on C34534**, C35405*, C34536*, **C35036 and **C35351 removed from `partNo`, kept in `partNoAsPrinted`.

## Validation
- **Numerical index (printed pp42-45, 691 lines):** compared line by line against an expected index rendered from the transcription, both directions, every mismatch checked by eye. Exactly 691 expected entries and 691 printed lines. All match except: C35421/C25421 (decided item 1) and the two zero-padded hardware codes above. Mower suspension ref 62 is C34156 in both table and index (8-3160 has C35156).
- Quantities, part-number forms and ref continuity: see the `validation` block in the JSON.

## Model and attachments
- Model **1112H** is now a full model (the stub in 8-3160 should be replaced by this): hydrostatic, engine C34536, all serials, `seeAlso` 1112 (inferred), no Noma alias. Attachments as for the 1112: 39" SD mid-mount deck (`source: book`, side discharge per you; pre-painted deck p19, final deck p21) and the unsized blade from TractorData (`verified: false`). The 1112 appears as a stub (edition lives in 8-3160).

## Commit (PowerShell)
```powershell
cd "C:\Users\Admin\Documents\Website\ingersoll-lookup-data"
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\lookup json\8-3170_lookup.json" data\
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\issues\8-3170_issues.md" notes\
git add data notes
git commit -m "Add 8-3170 lookup data"
git push
```
