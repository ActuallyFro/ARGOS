Question 1: For merged overlays and heat maps, should overlap intensity be based purely on the count of overlays covering a cell, or do you expect us to honor metadata (e.g., overlay colors/opacity) when computing the blended visualization?

Question 2: When users add custom-named cells or map other frameworks like DoDAF, do those entries need to reuse existing viewpoint keys (from the CSVs) or can they be entirely free-form with their own identifiers—especially for <EMPTY> cells that have no default label?

Question 3: For import/export, do you already have a preferred JSON schema (beyond name/description/viewpoints/custom cells/metadata) and should we validate files against it, or should we design the schema ourselves and document it as part of the UI?

Question 4: Regarding layer management (drag-and-drop ordering, visibility toggles), should the stack be shown as a list in the sidebar, and does the order need to persist across sessions via localStorage by default?

Question 5: The navigation menu needs theme toggling, clear-storage (confirmation), import/export, and mode switching—are there any specific UX states (e.g., which mode to open by default) or additional actions you want in that hamburger menu before we start building the sprint backlog?
