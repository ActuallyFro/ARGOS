1. The count

2. Because the labels and colors are seperate -- they can name independently/no key reuse -- effectively this app should have static/discrete "arrays" which can have data or not. Also, <EMPTY> is for the CSV -- feel free to ignore it in the code.

3. No schema. No validation. You create the format. The JSON should be the collected objects from the "overlays" to "current settings" -- or basically everything the user can change.

4. Layer order ONLY matters for merging (e.g., heat maps) -- otherwise the topmost visible layer is what shows -- unless it is "toggled off" (e.g., GIMP uses an "open eye" and "closed eye" icon to show visibility). So the order is only relevant when merging is active. YES the this is a "user change" -- so it should be saved in LocalStorage and in the JSON export.

5. The default code, should be the UAF Grid with the default colors and labels. However, a "hide all" button would be useful to see an empty grid for custom overlays -- AND a "search" function to find Overviews by name/description. would be useful. (e.g., they disable all layers, then search for "My Custom Overlay" and enable it).