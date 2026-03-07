# SPAD Generation Set: Image Downloads

To use the annotations in this folder, you must download the corresponding image subsets. The dataset is split into distinct categories based on evaluation parameters and reasoning tasks.

## 1. Download Sources
Please download the image archives from the following locations:

| Subset | Google Drive Link | Description |
| :--- | :--- | :--- |
| **Boolean Images** | [Google Drive](https://drive.google.com/drive/folders/16jMwYYnrgVOXH4WvBtdZoPP1jYrJmXNl?usp=sharing) | Images used for binary parameter training (technical flags). |
| **Scoring Images** | [Google Drive](https://drive.google.com/drive/folders/1fDI-s1h0aODweYlxE_wwUIJ-YMJyn2B-?usp=sharing) | Images used for scalar and textual training (aesthetic scores/critiques). |
| **Rule of Thirds Images** | [Google Drive Link](https://drive.google.com/drive/folders/1Hi9-E1O3_gv5-pB3ZUUdogIz3X4886v9?usp=sharing) | Images with Rule of Thirds grid overlays. |
| **Golden Rectangle Images** | [Google Drive Link](https://drive.google.com/drive/folders/1mxTEIvMD4lMW5kspqiHkeq-78vzN02jc?usp=sharing) | Images with Golden Rectangle border overlays. |
| **Golden Spiral Reasoning Set** | [Google Drive Link](https://drive.google.com/drive/folders/1YpiNoa2addjII0ixR12jXRy3aCpwLPVY?usp=sharing) | 2,000 image folders containing explicit visual overlays (all generated spirals, the final chosen spiral, and the evaluation label). Ideal for visual reasoning fine-tuning. |
| **Golden Triangles Reasoning Set** | [Google Drive Link](https://drive.google.com/drive/folders/1i1_1U6Guig3uvG2ztaJQnb62AiNvHJXW?usp=sharing) | 2,000 image folders containing explicit visual overlays (drawn triangles and the evaluation label) for geometric reasoning. |

*Note: The reasoning sets explicitly align with the targeted geometric preprocessing described in the SensiPhoto paper, which externalizes spatial structure to reduce interpretive variance[cite: 151, 153].*

## 2. Setup Instructions
The JSON files in `annotations/` expect the images to be located in specific directories relative to the training root. 

**Action:**
1.  Download the archives linked above.
2.  Extract them into the `data/spad_generation_set/images/` directory.
3.  Ensure your directory structure exactly mirrors the tree below:

```text
data/spad_generation_set/images/
├── boolean_saved_image/
│   ├── image_001.jpg
│   └── ...
├── scoring_saved_image/
│   ├── image_001.jpg
│   └── ...
├── saved_images_rule_of_thirds/
│   ├── batch_1_image_1.png
│   └── ...
├── saved_images_golden_rectangle/
|    ├── batch_1_image_1.png
|    └── ...
├── golden_spiral_images/
|   ├── image_001_folder/
|    │   ├── input.jpeg
|    │   ├── results.json
|    │   ├── GoldenSpiral/
|    │   │   ├── final_chosen_triangle.jpg
|    │   │   ├── processed_0.jpg
|    │   │   ├── processed_1.jpg
|    │   │   ...
|   └── ...
├── golden_triangles_images/
|   ├── image_001_folder/
|   │   ├── input.jpeg
|   │   ├── results.json
|   │   ├── GoldenTriangles/
|   │   │   ├── final_chosen_triangle.jpg
|   │   │   ├── processed_0.jpg
|   │   │   ├── processed_1.jpg
|   │   │   ...

    └── ...