# 🧪 Molden MO Movie Script

A simple **Jmol** automation script for generating **molecular orbital (MO) animation frames** from `.molden` files.  
This tool is ideal for visualizing orbital evolution from **real-time simulations**, **charge migration studies**, or **time-resolved electronic structure calculations** (e.g., RT-MR-ADC, TDDFT).

---

## 🎬 Overview

This script:
- Loads a `.molden` file containing molecular orbital data  
- Applies consistent visualization settings (colors, transparency, orientation, etc.)  
- Iterates through orbitals or time frames  
- Exports each as a high-resolution `.png` frame  
- Allows easy movie creation with **FFmpeg**

---

## ⚙️ Usage

### 1. Edit paths
Open the script in a text editor and set your file paths:
```jmol
load "path/to/your/file.molden"
var OUTDIR = "path/to/output/"


2. Configure parameters

Adjust rendering and frame parameters as needed:

var FIRST  = 1;       # First frame index
var LAST   = 7500;    # Last frame index
var STEP   = 10;      # Process every nth MO
var CUTOFF = 0.03;    # Isosurface cutoff
var ALPHA  = 0.25;    # Transparency

3. Run in Jmol

Open Jmol.

Go to File → Script → Open… and select the script.

The script will generate .png images sequentially in your output directory.

Each file will be named as:

mo_0001.png
mo_0011.png
mo_0021.png
...


Convert frames to a movie

After generating frames, compile them into a video using FFmpeg:

# Basic version
ffmpeg -framerate 10 -pattern_type glob -i "mo_*.png" -pix_fmt yuv420p mo_movie.mp4

# Optional: specify codec
ffmpeg -framerate 10 -pattern_type glob -i "mo_*.png" -c:v libx264 -pix_fmt yuv420p animation.mp4

You can adjust:

-framerate for animation speed

output name (mo_movie.mp4, animation.mp4, etc.)


Visualization details

The script sets:


background white;
set antialiasDisplay true;
set antialiasTranslucent true;

color atoms cpk;
spacefill 23%;
backbone 0.25;
isosurface translucent 0.25;

rotate y 180;
rotate x 30;
