# PS-23: COVID-19 and Lung Disease Detection from Chest X-rays

**V S Adharsh | RA2311026050021 | AIML B**

Deep-learning classifier that sorts chest X-rays into four classes: **COVID-19, Lung opacity, Viral pneumonia, Normal**, with Grad-CAM used to inspect whether the model looks at the lungs rather than text markers or image borders (shortcut learning).

## Dataset
[COVID-19 Radiography Database](https://www.kaggle.com/datasets/tawsifurrahman/covid19-radiography-database) (Kaggle), 21,165 images used in full (COVID 3,616 / Lung opacity 6,012 / Normal 10,192 / Viral pneumonia 1,345). Lung masks are not used.

## Method
- Stratified split, seed 42: 15,291 train / 2,699 validation / 3,175 test
- Resize 224x224, rescale to [0,1]; training augmentation: rotation 15 deg, shift 0.1, zoom 0.1, horizontal flip
- MobileNetV2 (ImageNet), backbone fully frozen, head: GAP -> Dense(128) -> Dropout(0.3) -> Dense(4, softmax)
- Adam (default LR), categorical cross-entropy, batch 32, 10 epochs (about 36 min on Colab)

## Test-set results (3,175 images)
| Class | Precision | Recall | F1 |
|---|---|---|---|
| COVID-19 | 0.81 | 0.90 | 0.85 |
| Lung opacity | 0.93 | 0.71 | 0.81 |
| Normal | 0.85 | 0.95 | 0.90 |
| Viral pneumonia | 0.96 | 0.88 | 0.92 |
| **Accuracy / Macro F1** | | | **0.87 / 0.87** |

Main confusion: Lung opacity predicted as Normal. Grad-CAM was run on four misclassified test images; the evidence on shortcut learning is inconclusive (see report).

## Files
- `COVID19_Xray_Classification.ipynb`: full notebook (data, split, training, evaluation, misclassified images, Grad-CAM)
- `RA2311026050021_PS23_Report.pdf`: two-page report

## How to run
1. Open the notebook in Google Colab (GPU runtime).
2. Upload your own `kaggle.json` (Kaggle > Settings > Create New Token) and copy it to `/root/.kaggle/`. Do not paste API keys into the notebook.
3. Run all cells.

## Limitations
Single public dataset, no patient IDs (possible patient overlap across splits), no external validation. For research and education only, not a diagnostic tool.

## Citation
M.E.H. Chowdhury et al., "Can AI help in screening viral and COVID-19 pneumonia?", IEEE Access, 8, 2020. T. Rahman et al., Computers in Biology and Medicine, 132, 2021.
