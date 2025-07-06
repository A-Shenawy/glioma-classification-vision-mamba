# Glioma Classification using Vision Mamba

<img src="https://github.com/A-Shenawy/glioma-classification-vision-mamba/blob/main/Glioma%20Classification%20using%20Vision%20Mamba.PNG?raw=true" width="100%" style="background-size: cover;">
---
## Project Overview  
Fine-tune a Vision Mamba (VIM) model to classify mitosis vs. non‑mitosis in glioma histopathology.  

### Agenda  
1. Literature Review  
2. Methodology  
3. Results  
4. Future Work  

## 1. Literature Review  
We surveyed recent approaches, including conventional CNNs, U‑Net, YOLO+ResNet, and Vision Transformers (ViTs).  
| Model Type      | Key Feature                      |
|-----------------|----------------------------------|
| CNN             | Local pattern extraction         |
| U‑Net           | Encoder–decoder segmentation     |
| YOLO + ResNet   | Fast detection, deep features    |
| Vision Transformer (ViT) | Self‑attention              |

## 2. Methodology  
- **ROI Extraction:** Load images + JSON annotations → normalize → crop ROIs  
- **Augmentation:** Flip, rotate, random crop (50% probability on non‑mitosis)  
- **Processing:** Resize → min–max normalize → binarize labels  

**Model Architecture:** Vision Mamba (SSMs + cross‑scan, no attention), patch embedding → VIM encoder → MLP head

## 3. Results  
5‑fold stratified CV:  
- CNN baseline: F1 95%  
- VIM base: F1 91.6%  
- VIM+ResNet head: F1 92.0%  
- VIM+CNN head: F1 92.6%  
- VIM+CNN+MSPE: F1 93.2%

Plots and detailed metrics in [results/](results/).

## 4. Future Work  
- Replace SSM blocks with cross‑convolution  
- Explore hybrid attention mechanisms  

---

## Getting Started

1. **Install dependencies**  
   ```bash
   pip install -r requirements.txt
