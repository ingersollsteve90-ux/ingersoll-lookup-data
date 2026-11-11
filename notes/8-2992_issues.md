# 8-2992 issues list (lookup-only transcription, 2026-11-11)

Catalog: Ingersoll Model 108, 111, 112, 114 and 116 Compact Tractors, Parts Catalog 8-2992 (6-96-RP-300-286, pages dated April 1996, replaces 8-2991).
File: `8-2992_lookup.json` (schema `lookup-v1.1`), 28 sections, 554 rows.
Method: scan with no text layer. Every table page read by eye (2 pages per image at 0.7x, 11 images, plus full-resolution zooms). Numerical index (pp46-48, 531 entries) checked row by row in both directions.

## Needs your decision

1. **30279 and 30260 (electrical, page 37 refs 9 and 12).** The table prints these two without the "C"; the numerical index prints C30279 and C30260. Stored as `C30279` / `C30260` with the printed form kept in `partNoAsPrinted` and a flag. Say if you want them stored bare instead.
2. **112 on the belts page (page 25).** The * / ** serial list names 108, 111, 114 and 116 only. Ref 1 says "(112 - all)" on the ** belt, so I tagged the ** rows of refs 15 (C30103 guide kit) and 20 (C33208 pulley) as 112, all serials, with `inferred: true`. Confirm or tell me the 112 uses the * parts.
3. **108 and 111 on the PTO support bracket (page 9 ref 45).** The footnote gives breaks for 112, 114 and 116 only. Nothing is stored for 108 and 111 on either bracket (C31009 * / C31437 **); the rows are flagged. Tell me which bracket they take if you know.
4. **Rear reflector footnote (page 39 ref 7).** "* will require 2 before S/N: 108 - all, 111 - all, 112 - 14102824, 114 - 14104697, 116 - 14106421". The table already prints qty 2 and the note does not say what later tractors need. Kept as a note with no variant (same handling as the 8-3100 headlight footnote).
5. **Engine mount kit overlap.** The kit is printed "112 - Use S/N 14102824 to 14122270" and Engine Mounts prints "Use S/N and after: 112 - 14122270", so S/N 14122270 is in both as printed. Stored as printed.
6. **Book attachments on the models.** I added the M13 weight box and WW10 wheel weights (both on page 45) to each model's `attachments[]` with `source: book`, kinds "weight box" and "wheel weights". These kinds are not in the schema's list (deck, blade, snowblower). Say if you would rather leave them as sections only.
7. **116 attachments.** Only the 116YT TractorData set (38", 42", 44" mid-mount decks, 38" blade, 38" snowblower) is on the 116 here; the 116 XC set is on the 8-2700 edition. This matches the still-open 8-2700 question.
8. **112 to 112B link.** I added a `seeAlso` relation from 112 to 112B (source inferred) carrying the "serial cannot tell them apart, ask the customer" note from the plan. Remove it if you want relations kept to the registry only.

## Bundle and sibling check

- Not a bundle. One catalog, 52 PDF pages.
- **No engine sections.** The book says engine parts come from the Briggs and Stratton distributor, so there are no BR numbers. Engines are on the ID page only: 108 C29097, 111 C29098, 112 C30146 (before S/N 14134908) and C33279 (after), 114 C29099, 116 C29100 and C33280 (no switch serial).
- Printed page 45 (M13 weight box, WW10 wheel weights) is in the PDF twice (PDF pp48 and 49, identical). Transcribed once (plan issue 14).
- Siblings: 8-2700 is the earlier 108 and 116 edition; 8-3100 (112B/114B/116B) shares the engines. No pages are shared with another book.

## Section map

| Printed page | Section | Applies to | Serial or other split |
|---|---|---|---|
| 5 | Fuel system; Choke and throttle | all | by model (108/111/112 vs 114/116) |
| 7 | Engine mounts | all | 112 before 14102824 and from 14122270; others all |
| 7 | Engine mount kit | 112 | 14102824 to 14122270 |
| 9 | PTO | all | ref 45: 112 14103055, 114 14104919, 116 14106472 |
| 11 | C44781 PTO clutch kit (refs 1-29) and parts not included (30-34) | all | component (kit installed) |
| 13 | Hood, frame and attaching parts | all | ref 26 by model |
| 15 | Seat and fenders (before) | all | 108, 111 all; before 112 14102824, 114 14104697, 116 14106421 |
| 17 | Seat and fenders (after) | 112, 114, 116 | same three breaks, and after |
| 19 | Steering gear | all | none |
| 21 | Front axle; Front and rear wheels | all | none |
| 23 | Travel control; Brake assembly | all | none |
| 25 | Belts, pulleys and idlers | all | 108 14084847, 111 14085810, 114 14087760, 116 14089591; 112 all |
| 27 | Lift system | all | 108 14084946, 114 14088189, 116 14089708; 111 and 112 all |
| 29, 31, 33 | C29241 transaxle (3 sections) | all | differential by transaxle model 826 / 843 |
| 35 | Electrical system (before) | all | as page 15 |
| 37 | Electrical system (after) | 112, 114, 116 | as page 17, plus harness 112 14103055, 114 14104919, 116 14106472 and cables 112 14122349, 114 14123089, 116 14123800 |
| 39 | Electrical hardware; Headlight and rear reflector | all | none |
| 41 | Decals (before) | all | as page 15, rows by model |
| 43 | Decals (after) | 112, 114, 116 | as page 17, plus 112 14122100, 114 14122900, 116 14123700 |
| 45 | M13 weight box; WW10 wheel weights | all | none |

## Numerical index against the tables (table kept, rows flagged)

- C15096 (page 19 ref 2) is not in the index; the index lists C26325 at 19/2 (table: ref 1).
- The index prints C27651 at 31/25; the table prints C27561 (checked at full resolution).
- C29192 indexed at 15/5 (table ref 7).
- C29245 indexed at page 23 ref 15 (table page 25).
- C31035 35/1 is printed twice in the index.
- C43044 indexed as "34 50" (table 35/10).
- 014- 712 and 132- 310 (page 25) are indexed with no ref.
- The index prints 129-2175 at 7/6; the table prints 195-2175.
- The index prints hardware with a space and a leading zero (131- 911, 013- 624, 061- 612); the tables print 131-911, 13-624, 61-612.
- Everything else matches in both directions.

## Kept as printed and flagged

- Refs not printed: hood ref 23, electrical hardware ref 13 (the index has neither).
- 4 unnumbered rows: C28030 (page 5), C33300 (page 37), C28962 and the C32178 headlight assembly (page 39).
- 20 NSS rows and 3 NLA rows (page 25 ref 23, page 35 ref 9, page 41 ref 8 "Case" medallion). The "use C..." replacements stay in the descriptions.
- Refs printed on two rows with no note saying which applies: engine mounts 2 and 3, PTO 32, PTO kit 23, hood 16, seat 3, 9 and 12, electrical hardware 6, 7, 14 and 15, decals 10.
- Hood ref 16: both foot rests are printed "R.H." (C29204 is probably L.H.). Hood ref 26: no instrument panel cap is listed for the 112.
- Typos: steering 5/18" washer and "steering gar"; brake ref 20 "15/16" - 18" on 131-69; lift ref 33 "x 4"; 192-20 called WASHER and 195-103 called LOCKWASHER on page 27.
- Short hardware codes 13-624, 13-628, 14-712, 61-612.
- "Early production" / "late production" rows with no serial: page 17 refs 10 and 18, page 25 ref 23.
- PTO kit ref 16 "for twin cylinder models only": tagged 114 and 116 with `inferred: true`.
- Lift page: "111 - ALL" and "112 - ALL" sit under "** Use S/N and after", read as the ** parts at all serials.
- Part numbers that appear only in notes or descriptions (no row, not in the index): C28937, C35291, C33171, C33170, C31336, C31335, C30161, C30162, C27569, C33025, C32396, C32397.
- REQ'D printed out of register on pages 11, 19, 35 and 39: 98 quantities mapped in sequence (counts equal) and flagged `inferred qty`.

## Handwriting on the scan (flags and notes only)

- Page 25 ref 20: 7" beside C33208 and 6" beside C27068.
- Page 29 heading: "PEERLESS #843".

## Format notes

- Description rows indented in the book (parts of an assembly) carry a flag naming the row they sit under; no new field was added.
- Section-level before/after pages store one serial variant per model with a `model` field (8-2700 format). On the "after" pages, a row with its own footnote stores the narrower window (for example 114 harness C31036: 14104697 to 14104918).
- TractorData attachments added per the standing step (`verified: false`): 108YT 34" deck, 38" blade, 38" snowblower; 111YT/112YT/114YT/116YT 38", 42" and 44" decks, 38" blade, 38" snowblower.
