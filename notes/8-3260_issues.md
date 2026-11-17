# 8-3260 issues list (Ingersoll 1212G and 1212H, July 1992)

File: `8-3260_lookup.json` (schema `lookup-v1.1`), 26 sections, 786 rows. Transcribed 2026-11-17. All index-versus-table items below were decided by the user the same day.

## Book facts
- Cover: "Compact Tractors 1212G, 1212H, Parts Catalog 8-3260", 7-92-RP-500-217; footers "8-3260-NN July 1992". Not a bundle; no pages shared with another book in the set. Scan, no text layer, 24 PDF pages.
- No ID/serial table and no S/N notes anywhere: both models match all serials. Variants split by model: 1212G-only transaxle and gear shift (printed pp11, 33); 1212H-only motion drive, transaxle, hydrostatic pump (pp13, 29, 31). Sections that carry both models' parts (fender p7, clutch p15, decals p27) use `variantBasis: model` with per-row `models[]`.
- Engine C37477 "12 HP B&S I/C 283707 type 0126" for both models. Attachment: the book's own 40" deck (C42123, blades C42132), `source: book`, `verified: true`. Side or rear discharge is not printed and not recorded. No TractorData attachments are on file for the 1212G/1212H.
- Paint (7 rows) and oil (3 rows) are printed on the cover spread without a page number (stored as sections `paint` and `oil`, page "cover"); they are not in the numerical index.

## Index versus table (decided by the user)
- Index value used: transaxle 1212G ref 18 SPACER, table prints C24496, index prints C34496 (33/18): stored `C34496`, printed form and note in the flags.
- Table value kept, index differs (flagged): starter 5 C27258 (index C37259, 43/5); spindle 5 C35303 (index C34303, 23/5); chassis 18 FRAME - main C39506 (index C39056, 5/18); mower suspension 9 and 19 C29620 (index C39620 at 9/9 and 9/19); electrical 36 WASHER 195-518 (index lists 195-518 at 25/33, but ref 33 is the 113-3 bolt).
- Not in the index, kept as printed: fuel bowl C40877 (39/27); carburetor kits C40870 and C40878; C40894 (motion drive, no ref); C40895 and C35411 on the pump page (no refs, "not shown"; C35411 is indexed at 13/14).
- Every other entry matches in both directions (718 index entries read by eye).

## Kept as printed + flagged
- Mower suspension (p9) is headed "Lawn Tractors Model 1112G and 1212H" (misprint): kept in `headingAsPrinted`, section applies to 1212G and 1212H.
- Motion drive ref 2 prints `C 35405*` with no footnote text on p13 (the transaxle 1212G ref 1 footnote "*See Transaxle Section for Service Parts" is on p11). Marks removed from `partNo`, kept in `partNoAsPrinted`.
- `*` and `**` part cells (clutch 24 and 27, steering 31 and 32) stored as NSS with the footnote text in the flags. Steering ref 32 and its three unnumbered sub-items (valve stem C34920, wheel C35193, bearing C35404) are flagged as indented under ref 31.
- The motion drive (p13) and pump (p31) both list a "DIAPHRAGM - reservoir (not shown)": C40894 on p13 and C40895 on p31, neither indexed. They may be one part with a misprint; not decided, both kept.
- Printed ref gaps: transaxle 1212H 11, 50, 62; transaxle 1212G 16, 19, 24, 63; flywheel 2, 6. Repeated refs are the printed model/option rows (fender 18, decals 4/5/10/14/16, electrical 9, steering 34 and 35, transaxle 28/49/53A, engine block 9/18/19/21/22, starter 1/2/5/7).
- 12 unnumbered rows stored as ref 0 (pump page, steering tire sub-items, engine gasket set, carburetor kits, motion drive diaphragm, transaxle assembly C40675); 56 rows flagged as indented under a parent ref or kit.
- No qty printed: clutch refs 25 (VALVE - air) and 27 (TIRE **), carburetor kits C40870 and C40878. 9 UAR rows. No REQ'D column is out of register.
- Hardware `11- 312` (governor ref 6) stored `11-312` (the index prints a leading zero). Air cleaner refs 2, 3, 8, 11 print O/L (obtain locally): stored as `O/L`, no source.
- Typos corrected under the standing rule, printed form in each row's flags: ASESMLBY (engine block 18), "resister" (flywheel 18, now "resistor"), "inlcudes" (engine block 13), "dowl" (transaxle 1212H 60, now "dowel"). Tell me if you want any of these left as printed.
- Part numbers named only in notes (not rows): C35497, C34482, C28937, 113-102, 92-5, 113-120, 192-20, 163-18, 192-18.

## Not done
- Sibling comparison against the committed 8-3160, 8-3170 and 8-3270 data was not possible: `8-3270_lookup.json` was not among the uploads (only the PDF and `A1226_lookup.json` arrived), and the other committed files are not in this session. Conventions for stubs, NSS rows, indented rows and index-sourced corrections were taken from the plan doc's 8-3270 row. If a convention differs, send the file and I will adjust.

## Commit commands (PowerShell)
```powershell
cd "C:\Users\Admin\Documents\Website\ingersoll-lookup-data"
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\lookup json\8-3260_lookup.json" data\
Copy-Item "C:\Users\Admin\Documents\Website\Interactive Parts Catalogs\Lookup Data\issues\8-3260_issues.md" notes\
git add data notes
git commit -m "Add 8-3260 lookup data"
git push
```
