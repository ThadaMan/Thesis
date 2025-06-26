# DXF Parser & BIM Geometry Pipeline

This repository is part of a **modular pipeline** for extracting BIM-ready geometry from structural engineering drawings. It processes DXF files, identifies and classifies geometry, and validates the structured outputs with optional ground truth references.

---

## Repository Structure

```
Thesis/
│
├── DXF_Parser.ipynb                 # Step 1: Parse DXF and extract raw primitives
├── Geometry_Interpreter.ipynb      # Step 2: Interpret geometry and infer part types
├── JSON_Builder.ipynb              # Step 3: Convert parts into structured BIM output
├── Validator.ipynb                 # Step 4: Validate output against schema or reference
│
├── Config/
│   ├── config.json                 # Rules for the DXF parser
│   └── rules_config.json           # Geometry interpreter configuration
│
├── Example_Data/
│   ├── HTA1071F.dxf                # Original DXF drawing
│   ├── HTA1071F_parts.json         # Geometry output from Step 2
│   ├── HTA1071F_structured_output.json # Final structured BIM output
│   └── HTA1071F_ref.json (optional)    # Ground truth for validation
```

---

##  Pipeline Modules

| Notebook                   | Description |
|---------------------------|-------------|
| **DXF_Parser.ipynb**       | Parses raw DXF files and extracts geometry primitives (lines, arcs, polylines) with metadata. |
| **Geometry_Interpreter.ipynb** | Classifies geometry into labeled part types (e.g., anchors, blocks) using spatial rules and tag inference. |
| **JSON_Builder.ipynb**     | Converts labeled parts into structured BIM JSON format, applying shape logic (extrusions, revolutions). |
| **Validator.ipynb**        | Validates the structured output against schema rules and optionally against a reference file. |

---

## Setup Instructions

1. Clone the repository:
   ```bash
   git clone https://github.com/ThadaMan/Thesis.git
   cd Thesis
2. Install required Python packages:
3. pip install ezdxf jsonschema pandas matplotlib
4. Place any .dxf drawing files you want to process in the Example_Data folder.

Adjust the configuration files in the Config/ directory if needed.

▶️ Execution Steps
Run DXF_Parser.ipynb
Parses the drawing and extracts raw geometry into *_geometry.json.

Run Geometry_Interpreter.ipynb
Interprets primitives and classifies parts into *_parts.json.

Run JSON_Builder.ipynb
Builds structured BIM output as *_structured_output.json.

Run Validator.ipynb
Validates the structured file. Optionally compares it with a ground truth file.

🔍 Example Output
In the Example_Data/ folder:

HTA1071F.dxf: Raw input

HTA1071F_parts.json: Labeled geometry

HTA1071F_structured_output.json: Final BIM representation

HTA1071F_ref.json: Ground truth reference for validation (if available)

📄 License & Credits
This repository was developed as part of a master thesis in collaboration with Leviat.
Please contact the author for reuse permissions.
