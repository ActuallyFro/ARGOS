I want to return to the "BASE MODEL" and "DATA FLOW" construct.

If the GRID is two parts -- the labels and the colors, then the "GRID MODEL" is the unique combo of them. In this case `CSV_LABELS` is the HARDCODED Labels for UAF (the base model supported by ARGOS), and the `CSV_COLORS` is the HARDCODED Colors for UAF. Hence , ARGOS is HARDCODED FOR UAF (which is intended!).

However, I want to add MORE Models, which can be mapped to UAF (i.e., I want to show how other Models/Frameworks map to UAF). Hence, I can simply ignore the colors and grid sizing -- BECAUSE the "new models" will simply use the same colors and grid sizing as UAF -- and just "new labels" will be needed.

Thus, I need a "Model Editor" -- this will enable the user to remix/clone eisting models (i.e., the HARDCODED UAF model with `CSV_LABELS` is immutable -- BUT a user could create a copy). Yet, most importantly, the user can create NEW MODELS by defining new LABELS that map to UAF the GRID. Within the Settings, I want a new section "Model Management" with a button "Open Editor". This will be a Modal, which can go "full screen" that allows the user to create/edit/clone-to-revise new Models. It needs to have a separate "Export/Import" function so that users can share their custom models (e.g., JUST LIKE the OOverlays Editor). However this also means that each cell can be "clicked" to have an editable field for the grid labels. 

Ask all relevant questions before starting the editing of ARGOS.html.