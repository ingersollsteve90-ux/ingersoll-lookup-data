# 8-3021 issues list (lookup-only transcription, 2026-11-11)

Ingersoll Compact Tractors 1012, 1014, 1016, Parts Catalog 8-3021 (6-88-RP-400-385, replaces 8-3020). 44 sections, 926 rows, schema `lookup-v1.1`.

## Checks done
- **Bundle:** not a bundle. One catalog, 35 PDF pages (cover, paint/oil + ID table, 30 table spreads, numerical index pp64-68).
- **Sibling:** 8-3100 (112B/114B/116B) shares the engine, hood, seat, PTO, steering, axle, lift and electrical pages. Its committed file was used as a draft for those pages only; every row was compared with this book's own table. 46 rows carry a different part number or are new, 4 more a different quantity.
- **Transmission comparison (plan decision #18):** confirmed different. 8-3021 has the **C30887 friction-drive gear case** (differential, brake, housings, input shaft and pinion gears) plus spindle and drive disc, neutral cam, input shaft, drive chain and traction-arm tables (printed pp41-53). 8-3100 has the C29241 5-speed transaxle. No rows are shared between the two transmissions, so `driveType` is `friction` for all three models.
- **Numerical index:** 894 entries compared in sort order, both directions. Everything matches. The index also confirms every doubtful reading below.
- **Ref continuity and quantities:** see the `validation` block in the JSON.

## Needs your decision
1. **Seat and fenders "Use before PIN" page (p29) omits the 1016 line.** It prints only 1012-14103745 and 1014-14105556. The facing "PIN and after" page prints 1016-14116701, so I stored the 1016 as "before 14116701" with `inferred: true` (same idea as the B1193 unlabelled-sibling rule). Confirm or tell me to leave the 1016 off that page.
2. **Harness C31036 on the "PIN and after" electrical page (p59)** is printed "(1014, 1016)" with no serial, while the row above says C31443 is for "1014 S/N 14105564 and after (1016 all)". 8-3100 prints the same row as "114B before PIN 14105564". I stored a 1014 window of 14105556 to 14105563 as inferred and gave the 1016 no window. Confirm.
3. **1014 break printed three ways** (same as 8-3100, issue 8): 14105556 on the seat and electrical headings, 14105564 on the PTO footnote and harness row, 14105555 on the decal and headlight footnotes. Registry value kept at 14105556; each row keeps its own printed value.
4. **Decal breaks differ from the main break:** decals use S/N 14103738 (1012) and 14105555 (1014), "1016-all". Stored as printed on the decal rows only.
5. **Differential ref 4 (C19311 PIN - drive) prints a quantity of "11".** Checked at 4x zoom; it looks like a double-struck 1. Stored as printed (11) and flagged. Say if you want it changed to 1.
6. **TractorData attachments** (42" P42 deck, 38" M52 blade, 38" T82 snowblower) added to the 1012 and 1014 only. TractorData has no 1016 page, so the 1016 has none. Say if the 1016 should get the same list.

## Kept as printed and flagged
- **BR 27352** (flywheel ref 3, 1014/1016 spring washer): table and index both print BR; 8-3100 prints C 27352. Stored as 27352, source briggs. Worth a store check under both forms.
- **111- 102** (PTO ref 24): smudged in the table, but the index also prints 111- 102 at 25/24. 8-3100 prints 113- 102 for the same bolt.
- **111- 202** (steering ref 4): 8-3100 prints 111- 132.
- Hardware codes with doubtful prefixes: 11- 312, 13- 624, 13- 628, 14- 712, 83- 520 (the index prints them 011-, 013-, 014-, 083-).
- Same code, different size in the descriptions: 113- 208 (1-1/4" on p45, 1" on p49), 129- 163 (3/8"-24 on pp37/45, 3/8"-16 lock on p51), 195- 103 (5/16" here), 195- 2029 (7/16" on p47, 3/8 on p53), 195- 521 (1/4" on p39).
- Typos: "ASSEMLBY" (p5), "BLAFFLE" (p21), "INSULATION - full line" (p11), "support(shown)" (p25).
- Refs not printed: carburetor 1014/1016 ref 9, blower refs 4 and 20, hood ref 23, electrical hardware ref 13.
- No quantity printed: gasket kit C27335 (p7) and carburetor 1012 ref 7.
- 16 unnumbered rows (assemblies and kits) and 22 NSS rows, including the two "25th anniversary" hood decals (ref 3, no model named).
- Footnotes kept as notes only: "*Order C30507 to get 4 complete mounts" (p23; C30507 is not a row and not in the index) and the headlight "*Will require 2 before S/N 14103738 / 14105555 / 14116700" (says nothing about what changes).

## Inferred quantities
REQ'D is printed about half a row low on printed pages 33, 41, 45, 47, 49, 51, 53 and 61. Quantities were mapped to rows in sequence; the counts are equal in every table. 219 rows are flagged `inferred qty`.

## Part numbers that differ from 8-3100 on shared pages
Engine 1014/1016 ref 38 (187-1047, was 187-1334) and ref 49 (C18814, was C19473); fuel filter C28935 (C31978); hose clamp 214-251 (C32376); blower plate C27370 (8-3100's table reads C27270, its index C27370); spindles C26371 / C26034 (NSS in 8-3100); valve stem C10442 (C28236); wheel spacer C30555 (C27047); lift washer C25556 (C28987); ignition key C27751 (C32407); solenoid C27523 (NSS); headlight assembly C22571 (C32178); fuse holder C30261 (C31947); all hood decals, instruction decal C30857 and seat decal C31030. Electrical hardware refs 8 to 10 are quantity 6 here (2 in 8-3100).
