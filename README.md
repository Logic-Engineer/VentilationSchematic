# Ventilation Schematic Generator (Revit + pyRevit)

This script is a **Ventilation Schematic Generator** for Autodesk Revit, built with the pyRevit framework. It automates the generation of a drafting view that visually represents the vertical distribution of a ventilation network across multiple levels.

---

## 🎯 Purpose

The tool is designed to:

* Trace the **connected network** of ducts and MEP components starting from a selected duct.
* **Filter** only key MEP components: **Air Terminals** and **Mechanical Equipment**, excluding other fittings and accessories.
* Identify **vertical ducts** that span across multiple floors and include only those in the schematic.
* Create a clean and readable **drafting view** with **horizontal level lines** and **vertical duct lines**.
* Annotate the schematic with **element labels** based on the traced network hierarchy.

---

## ✅ Features

* 🚀 **Network Tracing**: Follows MEP connections recursively to determine the system layout.
* 🧹 **Filtered Elements**: Only includes Air Terminals and Mechanical Equipment.
* 🏢 **Floor-Aware**: Filters out ducts that remain on a single level—only multi-level ducts are considered.
* 📐 **Clean Drafting View**:

  * Horizontal lines represent floor levels.
  * Vertical lines represent multi-floor ducts.
  * Avoids diagonal or curved lines to maintain clarity.
* 🗂 **Dynamic Text Notes**: Automatically generates textual annotations using a custom font and size.
* 🧠 **Smart Labeling**: Elements are labeled using a hierarchy-based naming system.

---

## 🏗 Components

* **Element Selection**:

  * Start from a duct.
  * Select Titleblock (to determine sheet size).
  * Choose relevant Levels to visualize.
* **Element Filtering**:

  * Includes only Air Terminals and Mechanical Equipment.
  * Ducts must span multiple levels to be drawn.
* **View Creation**:

  * Drafting view with sheet-aligned coordinates.
  * Draws only vertical and horizontal lines for clarity.
* **Utilities**:

  * Level sorting, connector analysis, hierarchy naming, and room-space lookup for labeling.

---

## 🛠 Technologies Used

* **Autodesk Revit API**
* **pyRevit Framework**
* **.NET Libraries** via `clr`
* **Python 3.x**

---

## 📋 How to Use

1. Load this script through **pyRevit** in Revit.
2. **Select a starting duct** when prompted.
3. **Choose a title block** to define drafting view size.
4. **Pick levels** to include in the schematic.
5. The tool will:

   * Trace the network from the selected duct.
   * Filter and structure the relevant MEP components.
   * Generate a schematic with annotations in a new drafting view.

---

## ⚠️ Constraints

* Ducts must have HVAC connectors.
* Only elements that span **multiple levels** will be visualized.
* Diagonal, curved, or non-horizontal/vertical representations are automatically excluded.
* Script halts if execution exceeds **2 minutes** (`MAX_SEC = 120`).

---

## 📎 Dependencies

* Autodesk Revit (tested with 2021+)
* pyRevit ([https://www.notion.so/pyrevit/pyRevit-Documentation-6bc7f3f3f09b4993a2cfc25d72e2e9f9](https://www.notion.so/pyrevit/pyRevit-Documentation-6bc7f3f3f09b4993a2cfc25d72e2e9f9))
* Python modules: `clr`, `math`, `collections`, `time`

---

## 📌 Notes

* Text annotations use a customized text style: **Cambria, 3.5mm**.
* Sheet height and width are either retrieved from the title block or calculated based on ISO sheet sizes.

---

## 📧 Support

For feature enhancements, bug reports, or help using the script, contact the developer or open a discussion in your internal BIM tools community.

