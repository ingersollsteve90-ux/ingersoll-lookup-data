# G102 lookup transcription: issues and decisions (2026-11-18, revised with your answers)

`G102_lookup.json` (schema `lookup-v1.1`): 16 sections, 501 rows. Bundle of two Grazer parts lists, one catalog, `books[]` with two entries (issue 35). Scan with no text layer; every table read by eye at 220 dpi, tesseract only as a draft on the gearbox and decals.

## Decisions applied 2026-11-18 (your answers)
1. **Deck models.** The 52", 62" and 72" decks are their own models (`DECK52`, `DECK62`, `DECK72`, family "Grazer mower deck"). The five G108-family zero turn mowers (G3100CD, G3200C, G4200CD, G3210C, G4210CD; stubs, edition in G108) each carry three `mid-mount deck` attachments (sizes 52", 62", 72", catalogId G102, source book, verified true). The deck sections apply to their deck model; decals and the Peerless gearbox apply to all three decks. Two things to be aware of: (a) the book prints no per-size fitment, so all three sizes are attached to all five mowers; (b) stubs normally hold only id, name, ref and note, so adding `attachments` to a stub is a small extension of the schema, and the book does not print the mount type (the kind label is yours).
2. **`source` values.** All G102 rows use `grazer` (G#######, 27xxxxx and decal numbers) and `grazer-hardware` (numeric hardware codes and F102). The locked schema lists briggs / case / case-hardware / perkins, so the plan doc's Row definition needs these two values added.
3. **EM72 deck ref 45** is stored as G9002547 (the printed G9002537 is crossed out and 47 written in); printed number kept in `partNoAsPrinted`. This matches the 3 cylinder "H Taper Hub" 900-2547 on the 62" drive. The handwritten `H x 1"` beside the struck description is flagged; the description is stored as printed.
4. **Gearbox ref 7** is now "Bevel Gear, 26 Teeth" (printed "926 Teeth", original in flags).
5. **EM52 carriage ref 22** is now `35003C` (printed `350035`, kept in `partNoAsPrinted`, flagged).

## Still open
- **EM72 carriage ref 10 (Support Brace, qty 2).** The last digit is hidden by an ink mark: `G346000?`. Searching the book for the same family: the only other "Support Brace" is `G3360008` (EM62 and EM72 carriage ref 34), which starts G336, not G346. Nothing else in the book is labeled support brace with a G346 number. The G346000x numbers that are printed are 0 (deck), 2 and 3 (pulley box covers), 4 and 5 (gauge wheel mounts) and 6 (roller pin); 1 and 7 do not appear anywhere, but that is not enough to pick one, so it stays `G346000?` and flagged. Needs the digit from a clearer copy or a part in hand.
- **EM72 deck ref 34** has no printed text; `G900 2540`, "Sheave, TBX 62H", qty 1 are handwritten (stored as G9002540, matching the 62" drive 900-2540, flagged as handwritten).

## Serial and engine breaks
- No serial breaks anywhere; confirmed by eye on every table.
- **62" deck drive** refs 11 and 12 split by engine (`variantBasis: engine`, issue 37): 4 cylinder (900-2539 double pulley, 900-2546 taper hub) and 3 cylinder (900-2538, 900-2547 "H Taper Hub"). The 4-cyl taper hub (ref 12, 900-2546) has no cylinder count printed; its 4-cyl variant is inferred from the pairing (flagged).

## Numbering and forms
- 62" deck drive is typeset in the 900-/300-xxxx style; stored in G form (900-2518 -> G9002518, 300-0015 -> G3000015, 335-0001 -> G3350001), printed form in `partNoAsPrinted`, flagged on each row. Several map to numbers used elsewhere in the book (300-0031/0032/0034 = G3000031/32/34 on the EM62 deck, 900-3020 = G9003020, 900-2540 = G9002540 on the handwritten EM72 row).
- 62" drive ref 28 prints `600-0001` in a different (condensed) typeface; stored G6000001 (inferred from the 52" G6000000 and 72" G6000002), flagged.
- Decals print `C 37491` to `C 37494`; stored closed up.

## Kept as printed + flagged
- EM62 carriage ref 27 grease zerk prints 450543 (the EM52 and EM72 carriages print 45051); kept as printed.
- EM72 deck ref 33 "Shoe, LH" carries G3300011, the RH shoe number elsewhere (kept).
- Typo corrected: EM52 deck ref 28 "Decal; Danger" -> "Decal, Danger" (original in flags).
- Qty printed as a dash or "As Req'd." (qtyNum null): 52" drive refs 18, 28; 62" parts rim; 62" drive ref 18; 72" rim and drive ref 28; gearbox refs 8, 9.
- Wheel-assembly tire, rim and bearing rows print without an item number: stored with ref "" and flagged as indented under the wheel assembly.

## Printed gaps (not missing from the file)
Gearbox refs 13, 20, 21, 27; EM52 deck ref 33 (blank row); EM52, EM62, EM72 carriage ref 17; EM72 deck ref 54; IID shaft refs 2 and 14.

## Numerical index
**The book has no numerical index** (contents list only), so there is no index cross-check and no index-vs-table differences (same situation as 8-58030).

## Sibling and bundle check
- Bundle: confirmed (book 1 decks, book 2 EM mowers), one PDF, one catalog.
- Not linked to the G2018D (8-58030, issue 36). Book 1 fits the live G108 family of zero turn mowers per the cover. No weight box or wheel weights printed, so no such attachments added.
- Overlaps: no live-catalog data was in this session, so G108, G100, G101, 8-3500 and GZFC were not compared part by part. Within the book, 52" and 62" deck gearbox G9005618 and the 2736461/2736462 EM parts repeat as expected.
