# Argos Development Prompt

## Project Overview
Create a single-page application (SPA) called **Argos** (Architecture Repository for Governance and Operational Standards) that visualizes and manages architectural frameworks based on the OMG Unified Architecture Framework (UAF).

## Core Concept
Argos displays a grid matrix where:
- **Y-axis**: Represents various architectural domains
- **X-axis**: Represents different model kinds/types
- **Cells**: Represent specific viewpoints at domain/model intersections

## Key Features & Requirements

### 0. Default UAF Grid Labels and Colors
- The base grid must use the standard UAF domain and model kind labels (i.e., a static <X,Y> or <13, 12> grid).
- Each cell must be color-coded according to the UAF Grid Colors specification.
- Both the GRID Labels and COLORS are defined in this repository in the file: ` 00_Resources/UAF-GRID-LABELS.csv` and ` 00_Resources/UAF-GRID-COLORS.csv`.

### 1. Grid Visualization
- Render the complete UAF grid showing all possible viewpoints (i.e., the full matrix of domain/model kind intersection -- with labels and colors)
- Grid colors should be visible at all times as the base layer
- Apply appropriate color coding to cells based on UAF standards
- Grid should be responsive and clearly labeled

### 2. Overlay System
- **Default Overlay**: Show all UAF viewpoints
- **Custom Overlays**: Users can create named overlays containing selected subsets of viewpoints
- Overlays contain word-wrapped text labels that render on top of the grid cells
- Support for mapping alternative frameworks (e.g., DoDAF) to UAF viewpoints in custom overlays
- Layer-based approach with drag-and-drop reordering capability

### 3. Two Primary Modes

#### Mode A: Viewer/Tab Mode
- Display the grid with selected overlay(s) applied
- Navigate between different saved overlays
- View merged overlays with heat map visualization

#### Mode B: Editor Mode
- GUI selection interface to click and select specific viewpoints
- Save selected viewpoints as named custom overlays
- Add custom-named cells to new overlays for framework comparison
- Edit existing overlay definitions

### 4. Layer Merging Capability
- Support multiple overlay selection simultaneously
- Implement merge modes similar to Photoshop/GIMP (add/subtract)
- Generate heat maps showing commonalities across overlays
- Smart text label merging for cells present in multiple overlays
- Visual indication of overlap intensity

### 5. Data Persistence & Portability
- Store user-created overlays in browser localStorage
- Auto-load saved overlays on page refresh
- **Import**: Load overlay definitions from JSON files
- **Export**: Save overlay definitions as JSON files for sharing
- Clear localStorage option to reset user data

### 6. UI/UX Requirements

#### Navigation
- Hamburger menu (three-bar icon) for main navigation
- Clean, intuitive interface for both modes

#### Menu Options
- Toggle between light mode and dark mode
- Clear local storage (with confirmation)
- Import overlay data
- Export overlay data
- Switch between Viewer and Editor modes

#### Visual Design
- Modern, clean aesthetic
- Proper contrast for readability in both themes
- Color-coded cells following UAF conventions
- Clear visual hierarchy

## Technical Specifications

### Technology Stack
- Pure HTML/CSS/JavaScript (or specify your preferred framework)
- No backend required - fully client-side
- LocalStorage for persistence
- JSON format for import/export

### Data Structure Considerations
- Grid definition (domains × model kinds)
- Overlay objects containing:
  - Name
  - Description
  - Selected viewpoint array
  - Custom cell definitions
  - Color/styling metadata
- Layer stack order
- Merge mode settings

### Responsive Design
- Must work on desktop browsers (primary target)
- Grid should scale appropriately
- Mobile-friendly navigation

## Development Approach

### Phase 1: Core Grid
- Implement base UAF grid structure
- Basic rendering with proper labels
- Default color coding

### Phase 2: Overlay Foundation
- Overlay data structure
- Basic overlay switching
- localStorage integration

### Phase 3: Editor Mode
- Click-to-select interface
- Save/name overlay functionality
- Custom cell creation

### Phase 4: Layer Management
- Drag-and-drop layer reordering
- Multiple overlay display
- Layer visibility toggles

### Phase 5: Merging & Heat Maps
- Merge mode implementation
- Heat map visualization
- Label merging logic

### Phase 6: Polish & Features
- Import/export functionality
- Theme switching
- Menu system
- Clear storage option

## Success Criteria
- Grid renders correctly with all UAF viewpoints
- Users can create and save custom overlays
- Layer system allows flexible comparison of frameworks
- Heat maps effectively show commonalities
- Data persists across sessions
- Import/export enables collaboration
- Both light and dark modes are fully functional

## Notes for AI Agents
- Prioritize clean, maintainable code
- Comment complex logic, especially layer merging
- Ensure localStorage doesn't exceed browser limits
- Handle edge cases (empty overlays, corrupted imports)
- Maintain grid visibility regardless of overlay complexity
- Test with multiple overlays to ensure performance

---

Use this specification to guide incremental development sprints, building from the foundation upward while ensuring each feature integrates cleanly with existing functionality.