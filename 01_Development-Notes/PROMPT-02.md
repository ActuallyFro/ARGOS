

# Argos SPA - (Towards V1.0.0) Precise Implementation Specification
It's assumed that "all Architecture Frameworks" can be placed into an NxM grid structure. The X and Y axes would map domains/views/etc., which the cells represent the model kinds/artifacts/diagrams/etc.
Hence, the "DATA FLOW" is: [MODEL FRAMEWORK] --> [MODEL MAPPING and RENDERING] (i.e., this splits between COLORS and LABELS for each cell in the grid) --> [OVERLAYS] (i.e., the full set or a subset of the LABELS -- the grid never "shrinks" for a given framework, BUT "rendering cell labels" is dynamic based on those selected for a given overlay).

The data structure for ARGOS, should consider this "DATA FLOW", and be flexible enough to allow for future frameworks to be added (beyond UAF). Inmediate impact: there needs to be an association with a MODEL FRAMEWORK to a specific grid (e.g., N x M dimensions, related/joined cells, and the MODEL MAPPING and RENDERING). This could be seen as a "drop down" or "selectable Framework" of which framework to render -- BUT v1.0.0 will only implement UAF.

## Reference Data Files
The following CSV files must be used as the source of truth for grid structure:

### File 1: `model-uaf_grid_labels.csv`
```csv
Domain (Y-Axis)\Model Kinds (X-Axis),Motivation (Mv),Taxonomy (Tx),Structure (Sr),Connectivity (Cn),Processes (Pr),States (St),Sequences (Sq),Information (If),Parameters (Pm),Constraints (Ct),Roadmap (Rm),Traceability (Tr)
Architecture Management (Am),Architecture Principles (Am-Mv),Architecture Extensions (Am-Tx),Architecture Views (Am-Sr),Architecture References (Am-Cn),Architecture Development Method (Am-Pr),Architecture Status (Am-St),<EMPTY>,Dictionary (Am-If),Architecture Parameters (Am-Pm),Architecture Constraints (Am-Ct),Architecture Roadmap (Am-Rm),Architecture Traceability (Am-Tr)
Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov),Summary & Overview (Sm-Ov)
Strategic (St),Strategic Motivation (St-Mv),Strategic Taxonomy (St-Tx),Strategic Structure (St-Sr),Strategic Connectivity (St-Cn),Strategic Processes (St-Pr),Strategic States (St-St),<EMPTY>,Strategic Information (St-If),Environment / Measurements / Risks (En-Pm-E / Me-Pm-M / Rk-Pm-R),Strategic Constraints (St-Ct),Strategic Deployment / Strategic Phasing (St-Rm-D / St-Rm-P),Strategic Traceability (St-Tr)
Operational (Op),Requirements (Rq-Mv),Operational Taxonomy (Op-Tx),Operational Structure (Op-Sr),Operational Connectivity (Op-Cn),Operational Processes (Op-Pr),Operational States (Op-St),Operational Sequences (Op-Sq),Operational Information (Op-If),Environment / Measurements / Risks (En-Pm-E / Me-Pm-M / Rk-Pm-R),Operational Constraints (Op-Ct),<EMPTY>,Operational Traceability (Op-Tr)
Services (Sv),Requirements (Rq-Mv),Services Taxonomy (Sv-Tx),Services Structure (Sv-Sr),Services Connectivity (Sv-Cn),Services Processes (Sv-Pr),Services States (Sv-St),Services Sequences (Sv-Sq),Operational Information (Op-If),Environment / Measurements / Risks (En-Pm-E / Me-Pm-M / Rk-Pm-R),Services Constraints (Sv-Ct),Services Roadmap (Sv-Rm),Services Traceability (Sv-Tr)
Personnel (Ps),Requirements (Rq-Mv),Personnel Taxonomy (Ps-Tx),Personnel Structure (Ps-Sr),Personnel Connectivity (Ps-Cn),Personnel Processes (Ps-Pr),Personnel States (Ps-St),Personnel Sequences (Ps-Sq),Resources Information (Rs-If),Environment / Measurements / Risks (En-Pm-E / Me-Pm-M / Rk-Pm-R),Competence / Drivers / Performance (Ps-Ct),Personnel Availability / Personnel Evolution / Personnel Forecast (Ps-Rm-A / Ps-Rm-E / Ps-Rm-F),Personnel Traceability (Ps-Tr)
Resources (Rs),Requirements (Rq-Mv),Resources Taxonomy (Rs-Tx),Resources Structure (Rs-Sr),Resources Connectivity (Rs-Cn),Resources Processes (Rs-Pr),Resources States (Rs-St),Resources Sequences (Rs-Sq),Resources Information (Rs-If),Environment / Measurements / Risks (En-Pm-E / Me-Pm-M / Rk-Pm-R),Resources Constraints (Rs-Ct),Resources Evolution / Forecast (Rs-Rm-E / Rs-Rm-F),Resources Traceability (Rs-Tr)
Security (Sc),Security Controls (Sc-Mv),Security Taxonomy (Sc-Tx),Security Structure (Sc-Sr),Security Connectivity (Sc-Cn),Security Processes (Sc-Pr),<EMPTY>,<EMPTY>,Resources Information (Rs-If),Environment / Measurements / Risks (En-Pm-E / Me-Pm-M / Rk-Pm-R),Security Constraints (Sc-Ct),<EMPTY>,Security Traceability (Sc-Tr)
Projects (Pj),<EMPTY>,Projects Taxonomy (Pj-Tx),Projects Structure (Pj-Sr),Projects Connectivity (Pj-Cn),Projects Processes (Pj-Pr),<EMPTY>,<EMPTY>,<EMPTY>,Environment / Measurements / Risks (En-Pm-E / Me-Pm-M / Rk-Pm-R),<EMPTY>,Projects Roadmap (Pj-Rm),Projects Traceability (Pj-Tr)
Standards (Sd),<EMPTY>,Standards Taxonomy (Sd-Tx),Standards Structure (Sd-Sr),<EMPTY>,<EMPTY>,<EMPTY>,<EMPTY>,<EMPTY>,<EMPTY>,<EMPTY>,Standards Roadmap (Sd-Rm),Standards Traceability (Sd-Tr)
Actual Resources (Ar),<EMPTY>,<EMPTY>,Actual Resources Structure (Ar-Sr),Actual Resources Connectivity (Ar-Cn),Simulation,Simulation,Simulation,<EMPTY>,<EMPTY>,Parametric Execution/Evaluation,<EMPTY>,<EMPTY>
```

### File 2: `model-uaf_grid_colors.csv`
```csv
#FFFFFF,#000000,#000000,#000000,#000000,#000000,#000000,#000000,#000000,#000000,#000000,#000000,#000000
#FFFFCC,#FFFFCC,#FFFFCC,#FFFFCC,#FFFFCC,#FFFFCC,#FFFFCC,#000000,#FFFFCC,#FFFFCC,#FFFFCC,#FFFFCC,#FFFFCC
#595959,#595959,#595959,#595959,#595959,#595959,#595959,#595959,#595959,#0070C0,#595959,#595959,#595959
#D7E4BD,#D7E4BD,#D7E4BD,#D7E4BD,#D7E4BD,#D7E4BD,#D7E4BD,#000000,#D7E4BD,#0070C0,#D7E4BD,#D7E4BD,#D7E4BD
#8EB4E3,#7F7F7F,#8EB4E3,#8EB4E3,#8EB4E3,#8EB4E3,#8EB4E3,#8EB4E3,#BFBFBF,#0070C0,#8EB4E3,#000000,#8EB4E3
#E6B9B8,#7F7F7F,#E6B9B8,#E6B9B8,#E6B9B8,#E6B9B8,#E6B9B8,#E6B9B8,#BFBFBF,#0070C0,#E6B9B8,#E6B9B8,#E6B9B8
#FFFFFF,#7F7F7F,#FFFFFF,#FFFFFF,#FFFFFF,#FFFFFF,#FFFFFF,#FFFFFF,#BFBFBF,#0070C0,#FFFFFF,#FFFFFF,#FFFFFF
#FCD5B5,#7F7F7F,#FCD5B5,#FCD5B5,#FCD5B5,#FCD5B5,#FCD5B5,#FCD5B5,#BFBFBF,#0070C0,#FCD5B5,#FCD5B5,#FCD5B5
#B7DEE8,#B7DEE8,#B7DEE8,#B7DEE8,#B7DEE8,#B7DEE8,#000000,#000000,#BFBFBF,#0070C0,#B7DEE8,#000000,#B7DEE8
#CCC1DA,#000000,#CCC1DA,#CCC1DA,#CCC1DA,#CCC1DA,#000000,#000000,#000000,#0070C0,#000000,#CCC1DA,#CCC1DA
#C4BD97,#000000,#C4BD97,#C4BD97,#000000,#000000,#000000,#000000,#000000,#000000,#000000,#C4BD97,#C4BD97
#595959,#000000,#000000,#595959,#595959,#595959,#595959,#595959,#000000,#000000,#595959,#000000,#000000
```

### Data Files Notes
1. Row 1 of labels CSV = Header row (Model Kinds on X-axis)
2. Column 1 of labels CSV = Domain names (Y-axis)
3. `<EMPTY>` cells should render as empty (i.e., NO string labels)
4. Colors CSV has same dimensions as labels CSV (13 columns × 12 rows including header)
5. Color row index matches label row index exactly
6. Color column index matches label column index exactly

## Default Overlay Definition

### UAF 1.3 (Default Complete Framework)
This overlay includes ALL non-empty, non-disabled cells from the grid.

### Example "array" of UAF's active cells for UAF 1.3 Overlay
```csv
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
1,1,1,1,1,1,1,1,1,1,1,1,1
```

## Layout Examples

### Top Bar (fixed)
```
┌─────────────────────────────────────────────────────────┐
│ [Argos Logo/Title]          [{Display || Overlays} ] [≡]│
└─────────────────────────────────────────────────────────┘
```

### Main Grid Area
```
┌─────────────────────────────────────────────────────────┐
│ [Argos Logo/Title]         [{*Display || Overlays} ] [≡]│
└─────────────────────────────────────────────────────────┘
│                                                         │
│            [Grid Renders Here in DISPLAY]               │
│                                                        <│ (Hiddden Right Sidebar for Layers -- Icon to toggle open/close) 
│                                                         │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Main Grid Area
```
┌─────────────────────────────────────────────────────────┐
│ [Argos Logo/Title]         [{Display || *Overlays} ] [≡]│
└─────────────────────────────────────────────────────────┘
│                                                         │
│        [Editor HUD Additions when in Overlays]          │
│                                                        <│ (Hiddden Right Sidebar for Layers -- Icon to toggle open/close) 
│                                                         │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Right Sidebar - Layer Panel (hidden by default)
```
┌────────────────────────┐
│ [MODEL FRAMEWORK][v]   │ (e.g., UAF, DoDAF, TOGAF, etc. -- v1.0.0 ONLY has UAF)
│ Layers                 │
│ ────────────────────── │
│ □ UAF-1.3  [ ][v]      │ (enable/disable checkbox, Overlay Name, and up/down clickable buttons to reorder)
│ ☑ Minimal [^][v]      │
│ □ Custom-1 [^][ ]      │
│ ───────────────────── >│ (When the sidebar is open, this Icon would hide the sidebar)
│ Merge Mode:            │
│ ◉ None                 │
│ ○ Add (Union)          │
│ ○ Intersect            │
│ ────────────────────── │
│ [+ New Overlay]        │ (Swaps from the "Display Mode" to "Overlays Mode")
└────────────────────────┘
```

### Hamburger Menu (overlay from right)
```
┌──────────────────────────┐
│ Settings                 |
│ ─────────────────────────│
│ ⚙ Preferences            │
│ □ Dark Mode              │ (toggle switch prefered)
│ ──────────────────────── │
│ 📁 Data Management       │
│ 📥 Import JSON           │
│ 📤 Export JSON           │
│ 🗑 Clear Storage          │
│ ──────────────────────── │
│ ℹ About                  │
│ Version 0.1.0            │
│ ──────────────────────── │
│ [Close]                  │
└──────────────────────────┘
```

## Exact Color Specifications

### Theme Colors
```javascript
const COLORS = {
  darkmode: {
    background: '#121212',
    surface: '#1a1a1a',
    surfaceVariant: '#252525',
    border: '#333333',
    text: '#e0e0e0',
    textSecondary: '#a0a0a0',
    gridCell: '#1e1e1e',
    gridBorder: '#444444'
  },
  lightmode: {
    background: '#fafafa',
    surface: '#ffffff',
    surfaceVariant: '#f5f5f5',
    border: '#dddddd',
    text: '#212121',
    textSecondary: '#757575',
    gridCell: '#ffffff',
    gridBorder: '#cccccc'
  }
};
```

### Cell Heat Map Colors (for merge mode)
```javascript
const HEAT_MAP_COLORS = {
  1: '#4A90E2', // Single overlay
  2: '#FFB347', // Two overlays
  3: '#FF6B6B', // Three overlays
  4: '#C44569' // Four+ overlays
};
```

## Data Structures

### Example LocalStorage Keys
```javascript
const STORAGE_KEYS = {
  models: 'argos_models',
  overlays: 'argos_overlays',
  activeOverlays: ['overlay-id-1', 'overlay-id-2'],
  isMenuLayerOpen: 'argos_is_menu_layer_open',
  theme: 'dark' | 'light',
  activeMode: 'display' | 'overlay',
  mergeMode: 'none' | 'add' | 'intersect'
};
```

### Model Object Structure
```javascript
{
  id: 'string', // UUID
  name: 'string', // Display name
  description: 'string', // Optional description
  modelFramework: 'UAF' | 'DoDAF' | 'TOGAF' | ..., // Framework type
  gridDimensions: { rows: 12, columns: 13 }, // Dimensions of the grid
  version: 'string', // Version of the model
  gridLabels: [ // 2D Array of labels from CSV
    ['Domain (Y-Axis)\\Model Kinds (X-Axis)', 'Motivation (Mv)', 'Taxonomy (Tx)', 'Structure (Sr)', 'Connectivity (Cn)', 'Processes (Pr)', 'States (St)', 'Sequences (Sq)', 'Information (If)', 'Parameters (Pm)', 'Constraints (Ct)', 'Roadmap (Rm)', 'Traceability (Tr)'],
    ['Architecture Management (Am)', 'Architecture Principles (Am-Mv)', 'Architecture Extensions (Am-Tx)', 'Architecture Views (Am-Sr)', 'Architecture References (Am-Cn)', 'Architecture Development Method (Am-Pr)', 'Architecture Status (Am-St)', '<EMPTY>', 'Dictionary (Am-If)', 'Architecture Parameters (Am-Pm)', 'Architecture Constraints (Am-Ct)', 'Architecture Roadmap (Am-Rm)'],
    ...
  ],
  gridColors: [ // 2D Array of colors from CSV
    ['#FFFFFF', '#000000', ...],
    ['#FFFFCC', '#000000', ...],
    ...
  ],
  gridCellDescriptions: [ // 2D Array of descriptions (optional, can be empty strings)
    ['', '', ...],
    ['', '', ...],
    ...
  ],
  created: 'ISO date',
  modified: 'ISO date'
}
```

### Overlay Object Structure
```javascript
{
  id: 'string', // UUID
  name: 'string', // Display name
  description: 'string', // Optional description
  modelFramework: 'UAF' | 'DoDAF' | 'TOGAF' | ..., // Framework type
  version: 'string', // Version of the overlay
  cells: [ // Array of active cells -- as 1/0 or true/false
    [1,0,1,0,...], // Row 1
    [0,1,1,1,...], // Row 2
    ...
  ],
  created: 'ISO date',
  modified: 'ISO date'
}
```

## Behavior Specifications

### Display Mode
1. Grid displays with all cells visible with colors
2. Active overlay cells shown with labels
3. If merge mode active:
   - Calculate overlap count per cell
   - Apply heat map color based on count
   - Show all labels comma-separated in cell
4. Click on cell: show tooltip with full details
5. Layer panel accessible (reveal and hide) with right side-of-screen icons

### Overlay Mode
0. When in overlay mode -- the intent is to allow toggling on/off a subset of grid labels -- the "editing" of a overlay is based on the Drop-Down selection of both the MODEL FRAMEWORK (e.g., UAF) and the specific OVERLAY to edit (e.g., UAF-1.3, Minimal, Custom-1, etc.) (these autofilter/etc.)
1. Include a [Select All] | [Clear All] set of buttons to quickly select/deselect all cells
2. Click cell to toggle selection (border: 3px solid #4A90E2)
3. Selected cells highlighted with blue outline
4. Top-right shows: [Save as Overlay] button
5. Clicking "Save as Overlay" prompts for name, then saves to localStorage -- and html form enables adding applicable object variables
6. Delete button: remove overlay from localStorage (confirm dialog)
7. Layer panel hidden in Overlays mode

### Display Mode: Layer Panel Interactions
- Checkboxes: toggle overlay active/inactive
- IF there is no selected overlays then ONLY the grid with default colors and NO labels is shown
- Up/Down buttons: reorder layers (affects z-index rendering)
- New Overlay button: switches to Overlays mode

### Merge Modes
- **None**: Show all active overlays, last one wins for overlapping cells
- **Add (Union)**: Show union of all cells, heat map based on overlap count
- **Intersect**: Show only cells present in ALL active overlays

## Implementation Steps

## File Structure
```
./
├── index.html (ALL CODE, html/css/js in one file)
└── README.md
```
