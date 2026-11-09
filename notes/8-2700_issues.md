# 8-2700 issues (lookup-only transcription, 2026-11-09)

Ingersoll Model 108, 110 and 116 Compact Tractors, Parts Catalog 8-2700 (2-84-RP-1500, pages dated January 1984). 37 sections, 809 rows, schema lookup-v1.1. Numerical index: 792 entries, all match in both directions.

## Decisions (user, 2026-11-09)
1. **Per-model serial break (brake assembly, p39):** accepted. Starred rows hold one serial variant per model with a `model` field.
2. **Model variants:** accepted. `basis: model`, `value` "108, 110" plus a `models` array.
3. **"110 XC" alias:** kept (source `inferred`; meaning unknown).
4. **H part numbers** (transaxle: H296277, H392938 and others): stored as printed, closed up (`H296277`), not H0. The store carries no H part numbers. If it ever lists them as H0..., add an H0 ↔ H matching rule instead of changing the data.

## Still open
- Attachment `note` field, and listing both the Case 116 XC set (34"/44" decks) and the Ingersoll 116YT set (38"/42"/44" decks, 38" blade, 38" snowblower) on the 116. Left as delivered until decided.

## Kept as printed, flagged
- Carburetor 110 (p17): ref 27 is not printed. The index has no 17/27 entry either.
- Decals (French) (p55): only refs 8 and 9 (the French versions of the English 8 and 9).
- No qty printed: C27335 gasket kit (p9, unnumbered) and electrical ref 9 C14537 connector (p51).
- 13 rows have no ref number (gasket sets/kits, C27379 carburetor assembly, C26358 cups, C27418/C27264 starter motors, C22571 headlight assembly, C27588 plug).
- Governor 108/110 ref 18 prints "163 4" without the hyphen (index: 163- 4). Stored as 163-4.
- Transaxle ref 8 prints the bare number 35012. Ref 20 prints "LEVEL - brake". Engine 108 ref 26 prints "exhause". The 108 gasket set prints "carbuetor". Engine 110 ref 16 prints "1192-20" (p5 prints 192-20).
- Footnotes differ: the fuel line (p13) says use A21561, the fuel-pump vacuum hose (p19) says A21581. These are probably different hoses. Both kept.

## Handwritten notes on the scan (not part of the print; stored as row flags only)
- p5 ref 1: "includes C27265". p25 ref 20: "(116 only)". p41 ref 1: "C29878 for 86 models".
- p37 wheels: "if equipped with bearing" (ref 2), "C24903 Bushing - if equipped with bushing" (ref 3), "C24429 WHEEL SERVICES BOTH" (ref 5).
- **p45 ref 10: the printed H 392938 is struck through, with "H 372938" written above.** The index prints H 392938, so the printed number is stored. Worth checking which number the store or dealer uses. Also "5/13 37 Teeth" beside ref 11.
- p51: "use C24800" with a bracket from ref 13 (neutral start switch C26108) down to ref 18.

## Settled
- Issue 15: the PDF has two covers. p1 is ignored, and p2 is the cover used.
- Model 116 confirmed in this book (issue 3). Cover windows: 108 14031940+, 110 14032840+, 116 14047500+. Ends are inferred from 8-2992 for the 108 (14065369) and 116 (14066899); the 110 is open-ended.
