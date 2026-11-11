# 8-3140 (Ingersoll 114H) lookup transcription: issues

*Transcribed 2026-11-10. File: `8-3140_lookup.json` (schema `lookup-v1.1`), 35 sections, 704 rows. Scan with no text layer: every table read by eye.*

## Summary
- **Bundle / siblings:** not a bundle. One model, 114H (hydrostatic), engine C33753 (B&S spec 294777, type 0117, twin cylinder). Sibling: 8-3210 (2014, same engine, hydrostatic), linked as `seeAlso` only. No pages shared with another book.
- **Serials:** none. No range on the cover or ID page and no S/N or P.I.N. note in any table (checked by eye on all 24 table pages). The 114H matches all serials.
- **Model name:** the engine ID table prints the tractor model as "114"; cover and headers print 114H. Stored as 114H, no "114" alias (earlier decision).
- **Attachments:** TractorData has no 114H page. The only attachments named in the book are in the Lift System footnote ("* is included with snowblower and 44" mower"), so the model lists a 44" mid-mount deck and a snowblower with `source: book`.
- **Paint and oil** (unnumbered page, PDF p3) stored as two sections, as in 8-3100.

## Needs your decision
1. **Carburetor refs (page 11).** The REF column is printed one row low: no number beside CARBURETOR, then 1 to 47 beside BODY through SCREW - clamp. The numerical index (C34392 = ref 1 ... C34292 = ref 48) and the table's own note "KIT - carburetor gaskets (includes Ref. 5, 23, 28 and 30)" both use the numbering one higher. I stored refs 1 to 48 and put the printed number in each row's flags. Say so if you would rather keep the printed 1 to 47.
2. **Two probable part-number misprints in the tables** (stored as printed, flagged):
   - Page 7 ref 23 GASKET - valve cover prints **C 34262**, the same number as ref 24 NUT - lock. The index and Gasket Sets ref 16 give **C34367**.
   - Page 17 ref 18 VALVE OVERHAUL GASKET KIT prints **C 34279**, which is a screw on pages 13 and 15. The index gives **C34379**.
   If you can confirm C34367 and C34379, I would change `partNo` and keep the printed number in `partNoAsPrinted`.
3. **Lift System starred rows (refs 32 to 36).** Stored with a `component` variant "snowblower and 44" mower". The footnote does not say whether the tractor also has these parts without an attachment.

## Table versus numerical index (table kept, each row flagged)
The index looks like it was typed from an earlier draft of the tables.

| Page/ref | Table prints | Index prints |
|---|---|---|
| 7/10 | C 34229 RETAINER - valve | C34279 at 7/10, and C34229 at 7/38 (the table ends at ref 37) |
| 7/23 | C 34262 | C34367 |
| 11/36 | C 34232 MANIFOLD - intake | C34323 (the governor shaft washer on page 9; probable index typo) |
| 17/18 | C 34279 | C34379 |
| 23/32 | 113- 233 | 113- 209 |
| 25/4 | C 36892 HOOD | C34007 |
| 33/18 | 129- 102 | 131- 176 |
| 35/9 | 129- 101 | 131- 934 |
| 37/23 | C 25556 WASHER 3/8" x 1-7/8 | 195- 521 |
| 39/5 | C 34716 KNOB - control | C15644 |

- **Rows not in the index (17):** ignition refs 10 to 12 (C34306, C34292, C34293), oil filter refs 15 and 16 (C34260, C34264), PTO ref 46 (C29243), brake ref 34 (192-20), electrical ref 13 (C34284 starter), C34369 R.H. valve cover, and Gasket Sets refs 2 to 8 and 10.
- **Index entries with no table row (2):** C34229 at 7/38 and C34196 at 7/22 (probably meant 17/2).
- The index prints `13- 624` and `13- 628` with a leading zero (`013-`); stored as printed in the table.
- Count check: 630 index entries, 645 indexable rows; 618 agree exactly.

## Kept as printed and flagged
- Refs not printed (index agrees): hood 23, electrical system 14, electrical hardware 13.
- Page 7 ref 22 C 34369 COVER - valve No. 1 R.H. prints qty 2 (the L.H. cover prints 1).
- Electrical ref 11 says "see page 53 for service" and ref 13 "see page 49 for service"; the headlight table is on page 47 and the starter on page 17.
- Paint refs 2 and 3 both print C 28850 (quart and heat-resistant spray), as in GZFC.
- Typos: "cylidner" (7/15), "BOWL ASSEMLBY" (11/27), "SHIELD - stater" (15/7), a stray quote before POPPET (39/24).
- 10 unnumbered rows (assemblies and kits), 49 NSS rows, 13 UAR quantities.
- Pen marks on the scan beside carburetor refs 5 to 9 and transaxle refs 36 to 39 carry no text.

## Method
Two table pages per image at 0.66x (12 images) plus one sheet of full-resolution zoom strips for every row that disagreed with the index. The numerical index was OCR'd column by column, compared with the transcription in sort order, and every difference was checked by eye on full-resolution index images. No REQ'D column is out of register in this book.
