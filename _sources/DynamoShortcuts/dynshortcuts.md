# Workspace view based CTRL key combinations (hold ctrl key and press the additional keys listed):

CTRL + A Select all nodes in workspace.

CTRL + B Switch between geometry preview and workspace.

CTRL + C Copy the selected node(s), note(s), group(s).

CTRL + D Creates new custom node from the selected node(s), note(s), group(s).

CTRL + G Groups the current selection (if possible).

CTRL + I Enables Isolation mode, which fades geometry associated to nodes which are not selected.

CTRL + L Clean up node layout, which adjusts node locations to produce a more readable graph.

CTRL + N Creates a new graph.

CTRL + SHIFT + N Creates a new custom node.

CTRL + O Open an existing graph.

CTRL + P Toggle ‘Pan’ mode.

CTRL + S Save the active file (dyn or dyf).

CTRL + SHIFT + S Save the active file (dyn or dyf) as a new file.

CTRL + V Paste nodes from clipboard.

CTRL + W Create note.

CTRL + Y Redo a previously undone action.

CTRL + Z Undo an action.

CTRL + 0 Zoom extents if nothing selected, Zoom to origin if already at extents, Zoom to selection if node(s), note(s) or group(s) are selected.

­­­­CTRL + - (not number pad) Zoom out.

CTRL + = Zoom in.

CTRL + SHIFT + UPARROW Toggle console.
# Workspace view single key shortcuts:

Esc (hold) Toggle to geometry preview – will revert to workspace view once released.

Tab Add nodes connected to current selection to selection (select nodes at end of highlighted wires).

F5 Run the graph (when in manual execution mode.

Delete Removes the selected node(s) from the workspace.

F1 Displays the node help documentation for the last selected node in the workspace.
# Workspace Mouse Interaction:

Left click Select node.

Double left click Create new code block.

Right click node body Node context menu.

Right click node input Port context menu.

Right click group Group context window.

Right click background and type Quick access library search.

Right click background Workspace context window.

Right click note Note context window.

Middle Mouse click and drag Pan workspace.

Middle Mouse Scroll Zoom in/out.

Shift + Left Mouse + drag on connected out port Grab all wires and remove from node. Release on other out port to reattach. Release on background to remove wires from graph.

CTRL + Left Mouse on connected input Duplicate connector mode. Connect to as many ports as desired. Release ctrl and click to cancel additional connector creation.

Shift + Left Mouse on node body Add to selection.

Left Mouse drag to create a box from left to right Select node(s), note(s), groups which are completely contained inside the box. Note solid box lines.

Left Mouse drag to create a box from right to left Select node(s), note(s), group(s) which are inside or partially inside the box. Note dashed box lines.
# Geometry Preview CTRL key combinations (hold ctrl key and press the additional keys listed):

CTRL + A Select all nodes in the workspace and allow direct geometry manipulation as applicable to the elements in the display.

CTRL + B Toggle to workspace view.

CTRL + C Copy selected geometry.

CTRL + D Creates new custom node from the node which creates the selected geometry(s). Exactly what is included in the custom node can expand beyond the specific nodes – best to be careful when using this with a selection from the geometry preview windows.

CTRL + E Sets zoom to the default distance and re-centers camera.

CTRL + G Group the nodes which create the selected geometry in the workspace.

CTRL + I Enables Isolation mode, which fades geometry associated to nodes which are not selected.

CTRL + L Clean up node layout, which adjusts node locations to produce a more readable graph.

CTRL + N Creates a new graph.

CTRL + SHIFT + N Creates a new custom node.

CTRL + O Open an existing graph.

CTRL + S Save the active file (dyn or dyf).

CTRL + SHIFT + S Save the active file (dyn or dyf) as a new file.

CTRL + V Paste nodes from clipboard.

CTRL + W Create note in the workspace. These can be hard to find, so careful with them.

CTRL + X Cut selected node(s), note(s), group(s).

CTRL + Y Redo a previously undone action.

CTRL + Z Undo an action.

CTRL + 0 Zoom extents if nothing selected. Zoom to selected geometry if any is selected.

­­­­CTRL + - (not number pad) Zoom out from pivot point.

CTRL + = Zoom in towards pivot point.

CTRL + SHIFT + UPARROW Toggle console.
# Geometry Preview single key shortcuts:

Delete Removes the selected node(s) from the workspace.
# Deprecated Keyboard Shortcuts:

CTRL + T Opens the presets window (deprecated and not serialized into the file as of 2.0, but still accessible via shortcut in 2.1). Requires a node capable of having a preset be selected in order to avoid an error message, so it’s unlikely you’ll manage this with selection from the geometry side without use of CTRL + A or TAB keyboard shortcuts.
## Document
https://github.com/DynamoDS/Dynamo/wiki/Dynamo-Keyboard-Shortcuts