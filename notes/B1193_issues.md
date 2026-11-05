# B1193 (Case 107 / 117) — transcription issues

952 rows, 35 sections, schema lookup-v1.1. Not a bundle; full coverage. Engine C15513 for both models (make not printed, left blank per plan issue 12).

1. **117 serial break (your map's "964800").** The book uses **9646801** as the main break on every page ("use before S/N 9646801" / "use S/N 9646801 and after"). The only other form is **9646800**, printed on the two modification-kit headings: C-16763 kit (117, p31) and C16767 kit (107, p27, ref 27), both "used prior to S/N 9646800". "964800" appears nowhere, so it is a typo for this break (plan issue 1). Stored as printed; the kit rows carry serialTo 9646799, everything else 9646800.
2. **Hood latch (plan issue 13):** checked at full resolution. It prints "use before S/N 9646801"; the "9646804" was an OCR speck.
3. **Inferred serial on p39 (please confirm).** Hydraulic Transmission and Controls (117) appears twice: p41 is headed "use S/N 9646801 and after", and p39 has **no serial note**. I stored p39 as the before-9646801 version, with its serial variant marked `inferred: true`. If you'd rather leave p39 untagged, it's a one-line change.
4. **Table vs numerical index (table kept, flagged):**
   - p47 ref 60 SEAL - oil: the table prints C 10450 and the index prints **G 10450**.
   - p51 breaker refs 9 and 11: the table prints 129- 5 (NUT) and 129- 15 (SCREW). The index lists 129-15 at 51/9 and **C 16056** at 51/11.
   - The index lists all 14 Engine Mounting Plate parts at page 15 as well as page 7. Page 15 is the carburetor, so these are index errors (they also put C16752 at 15/4).
   - Otherwise the index and the tables match in both directions. The cross-check caught three of my misreads, each fixed after a zoom check: breaker ref 2 = **C15906**, differential ref 32 = **F53650**, late electrical ref 12 = **C17807**.
5. **Kept as printed and flagged:**
   - p9: exhaust valve standard and 1/32" oversize both print **C 15824**, and the index agrees, so a separate oversize number is never printed.
   - p25: ref 19 and ref 22 both print 178- 858 (5/16" x 5/16" vs 5/16" x 3/8").
   - p39 ref 10: transmission fan qty **5**.
   - Code/description mismatches: 195- 525 printed as LOCKWASHER (p39 ref 39), 192- 21 as a plain WASHER (p49 ref 15).
   - Short or bare codes: `26- 636`, `92- 4` and a bare `35012` with no prefix. The index prints the same.
6. **Missing or illegible quantities:** fuel ref 27 (scan blot, qty left blank), PTO ref 16 (no REQ'D printed), engine ref 11 (handwritten smudge, read as 1, flagged). The 117 early belts page (p29) prints REQ'D slightly low, so 20 qtys were mapped in sequence and flagged `inferred qty`.
7. **Non-serial variants:**
   - "early / late production" with no serial: steering wheel, hydraulic transmission p41, PTO refs 31-32, battery wire, decal 9. Stored as basis serial with value "early production" / "late production", so the finder shows both.
   - "*" rows not used if the C16767 (107) or C16763 (117) kit is installed: basis `component`.
   - Rows split by model inside shared sections (frame, steering bracket, tool tray, implement lift lever, decals): basis `model`.
8. **Models:** 107 driveType gear (own shift-lever transmission, pp45-47); 117 hydraulic ("117 hydraulic drive" decal, book alias). TractorData attachments were added with verified = false, as in A1227: 107 34" deck, snowblower, blade; 117 34" H-41 deck, 38" blade, 32" snowblower. Delete them if you'd rather wait.
