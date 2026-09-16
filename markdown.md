# A Humble Quick Plot

A lightweight, interactive client-side graph builder designed for students to rapidly create, customize, and export math and science charts.

**Author:** Steven Humble  
**Version:** v1.6.0  
**Build Date:** 08-20-2026[cite: 6]  
**License:** Free for educational use[cite: 6]

---

## 1. Overview

**A Humble Quick Plot** is an interactive, single-file HTML5 Canvas graphing application[cite: 6]. It simplifies graph generation for educational assignments by providing an intuitive graphical interface for plotting data directly onto a canvas, managing multiple series, formatting mathematical typography, calculating linear regressions, and exporting high-resolution images[cite: 6].

---

## 2. Key Features

### 📊 Graph Types
* **Bar Chart:** Grouped bar layouts with dynamic category management[cite: 6].
* **Line Graph:** Multi-series connected line plots with custom color coordination[cite: 6].
* **Scatter Plot:** Discrete point mapping with customizable markers and best-fit line regression[cite: 6].
* **Histogram:** Customizable bin starts, bin widths, bin counts, and frequency entries[cite: 6].

### 🎨 Accessible Color System (Okabe-Ito Palette)
Pre-configured with universal colorblind-friendly colors[cite: 6]:
1. **Navy / Blue** (`#0072B2`)[cite: 6]
2. **Orange** (`#E69F00`)[cite: 6]
3. **Bluish Green** (`#009E73`)[cite: 6]
4. **Vermilion** (`#D55E00`)[cite: 6]
5. **Sky Blue** (`#56B4E9`)[cite: 6]
6. **Reddish Purple** (`#CC79A7`)[cite: 6]
7. **Darkened Gold** (`#E5C494`)[cite: 6]
8. **Charcoal Slate** (`#4A5568`)[cite: 6]
* *Custom Hex Picker:* Allows picking any custom color via an integrated color picker[cite: 6].

### 📐 Scientific & Math Tools
* **Linear Regression:** Automatic calculation of the slope-intercept equation ($y = mx + b$) and coefficient of determination ($R^2$) on scatter plots[cite: 6].
* **± Error Bars:** Interactive drag-to-set error bar sizing mode[cite: 6].
* **Quarter-Interval Minor Gridlines:** Toggleable subtle gridlines drawn at 1/4, 1/2, and 3/4 intervals between major ticks[cite: 6].
* **Scientific Symbols Dropdown:** Quick-insertion for `±`, `°`, `μ`, `Δ`, `Ψ`, `α`, `β`, and `Φ`[cite: 6].
* **One-Click Sub/Superscript:** `X²` and `X₂` buttons to transform highlighted input text into native Unicode sub/super characters[cite: 6].

### 💾 Project Management & Export
* **JSON Project Persistence:** Save (`.json`) and open complete project files to resume work across sessions[cite: 6].
* **Export Options:** Download high-resolution PNG images with composite legends or copy image directly to the clipboard[cite: 6].

---

## 3. Architecture & Technology

### Technology Stack
* **HTML5 Canvas:** 3-layer canvas stack (`gc` for grid/labels, `dc` for data points/lines, `oc` for overlays)[cite: 6].
* **Vanilla JavaScript:** Zero external dependencies; self-contained DOM manipulation and canvas rendering[cite: 6].
* **CSS3:** Responsive flexbox layout with custom-styled scrollbars and UI controls[cite: 6].

### Canvas Layering Model
```text
┌───────────────────────────────────────────┐
│ #graph-wrap                               │
│  ├─ canvas #gc (Grid, Ticks, Axes, Titles)│
│  ├─ canvas #dc (Bars, Lines, Scatter, Fit)│
│  └─ canvas #oc (Interactive Overlays)     │
└───────────────────────────────────────────┘