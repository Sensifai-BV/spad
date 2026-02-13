# SensiPhoto Assess Dataset (SPAD)

**Paper:** SensiPhoto: An Open and Expert-Aligned Dataset for Image Aesthetic Assessment Using Human-in-the-Loop and Visual Retrieval-Augmented Generation  
**Authors:** Mohamad Hasan Bahari, Maxime Favier  
**Affiliation:** Sensifai & The Photo Academy (Brussels, Belgium) 

---

## 📸 Abstract
Image Aesthetic Assessment (IAA) is often limited by subjectivity and a lack of expert-aligned supervision . **SensiPhoto** introduces an open dataset generated through an engineering pipeline that integrates **Human-in-the-Loop (HITL)** validation with **Visual Retrieval-Augmented Generation (VRAG)** .

The **SensiPhoto Assess Dataset (SPAD)** comprises **4,000 images** annotated with a rigorously defined taxonomy of **64 photographic parameters**, spanning technical quality, composition, and semantic intent . To reduce ambiguity, the generation pipeline utilizes retrieval-based grounding on a reference set of expert-validated examples and incorporates targeted geometric preprocessing .

This repository supports reproducible research by releasing both the dataset and the underlying generation methodology .

---

## 📂 Repository Structure

The dataset is organized into two distinct subsets to ensure quality control and prevent circular supervision :

### 1. Reference Set (Expert-Validated)
* **Location:** `data/reference_set/`
* **Size:** 250 Images 
* **Description:** A compact set of images where every parameter has been audited and validated by professional photographers .
* **Purpose:** These images serve as the "trusted anchor" for retrieval-based grounding. They are **not** intended as a benchmark for performance evaluation but as context for the VRAG pipeline .

### 2. Generation Set (SPAD-4k)
* **Location:** `data/spad_generation_set/`
* **Size:** 4,000 Images 
* **Sources:** Curated from public photography repositories (Unsplash) and community critique datasets (RPCD) .
* **Description:** The core dataset annotated using the VRAG pipeline. Contains multi-modal labels including scores, binary indicators, and text .

---

## 🚀 Usage

### Prerequisites
* Python 3.8+
* (Optional) A local copy of the [Reddit Photo Critique Dataset (RPCD)](https://github.com/google-research-datasets/rpcd) .

## 📥 Dataset Download

The dataset images are hosted externally. To replicate the directory structure required by the annotation files, please follow the download instructions below.

### 1. Reference Set (250 Images)
* **Source:** [Google Drive Link](https://drive.google.com/drive/folders/1W_S02QDP-xmtUgQhw0Ozw6EZQgUQvB8t?usp=sharing)
* **Destination:** Place the images directly into `data/reference_set/`.
* **Note:** These images are the "Trusted Anchor" for the VRAG pipeline. See `data/reference_set/README.md` for details.

### 2. SPAD Generation Set (4,000 Images)
The generation set is split into two subsets (Boolean and Scoring). Download both and extract them into `data/spad_generation_set/images/`.

| Subset | Download Link | Description |
| :--- | :--- | :--- |
| **Boolean** | [Google Drive](https://drive.google.com/drive/folders/16jMwYYnrgVOXH4WvBtdZoPP1jYrJmXNl?usp=sharing) | Technical flags and binary parameters. |
| **Scoring** | [Google Drive](https://drive.google.com/drive/folders/1fDI-s1h0aODweYlxE_wwUIJ-YMJyn2B-?usp=sharing) | Scalar scores and textual assessments. |

**Directory Structure:**
After downloading and extracting, ensure your `images` folder structure looks exactly like this to ensure compatibility with the JSON annotations:

```text
data/spad_generation_set/images/
├── saved_images_boolean/   # Contains Boolean subset images
│   ├── batch_1_image_1.png
│   └── ...
└── saved_images_scoring/   # Contains Scoring subset images
    ├── batch_1_image_1.png
    └── ...

## 🤖 Models & Fine-tuning

The SPAD dataset is designed to facilitate the fine-tuning of open-source Vision-Language Models (VLMs) for aesthetic assessment tasks.

As a continuation of this research, we have released **Photo-Gemm**: a repository containing two **Gemma 3 (4B)** models that have been fine-tuned and quantized using the 4,000 images from the SPAD dataset.

🔗 **Access the code and models here:** [Sensifai-BV/photogemm](https://github.com/Sensifai-BV/photogemm)