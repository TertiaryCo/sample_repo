# FOSSEE CFD Grid Tool (Task 2)

A Blender Addon developed for the FOSSEE Screening Task. This tool provides a custom UI panel to generate grid-based cube distributions and merge meshes by removing internal geometry.

**Author:** Shlok  
**Blender Version:** 3.0.0+  
**Category:** Object

---

## Features

1.  **Distribute Cubes**:
    * Generates `N` cubes arranged in a roughly square 2D grid ($m \times n$).
    * Organizes generated cubes into a specific collection (`FOSSEE_Cubes`).
    * **Constraint**: Accepts values up to 20. (Input > 20 triggers an error).
    
2.  **Compose Mesh**:
    * Merges selected meshes into a single object.
    * Automatically cleans up geometry by merging coincident vertices (threshold `0.001`).
    * **Internal Face Removal**: Detects and deletes faces that become internal after merging, creating a single continuous mesh volume.

3.  **Delete Cubes**:
    * Quickly deletes the currently selected objects from the viewport.

---

## Installation

1.  Save the code as a Python file, for example: `fossee_task2_addon.py`.
2.  Open Blender.
3.  Go to **Edit** -> **Preferences**.
4.  Select the **Add-ons** tab on the left sidebar.
5.  Click the **Install...** button at the top right.
6.  Navigate to and select the `blender_addon.py` file.
7.  Click **Install Add-on**.
8.  Enable the addon by checking the box next to **Object: FOSSEE CFD Grid Tool**.

---

## Usage Guide

### 1. Locating the Panel
* In the 3D Viewport, press **`N`** on your keyboard to open the Sidebar.
* Click on the **FOSSEE** tab.
* You will see the panel labeled **Task 2**.

### 2. Generating a Grid
1.  In the "Number of Cubes" input box, enter a number (e.g., `10`).
    * *Note: The number must be 20 or less.*
2.  Click **Distribute Cubes**.
3.  The cubes will appear at the world origin, arranged in a grid.

### 3. Merging Meshes (Compose Mesh)
1.  Select multiple cubes (Shift + Click) that are touching each other.
2.  Click the **Compose Mesh** button.
3.  The selected objects will be joined into one.
4.  Internal faces between touching cubes will be deleted automatically.
    * *Tip: Switch to Wireframe mode (Z -> Wireframe) to verify that internal geometry is gone.*

### 4. Cleaning Up
1.  Select the objects you wish to remove.
2.  Click **Delete Cubes** to remove them from the scene.


## Requirements
* **Blender**: Version 3.0 or higher is recommended.
* **Dependencies**: Uses standard Blender Python API (`bpy`, `bmesh`, `math`). No external pip installation required.