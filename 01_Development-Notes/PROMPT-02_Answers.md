1. Correct -- single file for UAF (1.3) BASED ON the provided .csv in PROMPT-02.md
2. CSV only -- I gave NO TSV/Tab data. Also, the CSV is for you to move to the "K.I.S.S." approach for lookups in javascript (I assume the CSVs will become arrays -- I leave it to you); DO NOT have any non-inner-file lookups. Yes to <EMPTY> cells rendering as empty (no label) (i.e., these are placeholdeers for my/human/visual inspection only).
3. use key structures, and "fast look ups" (e.e., array indexing and iteration should be fast...); IF there's a method to compact the code, that is fine -- I would still use the "faster" approach (i.e., arrays are fine, and 4K monitors have LOTS of space to edit! ;)); the default UAF 1.3 name is required (because there are three, other main versions -- the loaded .csv data is 1.3)
4. I give you artisitc license to implement what makes sense in a "data visualiztion" and "Assessment" way -- think like your a Doctoral student...
5. The "editor" is GUI ONLY -- there's TOO MANY cells for a text-based approach. The "layer" so idk where you pulled drag-and-drop and eyes from ... I removed these from the prompt file -- the Up/down are the NEEDED methods to reorder the layers. Theme toggle is in settings --but yes in the settings add and font size controls -- UPDATE PROMPT2 first though!
6. NO ARIA roles, NOR keyboard shortcuts.
7. yes -- I need "everything" in the export -- file name convention: `ARGOS_VERSION-with-DASHES-not-PERIODS_YYYY-MM-DD_HH-MM-SS.json` (e.g., ARGOS_0-1-0_2026-01-15_14-30-00.json)
8. DO NOT test -- I will manually QA
9. grid correctness, Settings menu, Layer Sidebar, Overylay Mode (i.e., the editor), import-export; no on constraints
