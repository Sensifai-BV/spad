# Pipeline Pseudocode: HITL-VRAG Generation

This document outlines the algorithmic logic used to generate the SensiPhoto Assess Dataset (SPAD), as described in Section 3 of the paper. This pseudocode is provided to ensure reproducibility of the generation methodology .

## 1. System Components
* **Encoder ($\phi$):** CLIP-ViT-L/14 for embedding images into a shared latent space .
* **Reference Repository ($\mathcal{R}$):** The set of 250 expert-validated image-annotation pairs $(x_i, y_i)$ .
* **VLM:** A Vision-Language Model (e.g., GPT-4o) serving as the evaluator .

## 2. Generation Algorithm

For a given target image $x_{target}$:

### Step 1: Geometric Preprocessing (Selective)
If the parameter being evaluated relies on explicit spatial structure (e.g., Rule of Thirds):
1.  Apply a geometric overlay (grid/spiral) to $x_{target}$.
2.  **Note:** This provides explicit visual cues to reduce ambiguity during inference .

### Step 2: Visual Retrieval (VRAG)
Retrieve the $K$ most visually similar examples from the Reference Repository to serve as context .

```python
# K was empirically determined to be 3 
K = 3 

def retrieve_neighbors(target_image, reference_set):
    target_embedding = CLIP.encode(target_image)
    similarities = []
    
    for ref_image in reference_set:
        ref_embedding = CLIP.encode(ref_image)
        # Calculate Cosine Similarity 
        score = cosine_similarity(target_embedding, ref_embedding)
        similarities.append((ref_image, score))
        
    # Return top K neighbors
    return sort_by_score(similarities)[:K]