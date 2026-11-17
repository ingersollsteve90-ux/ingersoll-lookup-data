# 8-3220 (Ingersoll 2012, gear drive) — issues and notes

Transcribed 2026-11-17. `8-3220_lookup.json`, schema `lookup-v1.1`: 34 sections, 678 rows, one model (2012), one stub (2014).

## Needs your answer (defaults applied in the file)

Both are index-vs-table differences. The table value is stored, using the standing reading from 8-3210 (table wins unless it duplicates a neighbouring row or contradicts a cross-reference). Neither case does either, so the table stands. Tell me if you want the index value instead.

1. **Choke and throttle, 19/1:** the table prints **C37095** (CONTROL - throttle/choke). The index prints **C37905** at 19/1 and has no C37095. Looks like a digit transposition in the index.
2. **PTO, 23/46:** the table prints **C29243** (GUIDE - belt). The index lists C29243 at **23/40**, which is the position of C17066 WASHER - cup (also indexed at 23/40). C29243 is not indexed at 23/46. Looks like an index typo; C29243 is also the idler belt guide on the belts page (35/6).
3. **8-3280 attachments** (RM42Y2, RM44YR2, SB38Y2, UB38Y2, BG42Y2): linked from the 2012 the same way as in 8-3210 (`catalogId` 8-3280, `source: book`, `verified: false`; bagger kind not in the schema list). Same open question as 8-3210.

## Numerical index (printed pp52-54, read in full by eye)

605 index entries against 607 indexable table rows (NSS rows and the paint and oil page are not indexed). 602 agree exactly. The rest:

- The two differences above.
- **Not in the index, kept as printed and flagged:** exhaust 15/16 C37108 and 15/17 C37200, hood 25/21 C31597.
- **Index entry with no table row:** C28962 at 47 (no ref). Nothing to store; noted on the electrical hardware section.
- The index prints C34630 (11), C40798 (17) and C32178 (47) with no ref, matching the three unnumbered rows.
- Hardware 13-628, 61-612 and 83-55 print with a leading zero in the index (stored as in the table).

## Serial breaks (issue 25)

Confirmed by eye on all 24 table pages: **no serial or P.I.N. break anywhere**. The ID page has only the stock "references to serial numbers" note and no range. The only split is by **transaxle model 826 vs 843** on the differential page (ref 4, 11 and 12 printed twice: `+` = 826 double-D axle shafts, `++` = 843 splined). Stored as `variantBasis: transaxle` with one variant per row. The case/input and shifter/counter-shaft transaxle pages carry no 826/843 marks. The 2012 matches every serial, so the finder asks for the model.

## Bundle and sibling check

Not a bundle (one book, 29 PDF pages, no text layer). Sibling 8-3210 (2014, same 1-92 print run) was compared row by row only after this book's tables were read. Shared (same ref and part number): PTO 46/46, seat and fenders 21/21, steering 21/21, lift 14/14, headlight 8/8, wheels 13/13, fuel 16/17, front axle 21/22, hood 35/37, weight box 6/7. The engine sections are entirely different (single cylinder C37031 here, twin C33753 in the 2014), and the 2014's hydrostatic pages have no counterpart; this book has the C29241 5-speed transaxle in three tables.

**Follow-up for the 8-3210 file (not touched):** it has no `seeAlso` to the 2012. Add one there if you want the link both ways.

## Flagged rows

- Typos corrected, original in the row's flags: LOCKWASHSER (baffles 4), fillter (gasket kit 4), MAINIFOLD (air cleaner 7), interloc (electrical 13). Heading "HEADLIGHT AND REAR RELECTOR" is kept in `headingAsPrinted`, title corrected.
- Engine base ref 5 prints a trailing `*` with no footnote on the page; dropped from the description and flagged.
- Engine air baffles and exhaust (p15): REQ'D is printed half a row off register. 27 qtys mapped in sequence and flagged inferred.
- Printed ref oddities, kept as printed: hood ref 23 and electrical hardware ref 13 not printed; front axle prints ref 20 twice and no ref 21 (index agrees); repeated refs on pistons, ring sets, push rods, fuel tank brackets, hood, differential and decals; cylinder block refs 28 and 31 both C34616 (index agrees).
- Differential refs 15 and 16 are `NSS*` with the footnote "Discard the needle bearing, sleeve and seals when replacing with C27569 ball bearing". C27569 appears only in those notes.
- Counts: 61 NSS rows, 15 UAR, 3 unnumbered rows (carburetor C34630, starter C40798, headlight assembly C32178), 152 indented rows flagged with their parent.
- Engine: Briggs & Stratton C37031, spec 260777 type 0047 (a speck on the scan sits between the 7s). Briggs BR numbers 221535, 221798 and 270920 are stored bare.

## Section map (all sections apply to model 2012, no serial constraint)

| Section | Printed p | PDF p |
|---|---|---|
| Paint; Oil | unnumbered | 3 |
| Flywheel, crankshaft, camshaft and piston | 5 | 4 |
| Cylinder block, cylinder head and crankcase | 7 | 5 |
| Engine base, dipstick and oil filter; Ignition and charging | 9 | 6 |
| Carburetor | 11 | 7 |
| Air cleaner; Governor | 13 | 8 |
| Engine air baffles and breather; Exhaust system | 15 | 9 |
| Starter; Gasket kit | 17 | 10 |
| Fuel system; Choke and throttle | 19 | 11 |
| Engine mounts | 21 | 12 |
| PTO | 23 | 13 |
| Hood, frame and attaching parts | 25 | 14 |
| Seat and fenders | 27 | 15 |
| Steering gear | 29 | 16 |
| Front axle; Front and rear wheels | 31 | 17 |
| Travel control; Brake assembly | 33 | 18 |
| Belts, pulleys and idlers (drive) | 35 | 19 |
| Lift system | 37 | 20 |
| Transaxle: case, input shaft and brake | 39 | 21 |
| Transaxle: shifter and brake shaft and counter shaft | 41 | 22 |
| Transaxle: differential (**variantBasis transaxle**, 826 / 843) | 43 | 23 |
| Electrical system | 45 | 24 |
| Electrical system hardware; Headlight and rear reflector | 47 | 25 |
| Decals | 49 | 26 |
| M13 weight box | 51 | 27 |

## Commit commands (PowerShell)

```powershell
cd "C:\Users\Admin\Documents\Website\ingersoll-lookup-data"
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\lookup json\8-3220_lookup.json" data\
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\issues\8-3220_issues.md" notes\
git add data notes
git commit -m "Add 8-3220 lookup data"
git push
```

If the files were saved straight into the repo's `data\` and `notes\` folders, the two `Copy-Item` lines fail with "Cannot find path"; that is harmless and the `git` lines still commit them.
