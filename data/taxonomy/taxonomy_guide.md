
# Structured Photographic Parameter Taxonomy

To ensure reproducible and explainable assessment, SensiPhoto utilizes a taxonomy of **64 photographic parameters** . This taxonomy was developed through iterative consultation with experts and refined to minimize ambiguity .

For the full list of prompts and their refined versions (Old vs. New), please refer to `parameters_definition.csv` in this directory.

## 📊 Parameter Categories
The parameters are organized into eight thematic groups :

1.  **Technical Quality**: Assessment of noise, sharpness, exposure, and dynamic range .
2.  **Composition**: Analysis of visual balance, rule of thirds, and spatial arrangement .
3.  **Framing and Geometry**: Evaluation of crop, alignment, and perspective .
4.  **Color and Tone**: Saturation, color harmony, and white balance .
5.  **Visual Clarity**: Subject separation and distraction removal.
6.  **Narrative and Emotional Impact**: High-level semantics and storytelling intent .
7.  **Post-Processing Effects**: Analysis of editing naturalness and filter usage.
8.  **Intended Use**: Suitability for specific contexts (e.g., portfolio, social media) .

## 📝 Evaluation Modalities
To enforce consistency, each parameter is assigned a specific data type :

| Modality | Count | Description |
| :--- | :--- | :--- |
| **Quantitative Scores** | 29 | Scalar ratings (e.g., 0-10 or 0-100) |
| **Binary Indicators** | 23 | True/False technical flags (e.g., "Is focus sharp?") |
| **Categorical Selections** | 6 | Multiple-choice classifications |
| **Textual Descriptors** | 6 | Short, structured semantic descriptions |

## 📐 Geometric Preprocessing
Certain compositional parameters (e.g., leading lines, rule of thirds) are supported by **Geometric Preprocessing**. This involves overlaying visual guides (grids, spirals) onto the image during inference to provide explicit visual cues and reduce spatial ambiguity .