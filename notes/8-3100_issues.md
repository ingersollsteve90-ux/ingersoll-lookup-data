# 8-3100 issues (lookup-only transcription, 2026-11-10)

Ingersoll 112B / 114B / 116B, edition 9-90 (9-90-RP-300-402). Scan, no text layer, 33 PDF pages. 37 sections, 843 rows. Not a bundle. Sibling books: 8-2992 (112/114/116, same engines) and 8-3021 (1012/1014/1016, relabeled as 112B/114B/116B; not transcribed yet, so compare transmissions there).

## Needs a decision
1. **114B break.** Seat/fenders and both electrical headings print 14105556. The PTO footnote, the after-PIN harness rows (C31443 / C31036) and the wiring-diagram note on p54 print **14105564**. The registry keeps 14105556 (decision #8). Row variants keep each page's printed number, so the PTO bracket switches at 14105564. The harness C31036 is stored as 114B 14105556 to 14105563. The survey's "14105664" was an OCR misread: at full resolution the page prints 14105564.
2. **Travel control ref 19.** The table skips 19, but the numerical index lists 192- 19 at 47/19. I added it as an index-only row (no description or qty printed; flagged). Keep it or drop it?
3. **Headlight footnote** (p57, C30942 reflector): "*Will require 2 before PIN: 112B-14103738, 114B-14105555, 116B-14116700". It doesn't say what changes, so no serial variant was created. The note is stored on the row and the section.

## Index vs table (table kept, row flagged)
- p13 ref 13: table C25742, index C25745.
- p21 ref 19: table C27270, index C27370 (the neighbouring parts are C27368/C27369, so the index may be the right one).
- p27 ref 1: table C29314, index C29304.
- p35 ref 24: table 132-311 (refs 2/3 also say "use … 132-311"), index 123- 311.
- Index prints G25746 for C25746 (5/32).
- The index omits the whole **Headlight and Rear Reflector** table (p57). Paint and oil are not indexed either.

## Kept as printed, flagged
- Refs not printed: carburetor 114B/116B ref 9; blower housing refs 4 and 20; hood ref 23; electrical hardware ref 13.
- No qty printed: p7 gasket kit C27335 and p13 ref 7 (BR 230896, float hinge pin).
- Hardware codes with doubtful prefixes (same pattern as A1226): `11- 312`, `13- 624`, `13- 628`, `83- 55`. The index prints them with a leading zero (011-, 013-, 083-).
- p13 ref 34 prints "C- 30435" (stored C30435). Typo "PISTON ASSEMLBY" (p5 ref 18). Brake ref 12: 195-521 is described as 1/4" here but 5/16" everywhere else.
- REQ'D printed about half a row low on steering gear, transaxle shifter/counter shaft, differential and drive belts. Quantities were mapped in sequence (counts match) and flagged as inferred qty (105 rows).
- 30 NSS rows (substitute numbers kept in desc/flags), including the 6 hood decals ("original decals are not available").

## Modelling notes
- Model splits inside shared sections use basis `model` (from "(112B)" / "(114B, 116B)" in the descriptions). The seat/fenders and electrical before/after pages, and the PTO bracket */**, use per-model serial variants with a `model` field (8-2700 format). The differential uses basis `transaxle` (826 † / 843 ††).
- No attachments: the book has no chart and TractorData has no 112B/114B/116B pages.
- Paint and oil (unnumbered page facing p1) is transcribed as one section. The p3 "indented descriptions" example table (C55159 rear steering cylinder) comes from another book and was not transcribed.
