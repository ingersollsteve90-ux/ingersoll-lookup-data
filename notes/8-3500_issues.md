# 8-3500 lookup data: issues list

Catalog 8-3500 (Ingersoll mower decks, excerpt). File: `8-3500_lookup.json`, schema `lookup-v1.1`.
559 rows in 17 sections, 8 models (6 decks, 2 mulching kits), `coverage: partial`, text layer yes.
Prepared 2026-11-18.

## Decisions applied

From your message:
- Grazer book: row `source` is `grazer` (C numbers; 379 rows) or `grazer-hardware` (numeric codes; 175 rows); NSS rows (5) have no source. No `case` / `case-hardware`.
- Part numbers stored with whitespace removed; the printed form is in `partNoAsPrinted` (including footnote stars, e.g. `C44128 * *`).
- Descriptions kept as printed; every oddity is in the row `flags`.
- Text layer used (`pdftotext -layout`), then every page compared by eye with the page render. As an extra check, each page's part-number column was OCR'd from the page image and compared with the parsed list in row order: all 559 part numbers agree. (No G/6 type confusion is possible in a born-digital layer, but the check was done anyway.)
- Numerical index: not applicable (see that section).

From your answers to my questions:
- Models are decks only: DECK52SD, DECK62SD, DECK72SD, DECK52TCSS, DECK62TCSS, DECK62TCII (added 2026-11-18), plus MK52SD and MK62-2B as their own models. No tractor or mower stubs; the DECK52SD / DECK62SD models carry a `mulching kit` attachment pointing at MK52SD / MK62-2B.
- TCSS pages labelled as TCSS and flagged: the page titles say only 52" / 62", but the cover contents put pages 59-67 under "52TCSS AND 62TCSS".
- Full tables from this book, overlaps reported below (no stubs for deck content).
- Fix titles only: "6ZSD MOWER DRIVE" stored as "62SD Mower Drive"; the 52SD drive page (heading is a copy of "52SD MOWER DECK AND ATTACHING PARTS") titled "52SD Mower Drive"; the mulching kit section titled "Mulching Kits MK52SD and MK62-2B". Every printed heading is kept in `headingAsPrinted`. Part numbers and descriptions are not corrected.

My own calls (tell me if you disagree):
- PDF p2 "Paint and Oil" is a real parts table that the contents do not list. Stored as two sections (`paint`, 7 rows; `oil`, 3 rows), applying to the five deck models.
- The p3 General Information page has only an example table from another book; skipped (as in 8-3100).
- Page numbers: each row's `page` is the contents-list page of its diagram/table pair (3, 5, 7, ... 19 and 59-67); `pdfPage` is the table's PDF page. Paint and oil have no page number (`page` is "PDF 2"). The p5 footer prints a stray "58".
- The text layer reads "alIen head" (capital I) on both Curtis gear box pages; the page prints "allen". Stored as "allen", flagged on both rows.

## Still open

Answered 2026-11-18 and applied: mulching kit ref 6 C46701 qty stored as 1 (printed "I", original in flags); `113-2419` and `193-1000` stay in hardware form; 62TCII is its own model `DECK62TCII` (page 29 footnote "For Model 62TCII"); TCSS Curtis gear box ref 16 stored as `221-411` (printed 221-441, kept in `partNoAsPrinted`; 221-411 is the 1/8" 90° street elbow in the store catalog); C37930 "before S/N 013306046" inferred tag confirmed; `MK62-2B` stays the model id with the aliases MK62SD and MK62; no 5818V stub unless official documentation says the decks fit.

1. **8-58030's missing 52" drive and gear box (issue 21):** not linked. The 62TCSS deck and drive match 8-58030 row for row, but the missing tables cannot be compared, so "same" is unproven. Leave it until a copy of those 8-58030 pages turns up.
2. **DECK62TCII scope:** only the 62" drive section (p29) names 62TCII. The 62" deck (p27) and gear boxes (p31) apply to DECK62TCSS only, as printed.

## Serial and engine breaks

| Where | Break as printed | Stored as |
|---|---|---|
| Curtis gear box, 52SD and 62SD (PDF pp17, 19) | "Prior to Serial #010706048" (p17) / "After PIN #010706048" (p19); the diagram pages print "PIN" for both | Section `gearbox_curtis_before_010706048` rows: serial variant `serialTo` 010706047. Section `gearbox_curtis_after_010706048` rows: `serialFrom` 010706048 |
| 52TCSS drive (PDF p25) | "* Use before S/N: 013306046", "** Use S/N: 013306046 and after" | `serialTo` 013306045 / `serialFrom` 013306046 on refs 7, 8, 9, 10, 23, 24 |
| 62TCSS drive (PDF p29) | "For model 62TCSS: * before S/N 013306063, ** S/N 013306063 and after" | one variant per starred row with `model` DECK62TCSS: `serialTo` 013306062 / `serialFrom` 013306063 |
| 62TCSS drive, second footnote | "For model 62TCII: * before S/N 013307056, ** S/N 013307056 and after" | second variant on the same rows with `model` DECK62TCII: `serialTo` 013307055 / `serialFrom` 013307056 (62TCII is its own model, DECK62TCII) |
| Gear box refs 18 (pp25, 29) | Curtis model C37898 / Superior model C42775 | `component` variants "Curtis gear box" / "Superior gear box" |
| Mulching kit rows | rows marked (MK52SD) or (MK62SD) / (MK62-2B) / (MK62) | `model` variants with `models[]` |

Other facts:
- No engine appears anywhere in the book (decks only), so no engine breaks.
- Serial numbers keep their leading zeros as strings. The 9-digit 0133xxxxx numbers match the Grazer series in the plan.
- Starred rows with only one side printed (no counterpart): 52TCSS drive ref 9 (C42786 *) and ref 23 (C37886 *), 62TCSS drive ref 23 (C37886 *). Stored with the "before" variant only and flagged.
- Unstarred sibling rows: the 62TCSS drive refs 5, 6, 9 and the other unstarred rows carry no variant (they fit all serials).

## Numbering and forms

- No `###-####` Grazer numbers (320- / 330- / 900-xxxx) occur in this book, so nothing was converted to G form and no row carries a "stored in G form" flag.
- Letter-prefix numbers (`C#####`, 379 rows) are stored closed up, source `grazer`. Hardware codes (`113-3`, `192-19`, `219-20`, ...; 175 rows) are stored as printed, hyphen kept, source `grazer-hardware` (the same form 8-58030 uses).
- Whitespace removed from: `C 14482` (62SD drive ref 45), `131 -69` (mulching kits ref 18), and `C   28849` style numbers on the paint and oil table (all 10 rows).
- Footnote stars removed from `partNo`, kept in `partNoAsPrinted`: `C37883 *`, `C44128 * *`, etc. (18 rows: 9 on p25, 9 on p29).
- `###-####` hardware shapes: `113-2419` and `193-1000` (open item 2).
- All 5 NSS rows (52TCSS deck refs 24, 25; 62TCSS deck refs 25, 26; Superior gear box assembly) stored as `NSS` with no source.

## Kept as printed

- Descriptions all as printed, including mixed case on the 72SD drive refs 46-48 ("Pulley - Idler", "Bolt - spring tension", "Nut - 3/8" - 16, hex") and "idler, idler 5-1/2"" (62SD drive ref 46).
- "spindle. short" (period) on the 52SD and 72SD drives ref 7.
- "RH." (no second period) on mulching kits ref 10 C45516; "1'" (foot mark) in the ref 14 bolt; "x 18 x 5/8" in the ref 15 screw.
- "x 900" for the 90° elbow on the TCSS Curtis gear box ref 16; part number stored 221-411, printed 221-441 (user decision 2026-11-18).
- Quantities that differ between sibling tables are kept as printed, e.g. ref 26 bolt 1/4" - 20 x 3/4": 10 (52SD), 4 (62SD), 8 (72SD).
- 72SD drive: ref 35 and ref 36 both print `113-207` (3/8" - 16 x 1" and 5/16" - 18 x 1"); ref 37 prints `192-21` for a 5/16" lockwasher (the 52SD/62SD tables use `192-20`). Flagged.
- Duplicate ref numbers (flagged): 52SD drive ref 10 (C44136 blade / C45248 mulching blade) and 62SD drive ref 10 (C44138 blade / C45511 mulching blade), the mulching blades printed "not shown"; paint refs 2 and 3 share the part number C28850 (quart black / heat-resistant spray black). Mulching kit refs 1, 6, 10, 11 and 12 repeat by design (one row per kit) and are tagged with model variants instead.
- Notes on the page that are not table rows: the 52SD drive yellow note box ("Item #5 See Note Below": Complete Spindle C46682 consists of 219-20 Zerk (1), C46683 Housing (1), C46685 Spacer (1), C46686 Bearing (2)) is stored as a section note, not as rows (ref 40 already carries C46682). The cross-reference "see page 83 for repairs / service" (pp25, 29) is kept in the description text.
- Wheel sub-parts (tire, rim, bearing, grease fitting) print with no item number under ref 14 on all five deck-parts pages: 18 rows stored with ref "" and flagged "indented under ref 14". 7 more rows (the complete-assembly and grease rows on the gear box pages, and the Superior assembly row) also print with no ref number and are flagged.
- Trailing periods after "R.H." / "L.H." are absorbed by the dot leaders in the text layer, so a few descriptions end "R.H" (as on the printed page p5, p9).

## Printed gaps

- 72SD deck parts (PDF p13): refs 3, 21 and 49 are not printed.
- 72SD deck drive (PDF p15): ref 8 is not printed.
- No other gaps. All other sections run continuously from 1 (paint 1-7, oil 1-3, 52SD deck 1-47, 52SD drive 1-45, 62SD deck 1-48, 62SD drive 1-46, gear boxes 1-17 and 1-17, mulching kits 1-18, 52TCSS deck 1-42, drive 1-43, 62TCSS deck 1-27, drive 1-28, TCSS Curtis gear box 1-17, Superior 1-14).
- No qty is missing. No REQ'D column is out of register. 3 UAR rows (ref 30, WASHER - thrust C13716, on the 52SD, 62SD and 72SD deck-parts pages); `qtyNum` is null for them.

## Numerical index

Not applicable: the book has no numerical index (the cover index lists section titles and page numbers only), so there is no index cross-check and no index-vs-table differences. The cover contents were used only to label the TCSS pages and to map page numbers.

## Sibling and bundle check

- **Not a bundle.** One catalog, one book. It is an excerpt of a larger book: the contents run 3-19 and 59-67, and the tables refer to "page 83" for gear box repairs/service (not in this PDF). `coverage: partial`, `missingSections` lists what is absent.
- **8-58030 (committed file compared row by row, same ref and part number and qty):**
  - 52TCSS deck (p23) vs 8-58030 52" deck: 43 of 43 non-NSS rows identical.
  - 62TCSS deck (p27) vs 8-58030 62" deck: 27 of 28 identical; C37958 (WEIGHT - tail, 13 lb, ref 27, qty 3) is only in this book.
  - 62TCSS drive (p29) vs 8-58030 62" drive: 33 of 33 identical (same 013306063 break).
  - 8-58030 has no 52" drive or gear box tables (issue 21); the 52TCSS drive and both gear boxes here would fill those gaps (open item 8).
  - The SD pages differ from 8-58030: part overlap per section 26/51 (52SD deck), 10/45 (52SD drive), 29/52 (62SD deck), 13/46 (62SD drive), 25/53 (72SD deck), 5/44 (72SD drive); the SD tables are a different generation.
- **Within this book:** SD deck vs TCSS deck share 25 of 51 (52") and 16 of 52 (62") part numbers. The TCSS Curtis gear box (C44917) matches the SD Curtis gear box (pre-PIN 010706048) on every component except the elbow (221-441 vs 221-411) and the grease cartridge (C37975 vs C43346).
- **Live G101 (from the project archive notes; its data was not available):** it holds the 52" and 62" decks and the MK52 / MK62 mulching kits, so it overlaps this book's mulching kits and TCSS pages. Its notes agree with two readings here: C37930 is treated as "before S/N 013306046", and the 62TCSS drive ref 23 is the C37886 blade washer "before S/N" (this book prints C37886 * on both the 52TCSS and 62TCSS drives, with no ** row).
- **Live G100 (archive notes):** its 42TCSS deck has the ref 22 PIN C10821 struck through by hand. This book prints C10821 "PIN - deck" unstruck on the 52TCSS (p23, qty 1) and 62TCSS (p27, qty 2) deck pages; a part-by-part check needs the G100 data.
- **G102 (committed file):** only one part number is shared: C37494 (Danger decal; also mulching kits ref 5). G102's decks, gear boxes and drives use G####### numbers; no overlap with this book's decks. The G102 stubs (G3100CD ... G4210CD) were not given attachments from this book (no fitment printed).
- **Not compared (data not available in this session):** live 8-3400 (52SD/62SD/72" decks; the 010706048 gear box break is the same as in the plan's survey), live 8-58040 (52"/62" TCSS decks and the 62TCSS / 62TCII breaks), the live data for G100, G101 and G108 (only the archive notes above were available), and GZFC (not yet transcribed; its 52"/62" TCSS tables and breaks look identical to this book's, per the survey). Overlap with 8-58030, G102 and within this book is reported above; the rest is for you to decide when those files are available.
