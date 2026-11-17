# 8-3210 (Ingersoll 2014, hydrostatic) – issues and decisions

Decided 2026-11-17: table values kept on every index-vs-table difference and on gasket sets 17/18; 7/23 stored as C34367. Only the 8-3280 attachment items below are still unanswered. 34 sections, 694 rows, no serial breaks on any table page (checked by eye). Index (633 entries) read in full and compared both ways.

## Index vs table (decided 2026-11-17)
Table value kept and flagged in every case except 7/23 (user confirmed).

| Pos (page/ref) | Table prints | Index prints | Kept |
|---|---|---|---|
| 25/1 hood | C29314 | C29214 | table |
| 37/27 belts | 114- 314 | 114- 214 | table |
| 47/3 elec. hardware | C31597 | 182- 559 | table |
| 47/5 elec. hardware | 131- 934 | C34117 | table |
| 47/18 elec. hardware | 132- 334 | 132- 344 | table |
| 7/23 engine block | C 34262 (duplicate of ref 24) | C34367 | **C34367** (index + Gasket Sets ref 16 + 8-3140 precedent). Confirmed. |
| 17/18 gasket sets | C34279 (index agrees) | C34279 | as printed. C34279 is the screw on pp13/15; 8-3140 uses C34379. Kept as printed (decided). |

Also not in the index: air cleaner 13/16 C29855 and 13/17 C37544 (flagged).

## Other items
- Carburetor: REF column is in register here (no one-row-low shift as in 8-3140); index agrees. The kit note "includes Ref. 5, 23, 28 and 30" does not match this numbering (looks carried over from 8-3140). Kept as printed.
- Refs not printed: hood 23, electrical 14, electrical hardware 13 (index agrees).
- Typos corrected, original in flags: "cylidner" (7/15), "ASSEMLBY" (11/26), "stater" (15/7), "interloc" (45/5). Electrical refs 4 and 5 share C30275 (index agrees).
- Paint ref 3 prints C28851 (8-3140 prints C28850 twice).
- Attachments: M13 weight box added (source book, verified). Live 8-3280 items (RM42Y2, RM44YR2, SB38Y2, UB38Y2, BG42Y2) linked with source book, verified false. "bagger" is not in the schema kind list. Still open: confirm names and verified value.
- 114H kept as separate model with seeAlso; stub points to 8-3140.

## Sibling check vs 8-3140 (same ref + part)
Identical: flywheel, ignition, engine block, crankcase, blower, freewheel, weight box. Near-identical: gasket sets 18/19, hydrostatic 29/30, transaxle 62/63, starter 13/14. Carburetor same parts, refs one lower. Different (real part differences): lift system 0/41, electrical 4/18, front axle 8/23, fuel system 5/9, travel control 9/17, oil filter 10/16, hood 22/33, seat/fenders 10/17. Only in 8-3140: travel_control_locator.

## Commit
```
cd "C:\Users\Admin\Documents\Website\ingersoll-lookup-data"
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\lookup json\8-3210_lookup.json" data\
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\issues\8-3210_issues.md" notes\
git add data notes
git commit -m "Add 8-3210 lookup data"
git push
```
(If the files were saved straight into the repo folders, the two Copy-Item lines fail harmlessly.)
