1) Scope & project structure 🧭
Confirm: v1.0.0 should only implement UAF (per PROMPT-02.md), correct?
Confirm: you want a single-file app (ARGOS.html) with inline CSS/JS and no external libraries, correct?
Overwrite or preserve? Should I overwrite the current ARGOS.html or create a new file like ARGOS.v2.html (or keep backups)?
2) Data files & parsing 📄
CSV formats: PROMPT-02 shows comma-separated labels and comma-separated colors; current code used tab-separated colors in places. Should I:
Accept both commas and tabs gracefully for color CSVs? (recommended)
Fallback behavior: Should the app try to fetch 00_Resources/UAF-GRID-*.csv at runtime and fall back to embedded defaults if not found? (current behavior exists)
<EMPTY> handling: Confirm <EMPTY> cells must render as empty (no label) — agreed?
3) Storage & data model 💾
Storage keys: PROMPT-02 proposes split keys (argos_models, argos_overlays, etc.). Do you want to:
Adopt the PROMPT-02 key structure, or
Keep a single argos:state object (current approach)?
Overlay cell representation: prefer
Array-of-row-arrays (2D binary matrix) per PROMPT, or
List of cell coordinates {row,col} for compactness (current code)?
Default overlay name: do you prefer "UAF-1.3" or "UAF Standard View" (or other)?
4) Overlays & merge modes 🎛️
Merge modes to implement for v1.0: none (last-wins), union (heatmap), intersect — confirm all three should be included now?
Heatmap colors: Use the HEAT_MAP_COLORS from PROMPT-02 (1..4+) — confirm?
Label behavior:
For union heatmap: should cell label list show comma-separated overlay names (or show overlay count only)?
For none: last overlay (top of layer order) wins — confirm.
5) UI & UX decisions 🎨
Keep the Editor GUI-first flow (click to select cells, then Save Selection creates overlay)? (current behavior)
Layers drawer: keep it on the right, include drag-and-drop, eye toggles — do you also want explicit up/down buttons for accessibility?
Theme & font: keep light default, provide theme toggle and font size controls persisted to storage — OK?
6) Accessibility & keyboard ♿
Priority: Should I implement keyboard reordering (e.g., focus + Alt+Up/Alt+Down or buttons) and ARIA roles now, or is that lower priority?
Any specific accessibility standards to meet (WCAG level target)?
7) Import/Export & format 🔁
Export payload: prefer full state JSON or only overlays + layer order? (PROMPT suggests overlays + layer order)
File naming for export: default argos-state.json OK?
8) Testing, QA & targets 🧪
Browser targets: any browsers to prioritize (Chrome, Firefox, Edge)?
Do you want a small automated test harness (e.g., a test HTML that verifies parse output) or mainly manual QA?
9) Timeline & priorities ⏱️
What is highest priority for v1.0 (pick top 3): grid correctness, overlay merging/heatmap, persistence/import-export, accessibility, keyboard shortcuts, layer ordering?
Are there any hard constraints (release date / demo)?