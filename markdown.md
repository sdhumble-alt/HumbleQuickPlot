# A Humble Quick Plot

A lightweight, interactive client-side graph builder designed for students to rapidly create, customize, and export math and science charts.

**Author:** Steven Humble  
**Version:** v1.4.0  
**Build Date:** 09-24-2026  
**License:** Free for educational use

---

## 1. Overview

**A Humble Quick Plot** is an interactive, single-file HTML5 Canvas graphing application. It simplifies graph generation for educational assignments by providing an intuitive graphical interface for plotting data directly onto a canvas, managing multiple series, formatting mathematical typography, calculating linear regressions, and exporting high-resolution images.

---

## 2. Key Features

### 📊 Graph Types
* **Bar Chart:** Grouped bar layouts with single or clustered category management.
* **Line Graph:** Single or multi-series connected line plots with customizable line colors and marker shapes.
* **Scatter Plot:** Discrete point mapping with customizable markers, regression best-fit lines, and $R^2$ calculation.
* **Histogram:** Customizable bin starts, bin widths, bin counts, and frequency entries.

### 🔀 Smart Series Mode Toggles
* **Contextual Framing Questions:**
  * **Bar Graphs:** Prompts user to select between `Single Bar Graph` (default) and `Clustered Bar Graph`.
  * **Line Graphs & Scatter Plots:** Prompts user to select between `One Set of Data` (default) and `Multiple Sets of Data`.
* **Adaptive Control Sets:**
  * **Single / One Set:** Displays a clean color-only picker (plus point shape selector for line/scatter).
  * **Clustered / Multiple Sets:** Defaults to two active series and exposes full series naming, custom color picking, marker shape selection, dynamic series addition (up to 8), and deletion.
* **Auto-Switching:** Deleting down to a single remaining series automatically restores the single-series mode toggle.

### 🎨 Accessible Color System (Okabe-Ito Palette) & Marker Shapes
Pre-configured with universal colorblind-friendly colors:
1. **Navy / Blue** (`#0072B2`)
2. **Orange** (`#E69F00`)
3. **Bluish Green** (`#009E73`)
4. **Vermilion** (`#D55E00`)
5. **Sky Blue** (`#56B4E9`)
6. **Reddish Purple** (`#CC79A7`)
7. **Darkened Gold** (`#E5C494`)
8. **Charcoal Slate** (`#4A5568`)
* **Custom Hex Picker:** Allows selecting custom colors via native dialog.
* **Visual Marker Palette:** Choose from `Circle`, `Square`, `Triangle`, `Diamond`, `Cross`, and `Star` markers rendered directly in interactive shape triggers, canvas plots, and exported keys.

### 📐 Scientific & Math Tools
* **Linear Regression:** Automatic calculation of the slope-intercept equation ($y = mx + b$) and coefficient of determination ($R^2$) on scatter plots.
* **± Error Bars:** Interactive drag-to-set error bar sizing mode.
* **Quarter-Interval Minor Gridlines:** Toggleable subtle gridlines drawn at 1/4, 1/2, and 3/4 intervals between major ticks.
* **Centering Tick Font Controls:** Adjustable tick font size (defaults to centered 14pt).
* **Scientific Symbols Dropdown:** Quick-insertion for `±`, `°`, `μ`, `Δ`, `Ψ`, `α`, `β`, `Φ`, and `×`.
* **One-Click Sub/Superscript:** `X²` and `X₂` buttons to transform highlighted input text into native Unicode sub/super characters.

### 💾 Project Management & Export
* **JSON Project Persistence:** Save (`.json`) and open complete project files to resume work across sessions with full configuration persistence (graph type, series mode, colors, marker shapes, scales).
* **Export Options:** Download high-resolution PNG images with composite legends (matching point shapes and colors) or copy the image directly to the clipboard.

---

## 3. Architecture & Technology

### Technology Stack
* **HTML5 Canvas:** 3-layer canvas stack (`gc` for grid/labels, `dc` for data points/lines, `oc` for overlays).
* **Vanilla JavaScript:** Zero external runtime dependencies; self-contained DOM manipulation and canvas rendering.
* **CSS3:** Responsive flexbox/grid layout with custom-styled controls and scrollbars.

### Canvas Layering Model
```text
┌───────────────────────────────────────────┐
│ #graph-wrap                               │
│  ├─ canvas #gc (Grid, Ticks, Axes, Titles)│
│  ├─ canvas #dc (Bars, Lines, Scatter, Fit)│
│  └─ canvas #oc (Interactive Overlays)     │
└───────────────────────────────────────────┘
