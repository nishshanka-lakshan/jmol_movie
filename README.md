# 🧪 Molden MO Movie Script

A simple **Jmol** automation script for generating **molecular orbital (MO) animation frames** from `.molden` files.  
This tool is ideal for visualizing orbital evolution, such as the real-time evolution of electron dynamics.

## 🎬 Overview

This script:
- Loads a `.molden` file containing molecular orbital data  
- Applies consistent visualization settings (colors, transparency, orientation, etc.)  
- Iterates through orbitals or time frames  
- Exports each as a high-resolution `.png` frame  
- Allows easy movie creation with **FFmpeg**

## ⚙️ Usage

### 1. Edit paths
Open the script in a script editor in JMOL and set your file paths:
Open JMOL → Go to File → Script → Open… and select the script and update your file paths.
```jmol
load "path/to/your/file.molden"
var OUTDIR = "path/to/output/"

### 2. Configure parameters

Adjust rendering and frame parameters as needed:

var FIRST  = 1;       # First frame index
var LAST   = 7500;    # Last frame index
var STEP   = 10;      # Process every nth MO
var CUTOFF = 0.03;    # Isosurface cutoff
var ALPHA  = 0.25;    # Transparency

