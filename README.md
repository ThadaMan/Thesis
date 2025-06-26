# DXF Parser for Structural Drawings

This repository is part of a modular pipeline for extracting BIM-ready geometry from DXF files used in structural engineering workflows.

## Notebook
- `DXF_parser.ipynb`: Parses DXF files, classifies geometry, tags metadata, and saves structured outputs.

## Workflow Overview

1. **Setup**  
   Import libraries and define input/output paths.

2. **Define Parsing Logic**  
   Core functions are organized into modular categories:
   - Geometry Utilities
   - DXF Entity Parsers
   - Chain Builder (reconstruct profiles)
   - Cutout Detection
   - Profile Classification & Feature Grouping
   - DXF Entity Handler
   - Batch Processing & Layer Summary
   - Metadata Tagging

3. **Set File Paths**  
   Choose folders for DXF inputs and structured JSON outputs.

4. **Configure Parsing Behavior**  
   Define layer filters, arc segmentation detail, and adaptive tolerance.

5. **Run the Parser**  
   Process all DXF files in the folder and save parsed output as `_geometry.json`.

6. **Review Output**  
   Parsed geometry includes:
   - Edge chains
   - Cutout annotations
   - Text metadata
   - Profile classifications


## Output
The notebook generates a JSON file for each DXF, containing:
- Edges and geometry
- Layer info
- Detected holes, tags, arcs, circles, etc.

## Configuration
Supported via `config.json`, including:
- Allowed/Ignored layers
- Arc segmentation control
- Adaptive tolerance

## Usage
Run the notebook in Google Colab or locally with:
```bash

