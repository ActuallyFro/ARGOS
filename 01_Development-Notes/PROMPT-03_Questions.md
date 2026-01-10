Before proceeding, please clarify the following architectural decisions:

State & Storage Structure:

Currently, KEYS.MODELS ('argos_models') seems to store a single model object.
Proposed Change: I will repurpose this to store a Library of Custom Models (an array).
The "UAF 1.3" model will remain hardcoded in JS as the immutable "System Default".
I will add a new setting, e.g., state.settings.activeModelId, to persist which model is currently loaded in the main grid between sessions.
Question: Does this adhere to your vision?
Switching Models:

I plan to add a "Active Model" dropdown in the new "Model Management" section of the Settings drawer.
Changing this dropdown will immediately repaint the Main Grid with the new labels (keeping existing Selection/Overlays intact, as the grid geometry is constant).
Question: Is "Settings Drawer" the right place for switching the active model, or should it be more prominent?
Model Editor Interaction:

The "Model Editor" will be a modal overlay.
Visuals: Should the Editor display the Grid Colors (using UAF colors) to help the user orient themselves, or should it be a plain text grid?
Editing: My plan is that clicking a cell in the Editor turns that div into an <input type="text"> or <textarea> in-place.
Immutability: If the user tries to edit "UAF 1.3", I will force them to "Clone & Edit" instead. Is that acceptable?
Data Scope:

You mentioned "new models will simply use the same colors and grid sizing".
Confirmation: This means I strictly DO NOT need to build UI for adding rows/columns or changing colors in the
Model Editor. The Model Editor is purely a "Label Replacement" tool.

Once you confirm these points, I can begin the refactor.