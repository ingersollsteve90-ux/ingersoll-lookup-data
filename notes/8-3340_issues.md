# 8-3340 issues (lookup-only transcription, 2026-11-23)

Ingersoll front cut tractors 5720V, 5818V, 5820V and 5822K. Born-digital PDF with a text layer, 45 pages, no numerical index. `8-3340_lookup.json` (schema `lookup-v1.1`): 28 sections, 708 rows (686 table rows, counting the inferred 5818V engine row, plus 22 paint and oil rows).

## Source copy
- The archive folder holds three copies. **Used: `8-3340  IEC Front Cut.pdf`** (modified 2002-11-16), which is byte-identical to the PDF attached in chat.
- `(rev 2002-10-27)` is the **older** copy despite the "rev" label. It renders the same on 44 of 45 pages and differs only on the paint and oil page (PDF p5). It has no pages the newer copy lacks, so it was not used.
- `Front Cut Tractor Models, 5720V,5818V,5820V,5822K.pdf` (a 2018 save) renders identically to the newer copy on all 45 pages.

## Decided by the user 2026-11-23 (all applied; nothing open)
1. **Old paint page parts added:** C31643 (Power Red 1 oz touch-up) is now in `paint` and C32776 (SAE 30 oil) in `hydraulic_oil`. Both come from the older copy (rev 2002-10-27), keep its printed qty 1, and are flagged.
2. **5818V engine, inferred:** C44853 "B & S Model 350447, type 0139 (18 hp)" is added as engine ref 1 for the 5818V. The number comes from live 8-3400, so the row's model variant is `inferred: true`. The printed C46506 (351447 type 1192, 20 hp) is now tagged 5720V and 5820V (also `inferred: true`). The 5818V's `catalogEngineNo` is C44853 (hp 18), with a note saying it is inferred.
3. **Cross-shaft ref 2 stored as C37752.** The printed C37725 is kept in `partNoAsPrinted` and flagged. The parking brake ref 13 spring stays C37725.
4. **W48 is kind `tail weight`** (new attachment kind, now accepted).
5. **Tail wheels:** the DTW10 dual and single tail wheel `component` variants stay as delivered.
6. **TractorData set on all four models:** FM52SD, FM62SD, FM72SD, FCSB54 and FCSB51 stay on the 5720V, 5818V, 5820V and 5822K (`verified: false`).
7. **The electric deck lift is an optional extra.** Both deck lift sections now use `variantBasis: component`, and every row has the variant "electric deck lift (optional extra)". The lift lever is the standard lift.

## For the fitment chat (not done here, per Master Plan 2b-1 point 5)
- The book prints **no decks**, so this file has no deck models or deck sections. The tractor → deck pair rows for `ATTACHMENT_FITMENT.csv` (5720V, 5818V, 5820V and 5822K with 52SD, 62SD and 72SD; basis tractordata) are left to the fitment chat.
- TractorData also lists a **5825K** (2003-2005, Kohler 25 hp) in the same series. It is not in this book.

## Kept as printed + flagged
- **Ref gaps** (printed gaps): engine Vanguard 9 and 13; base 29; body 5720V 23 and 38; body 5818V/5820V/5822K 23 and 29; seat lid 13 and 14; single tail wheel 5; drive R.H. 7-9; drive L.H. 7-9 and 26; electrical Vanguard 19.
- **5720V body ref 14** prints `131-102` for a 5/16" x 3/4" BOLT (131- codes are nuts; probably 113-102).
- **Single tail wheel tire C37857**: qty 8 under a one-wheel assembly (8-58030 has the same misprint).
- **Same code, different size** (row flags on the first four):
  - 113-4: 1/4 x 1 and 1/4 x 1-1/4 (seat lid ref 26)
  - 113-17: "1/4 - 20 lock" (fuel ref 14) and 1/4 x 1-1/4
  - 121-21: 1/4 x 1/2 flange and 1/4 x 3/4 self-tap
  - 195-521: 5/16 and 1/4
  - 195-102: 1/4, 5/16 and 5/16 x 3/4
  - 195-103: 3/8 and 5/16
  - 195-104: 3/8 and 7/16
- Steering cable kit ref 6 prints "NUT - 1/4"-10" (131-71 is 1/4-20).
- Hydraulic ref 11 prints "900" for 90° (as in 8-3500 and GZFC).
- Drive R.H. ref 29 is 113-203 x8 plus 113-267 x2; drive L.H. ref 35 is x2 and x6.
- Both cross-shaft fans print "CCW".
- "5822 K" in decals ref 1.
- Arm rest kit (seat lid ref 23, NSS, optional) prints no qty.
- Decals ref 15 qty "I" is stored as 1.
- **Typos corrected** (original kept in each row's flags):
  - "1-318" → 1-3/8 (DTW10 ref 9)
  - "RECEPTICAL" → RECEPTACLE (both electrical pages)
  - text-layer "balI" → ball and "l8" → 18
  - "CYUNDER" → Cylinder (deck lift heading; the printed form is in `headingAsPrinted`)
- **Part numbers printed with a space**, stored closed up: C41 015, C31 947, C 14304, 131 -911, 131 -71, 131 -356.
- Cross-shaft ref 2: printed C37725, stored C37752 (decision 3 above).
- One Briggs number: BR93805 (booster fan ref 2), stored bare as 93805.
- **Skipped (not a parts table):** the "Indented descriptions" example on the General Information page (C55159 rear steering cylinder rows from another book).

## Draft parse comparison (`LOOKUP_8-3340_parsed.json`, 661 rows)
My transcription has **24 more table rows** than the draft:
- fuel refs 9 and 15, where the spaced part numbers were dropped
- the W48 row on the 5818V/5820V/5822K body page
- seat lid ref 23 (arm rest kit, no qty)
- DTW10 ref 22 (131 -356)
- 15 NSS sub-rows on the hydrostatic pump (refs 5-8, 10-20 and 22-25; the draft also mangled refs 5-8)
- 4 transmission rows (3 NSS sub-rows under ref 1, and ref 28)

Other draft errors:
- "UAR" read as "AR"
- 5720V body ref 6 W48 mangled into the part-number field
- decals ref 15 qty empty
- no paint and oil section, and no indentation, model variants or flags

## Sibling check: live 8-3400 (Grazer G1897V / G2097V / G2597K)
Same chassis family. Section by section, 517 of the 651 per-section part numbers here also appear in the matching 8-3400 section; 334 of the 423 distinct part numbers here appear somewhere in 8-3400.

**Identical:** booster fan, transmission, lift lever, hydraulic system, both deck lift tables. The 5818V/5820V/5822K body page also matches 8-3400's body 34 of 34 by ref.

**Mostly shared:**
- DTW10 and single tail wheel: all numbered refs match; 8-3400 has no wheel sub-rows.
- Drive R.H./L.H.: the wheel assembly is C37763 here and C48458 in 8-3400.
- Fuel: hose C44027 here, C32328 in 8-3400.
- Steering cable kit: 21 of 21 part numbers.

**Different:**
- 5720V body: 3 of 47 rows match by ref.
- Base (23 of 37 part numbers): different deck arms, idler and belt guard.
- Seat lid (32 of 42 part numbers).
- Vanguard clutch: C37511 with sub-parts here, C46994 in 8-3400.
- Electrical pages: about 27 shared numbered rows each; the unnumbered hardware here is not in 8-3400's dot data.
- Decals: 8 of 23 shared (model-name decals differ).

**Quantity differences on the same ref and part number** (this book's table kept):
- engine 131-69: 4 here, 5 in 8-3400
- seat lid 182-528: 2 here, 3 there
- seat lid 193-1000: 6 here, 7 there
- cross-shaft fan C46792: 2 here, 1 there
