# Enhanced Text-Guided Image Editing with EF P2P
**ESE 645: Deep Generative Models (Fall 2024)**  
Final Project – Edit-Friendly P2P with Improvements

---

## 1. Overview
This repository focuses on **text-driven image editing** based on a fork of [PnPInversion (by cure-lab)](https://github.com/cure-lab/PnPInversion), specifically the **Edit-Friendly (EF) P2P** method. The primary goal is to preserve structural fidelity from the input image while enabling semantic edits guided by text. We replicated the baseline EF P2P algorithm and introduced enhancements involving advanced text encoders (LLaMA 3B v2) and a newer diffusion backbone (Stable Diffusion 2-1-base). These modifications demonstrate how richer language embeddings and improved latent diffusion can yield better image edits in terms of style, structure, and perceptual realism.

---

## 2. Project Files
- **`edit-friendly-inv-p2p-pt1.ipynb`**  
  - Baseline EF P2P replication.
  - Demonstrates original algorithm’s steps on a subset of the PIE-Bench dataset.
- **`edit-friendly-inv-p2p-pt2.ipynb`**  
  - **Enhancement #1**: Integration of LLaMA 3B v2 text encoder in place of CLIP.
  - Focuses on semantic richness but notes slight trade-offs in metrics.
- **`edit-friendly-inv-p2p-pt3.ipynb`**  
  - **Enhancement #2**: Upgrading the diffusion backbone to Stable Diffusion 2-1-base.
  - Emphasizes higher-resolution fidelity and improved perceptual outcomes.

*(File names are indicative; each notebook might contain overlapping experiments and evaluation steps.)*

---

## 3. Method & Enhancements
1. **Edit-Friendly P2P (Baseline)**  
   - Uses a stochastic inversion to embed structural details into latent noise, allowing flexible edits while preserving major content.
   - Evaluated on ~700 images (PIE-Bench dataset).

2. **Replacing CLIP Encoder with LLaMA 3B v2**  
   - **Goal**: Enrich text-to-image alignment with a more advanced language model.  
   - **Outcome**: Slight drop in SSIM (fidelity) and LPIPS (visual similarity) due to more stylized or subtle transformations; semantic alignment remained comparable to baseline.

3. **Upgrading to Stable Diffusion 2-1-base**  
   - **Goal**: Improve image resolution and fine detail retention.  
   - **Outcome**: Notable improvement in SSIM and a lower LPIPS value, indicating better structural consistency and perceptual quality.  
   - CLIP similarity stayed consistent with baseline, confirming stable semantic alignment.

---

## 4. Key Results
- **Baseline EF P2P**:
  - Good balance of structural fidelity (SSIM ≈ 0.72) and perceptual similarity (LPIPS ≈ 0.07).
  - Demonstrates effective editing without heavy distortions.

- **EF + LLaMA 3B v2**:
  - Strong semantic embeddings but introduced more stylized or subtle edits.
  - Modest decline in SSIM and slight increase in LPIPS, suggesting less structural fidelity vs. baseline.

- **EF + Stable Diffusion 2-1-base**:
  - Slightly higher SSIM (≈0.73) and lower LPIPS (≈0.06), signaling improved preservation of structure and better perceptual outcomes.
  - Achieves finer details while staying faithful to textual prompts.

---

## 5. Conclusions
1. **EF P2P** effectively balances content preservation with semantic flexibility.  
2. **Richer text encoders** (e.g., LLaMA) can deepen semantic nuance but may introduce subtle or stylized changes.  
3. **Upgraded diffusion backbones** like SD 2-1-base greatly improve high-resolution editing without sacrificing prompt alignment.

---
