# Expert-Validated Reference Set

## Overview
This directory contains the metadata and annotations for the **Reference Set**, consisting of **250 images**. The 250 benchmark images are stored in [this Google Drive link](https://drive.google.com/drive/folders/1W_S02QDP-xmtUgQhw0Ozw6EZQgUQvB8t?usp=sharing).

## Purpose: The "Trusted Anchor"
Unlike standard validation sets used for benchmarking, this set serves a specific engineering function in the SensiPhoto pipeline:
* **Grounding:** These images act as the source pool for **Visual Retrieval-Augmented Generation (VRAG)**.
* **In-Context Learning:** When the system assesses a new image, it retrieves visually similar examples from this set to guide the Vision-Language Model.

**Important:** This set is **not** intended to be used as a test set for performance comparison. It is a component of the generation system itself.

## Validation Methodology (Human-in-the-Loop)
The annotations in `annotations.json` were produced via a **Human-in-the-Loop (HITL)** process:
1.  **Automated Proposal:** A VLM generated initial assessments.
2.  **Expert Audit:** Professional photographers audited the outputs, verifying correctness and identifying ambiguities.
3.  **Refinement:** Experts applied targeted corrections. These validated examples ensure the pipeline does not propagate noise or stylistic drift.

## File Format
* `annotations.json`: Contains the finalized, expert-audited values for all 64 parameters for each of the 250 images.