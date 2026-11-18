# GZFC issues and decisions

Catalog GZFC: Ingersoll Grazer front-cut mower decks (zero turn mowers), a 23-page web-build excerpt (Distiller 5.0.5, Nov 2002) with a real text layer. Transcribed 2026-11-18 into `GZFC_lookup.json` (schema lookup-v1.1): 357 rows, 12 sections, 6 models. Parsed with `pdftotext -layout` and checked against the page renders.

## Decisions applied

- Source values `grazer` (C-numbers) and `grazer-hardware` (###-### codes); NSS rows carry no source. Hardware codes stay in hardware form (no G form).
- Decks are their own models, decks only, no tractor stubs: DECK42A, DECK42AC, DECK52RD, DECK52TCSS, DECK62TCSS, DECK62TCII. The three TCSS/TCII ids, names and aliases are the exact 8-3500 ones.
- TCSS pages are labelled TCSS from the contents group heading ("52TCSS, 62TCSS and 62TCII"); the page titles say only 52" / 62" (kept in `headingAsPrinted`).
- Section map:
  - paint, oil (PDF p3): the five decks other than 62TCII (not changed; say if 62TCII should be added)
  - deck_parts_42a_42ac (p5), deck_drive_42a_42ac (p7): DECK42A, DECK42AC
  - deck_parts_52rd (p9-11, one table, refs 1 to 70): DECK52RD
  - deck_parts_52tcss (p13), deck_drive_52tcss (p15): DECK52TCSS
  - deck_parts_62tcss (p17), deck_drive_62tcss (p19): DECK62TCSS and DECK62TCII
  - gearbox_curtis_c44917 (all six decks), gearbox_superior (52RD, 52TCSS, 62TCSS, 62TCII) (p21), decals (all six decks) (p23)
- Fitment notes recorded as variants plus section notes:
  - 42AC = G2000CII (printed "(42AC) use on G2000" and "42AC (G2000CII)"); 42A = all other G2000 models. Model variants carry `model` DECK42A / DECK42AC.
  - Vanguard belt C44241 (42A/42AC drive ref 21) is an engine variant.
  - G1800SS/KSS and G1890/K/V belt, guard and pulley notes are model variants (one variant per tractor model, alternatives). Tractor models printed without the G prefix (1890, 1890K, 1800SS, 1800KSS, 1890V) are stored with it.
  - "All except G2000CII" is stored as a model variant with that value.
- Serial breaks stored like 8-3500 (before = serialTo, after = serialFrom; per-model variants on the 62" drive). The unstarred 52" drive ref 10 blade C37930 carries an inferred "before" variant, as in 8-3500.
- Description typo corrected, original in row flags: "G200CII" to "G2000CII" (62" drive refs 2, 13, 17). Title typos: none needed; the 42A/42AC drive page heading (a copy of the deck-parts heading) is retitled "42A and 42AC Mower Drive".
- Ref 16 of the Curtis gear box prints 221-441 (clear on the render); stored as 221-411 with the printed form in `partNoAsPrinted`, kept the same as 8-3500 (user confirmed).
- Gear box and decals applicability (user 2026-11-18): the Curtis gear box applies to all six decks (every deck's drive page lists it); the Superior only to DECK52RD, DECK52TCSS, DECK62TCSS and DECK62TCII; decals to all six decks.
- Gear box page: Curtis assembly C44917 and grease C37975 print with no ref; stored with ref "" and flagged.

## Still open

1. **DECK62TCII on the 62" deck page (p17).** The page names no model; DECK62TCII is applied there only through the contents group heading (and on the 62" drive page through the footnote, plus the Superior gear box and decals). 8-3500 applied it to the drive page only. Not yet answered: confirm, or I drop it from deck_parts_62tcss.
2. **Variant `value` for tractor models.** Tractor model fitment (G2000CII, G1890 and so on) is stored as basis "model" with the tractor model as the value and no `model` field (only deck ids go in `model`). Say if the schema wants another basis.

Settled by the user 2026-11-18 (all applied): gear boxes by model per the parts lists (Curtis on all six decks; Superior on DECK52RD, DECK52TCSS, DECK62TCSS and DECK62TCII, since the 42A/42AC drive page lists only the Curtis); decals good for all six decks; 221-441 stored as 221-411, kept the same as 8-3500; "G200CII" corrected to G2000CII; the 62" drive side table quantities are per spindle (bolts per spindle shaft); the drive-page row differences against 8-3500 and 8-58030 were checked against both PDFs (see Sibling and bundle check).

## Serial and engine breaks

- 52" drive (p15): * before S/N 013306046 (serialTo 013306045), ** S/N 013306046 and after (serialFrom 013306046). Rows: refs 7, 8, 9 (star only), 10 (C37930 unstarred, inferred; C44136 **), 23 (star only), 24.
- 62" drive (p19): For model 62TCSS: before 013306063 / 013306063 and after; for model 62TCII: before 013307056 / 013307056 and after. Rows: refs 7, 8, 10, 23 (star only), 24. Each row carries a variant per model.
- Engine: Vanguard belt C44241 on the 42A/42AC drive (ref 21, "Use on all units with Vanguard Engines"). 52RD, 52" and 62" belts C44241 are listed "(1890V)" and stored as a G1890V model variant. No other engine breaks.
- Serial breaks match 8-3500.

## Numbering and forms

- Part-number forms: 306 grazer (C-numbers), 44 grazer-hardware, 7 NSS, 0 G.
- Hardware codes (32 distinct, stored as printed): 111-202, 111-203, 111-371, 113-1, 113-3, 113-54, 113-102, 113-103, 113-208, 113-257, 113-268, 113-312, 113-2419, 129-101 to 129-105, 131-71, 141-56, 182-528, 192-19 to 192-23, 193-1000, 195-102, 219-20, 219-23, 221-84, and 221-441 (stored 221-411).
- Paint part numbers print with spaces ("C   28849"); stored closed up.
- Ref numbering: every section runs from 1 to its last ref with no printed gaps. Refs repeat for alternates (42A/42AC splits at 12, 13, 14, 15 on the deck page and 2, 11, 20, 21, 29, 30 on the drive page; 52RD 38 and 39; drive pages 2, 7, 8, 10, 13, 17, 18, 24).
- Unnumbered rows (ref ""): wheel tire/rim/bearing sub-parts under ref 14 on four deck pages (42, 52RD, 52", 62"), Curtis assembly C44917 and grease C37975, and the Superior NSS assembly.
- 42A/42AC drive ref 18 (HUB - pulley, C41658) prints indented under ref 17 with its own number; stored as ref 18 and flagged.

## Kept as printed

- Descriptions keep their in-table fitment text (for example "BELT - drive (G1800SS, G1800KSS, G1890, G1890K)"); 8-3500 stripped these on the TCSS drive pages, GZFC keeps them.
- 52RD ref 42 prints "L.H" with no final period; ref 66 prints "2-1/2" with no closing quote; 52RD ref 68 prints no dot leader or quantity (stored empty, qtyNum null).
- "x 900" on the gear box elbow (degree sign lost); "10 ga" on 62" drive ref 22 (the 42A/42AC and 52" drive pages print "10 gage"; the committed 8-3500 62TCSS drive also reads "10 gage"); "anti-skid" on the 62" deck ref 8 ("anti-scalp" on the 42/52" decks).
- 62" drive ref 2 guard C37875 omits 1890V while ref 13 and 17 list it; kept as printed.
- Paint refs 2 and 3 both print C28850 (quart vs heat resistant 12 oz spray); both rows kept and flagged, as in 8-3500.
- The 42A/42AC drive prints C37887 on both ref 14 (PULLEY - spindle, qty 2) and ref 30 (the 42AC spindle pulley, qty 1); stored as printed.
- Same part, different quantity across pages: C37895 qty 1 on the 42AC drive, qty 2 on the 52" drive; C38566 qty 2 on the 62" drive.
- Page 83 ("see page 83 for repairs / service") and "also see page 69" are binder pointers outside this excerpt; see missingSections.

## Printed gaps

- None in the ref sequences.
- Page 83 (gear box repairs) is not in the excerpt; the gear box tables themselves (p21) are.
- The book gives no edition date and no model list for the gear box and decals pages.

## Numerical index

Not applicable. The book has no numerical index; the front index lists section titles and page numbers only, so there is no index cross-check.

## Sibling and bundle check

- **8-3500 (committed, same 2002 web build).** The paint, oil, 52TCSS deck, 62TCSS deck, Curtis gear box and Superior gear box sections match row for row (same refs, part numbers, quantities and descriptions). The 52TCSS and 62TCSS drive pages differ: GZFC has 4 more rows on each (the 1800SS/1890 alternates) and prints the fitment notes; I checked the attached 8-3500.pdf and 8-58030 PDF on 2026-11-18: those books print one row per ref on these drive pages (8-3500 52" drive ref 2 C37875, ref 13 C37893, ref 17 C37895; 62" drive ref 2 C37876, ref 17 C38566; 8-58030 p87 the same as 8-3500), with no fitment notes, so the committed files are right and GZFC is a different (fuller) print; one description also differs (62" drive ref 22: GZFC "10 ga", 8-3500 "10 gage"). Model ids reused as is; no stubs created.
- **G102 (committed).** Decals only: the four decals C37491 to C37494 match (same refs, quantities). G102 prints them for DECK52, DECK62, DECK72.
- **8-58030 (committed, G2018D).** deck_52_attaching matches GZFC's 52TCSS deck page exactly (45 rows); deck_62_attaching matches the 62" deck page except for GZFC ref 27 (C37958, WEIGHT - tail, 13 lb), which 8-58030 lacks; drive_62_mower matches except for the four alternate rows noted above (the 8-58030 PDF p87 prints only the single-row version, confirmed against the PDF).
- **Live G100/G101** (archive notes, not committed lookup files): G100 overlaps the 42A/42AC decks (1992+); G101 overlaps the 52A/52AC/52TCSS and 62TCSS/62TCII decks (1992+). The 52RD is in neither. These live books are not in the lookup repo, so no row comparison was possible.
- Bundle: no other books ride along in the PDF; no pages belong to another catalog.
