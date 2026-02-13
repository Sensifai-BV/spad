# SPAD Generation Set: Image Downloads

To use the annotations in this folder, you must download the corresponding image subsets. The dataset is split into two categories based on the evaluation parameters: **Boolean** (technical flags) and **Scoring** (quantitative/qualitative assessments).

## 1. Download Sources
Please download the image archives from the following locations:

| Subset | Google Drive Link | Description |
| :--- | :--- | :--- |
| **Boolean Images** | [Google Drive Link](https://drive.google.com/drive/folders/16jMwYYnrgVOXH4WvBtdZoPP1jYrJmXNl?usp=sharing) | Images used for binary parameter training. |
| **Scoring Images** | [Google Drive Link](https://drive.google.com/drive/folders/1fDI-s1h0aODweYlxE_wwUIJ-YMJyn2B-?usp=sharing) | Images used for scalar and textual training. |

## 2. Setup Instructions
The JSON files in `annotations/` expect the images to be located in specific directories relative to the training root. 

**Action:**
1.  Download the two archives above.
2.  Extract them into the `data/spad_generation_set/images/` directory.
3.  Ensure your directory structure looks exactly like this:

```text
data/spad_generation_set/images/
├── saved_images_boolean/
│   ├── batch_1_image_1.png
│   └── ...
└── saved_images_scoring/
    ├── batch_1_image_1.png
    └── ...


