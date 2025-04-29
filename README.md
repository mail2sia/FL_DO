# Privacy-Enhanced Sentiment Analysis in Mental Health:  
**Federated Learning with Data Obfuscation and BERT**

This repository accompanies the paper:

**S.I. Ahsan, D. Djenouri, R. Haider**  
*"Privacy-Enhanced Sentiment Analysis in Mental Health: Federated Learning with Data Obfuscation and Bidirectional Encoder Representations from Transformers"*  
**Electronics 2024, 13, 4650**  
🔗 [Paper Link (Electronics MDPI)](https://doi.org/10.3390/electronics13234650)

## Overview

We introduce a **privacy-preserving framework** for mental health sentiment analysis, combining:
- **Federated Learning (FL)** for decentralized model training,
- **Data Obfuscation (DO)** for enhanced privacy,
- **BERT** for high-accuracy emotion classification.

Our system, **FL-BERT+DO**, achieves **stronger privacy protection and better prediction accuracy** compared to traditional FL-DP approaches.

## Repository Structure

| File | Description |
|:-----|:------------|
| `FL-BERT+DO.ipynb` | Federated BERT model with data obfuscation. |
| `FL-CNN+DO.ipynb` | Federated CNN model with data obfuscation. |
| `FL-BiGRU+DO.ipynb` | Federated BiGRU model with data obfuscation. |
| `fl-dof-roc-auc.ipynb` | ROC-AUC performance evaluation across models. |
| `FL-DP.ipynb` | Baseline: Federated Learning with Differential Privacy (FL-DP). |
| `figure2.png` | Comparison of novel vs baseline method (Accuracy, Precision, Recall, F1-score). |
| `figure3.1_CM_BERT.png` | Confusion matrix heatmap for FL-BERT+DO. |
| `figure3.2_CM_CNN.png` | Confusion matrix heatmap for FL-CNN+DO. |
| `figure3.3_CM_BiGRU.png` | Confusion matrix heatmap for FL-BiGRU+DO. |
| `figure4.png` | Forecast test metric comparison across models. |
| `figure5.1_ROC_AUC_BERT.png` | ROC-AUC curve per class for FL-BERT+DO. |
| `figure5.2_ROC_AUC_CNN.png` | ROC-AUC curve per class for FL-CNN+DO. |
| `figure5.3_ROC_AUC_BiGRU.png` | ROC-AUC curve per class for FL-BiGRU+DO. |
| `figure6.png` | Privacy (Epsilon) growth over epochs in FL-DP baseline. |

## Main Contributions

- **FL-BERT+DO Framework**  
  Combines federated learning with a novel data obfuscation method to protect user data.

- **Superior Privacy and Performance**  
  Demonstrates strong adversarial resistance (low AUC scores under attack) and outperforms FL-DP models.

- **Evaluation across Multiple Models**  
  - FL-BERT+DO
  - FL-CNN+DO
  - FL-BiGRU+DO
  - FL-DP (Baseline)

- **Confusion Matrix and ROC-AUC Analysis**  
  - Visualize classification accuracy across emotions.
  - Compare ROC curves and per-class AUC scores.
  
- **Privacy Tracking**  
  - Epsilon (𝜖) tracking over epochs shows extremely poor privacy with FL-DP baseline.

## Dataset

- **Emotions in Text Dataset**  
  🔗 [Kaggle Link](https://www.kaggle.com/datasets/ishantjuyal/emotions-in-text)
  
The dataset is **augmented with synthetic obfuscation** for privacy validation experiments.

## Getting Started

### Requirements

```bash
pip install torch transformers scikit-learn matplotlib seaborn numpy pandas
```

### Running

Run the notebooks in this sequence:
1. `FL-DP.ipynb` → Baseline: FL with Differential Privacy
2. `FL-BERT+DO.ipynb` → Main model: FL-BERT with Data Obfuscation
3. `FL-CNN+DO.ipynb` → Additional model: FL-CNN+DO
4. `FL-BiGRU+DO.ipynb` → Additional model: FL-BiGRU+DO
5. `fl-dof-roc-auc.ipynb` → ROC-AUC evaluation and metrics comparison

## Results Summary

| Model           | Test Accuracy | Precision | Recall | F1-Score |
|:----------------|:-------------:|:---------:|:------:|:--------:|
| **FL-BERT+DO**  | **82.74%**     | **83.30%**| **82.74%** | **82.80%** |
| FL-CNN+DO       | 61.34%         | 72.79%    | 61.34% | 62.40%   |
| FL-BiGRU+DO     | 57.83%         | 62.05%    | 57.83% | 58.32%   |
| FL-DP (Baseline) | 16.71%        | 24.82%    | 16.71% | 17.80%   |

📈 See `figure2.png` and `figure4.png` for visual comparison.

---

## ROC-AUC Analysis

| Model | Class | AUC |
|:------|:------|:---:|
| **FL-BERT+DO** | happy | 0.88 |
| **FL-BERT+DO** | anger / fear / sadness | 0.86 |
| **FL-CNN+DO** | surprise | 0.90 |
| **FL-CNN+DO** | love | 0.89 |
| **FL-BiGRU+DO** | all classes | ~0.58 |

- **FL-BERT+DO** achieves the highest AUC across most classes.
- **FL-BiGRU+DO** underperforms significantly (AUC < 0.6 for all classes).

📊 See:
- `figure5.1_ROC_AUC_BERT.png`
- `figure5.2_ROC_AUC_CNN.png`
- `figure5.3_ROC_AUC_BiGRU.png`

---

## Privacy Validation (Adversarial Attack Results)

| Attack Type | Model | AUC Score | Risk Level |
|:------------|:------|:---------:|:----------:|
| Membership Inference (Global) | FL-BERT+DO | 22.40% | **Low** |
| Membership Inference (Local) | FL-BERT+DO | 50.38% | **Moderate** |
| Linkage Attack (Macro Avg.) | FL-BERT+DO | 51.29% | **Moderate** |

- FL-BERT+DO shows strong privacy protection.
- FL-DP baseline experiences severe epsilon explosion over epochs (see `figure6.png`).

## Confusion Matrices

- `figure3.1_CM_BERT.png` → FL-BERT+DO
- `figure3.2_CM_CNN.png` → FL-CNN+DO
- `figure3.3_CM_BiGRU.png` → FL-BiGRU+DO

Each figure provides insights into model confusion between emotion classes.

## Citation

```bibtex
@article{Ahsan2024PrivacyEnhanced,
  title={Privacy-Enhanced Sentiment Analysis in Mental Health: Federated Learning with Data Obfuscation and Bidirectional Encoder Representations from Transformers},
  author={Shakil Ibne Ahsan and Djamel Djenouri and Rakibul Haider},
  journal={Electronics},
  volume={13},
  number={23},
  pages={4650},
  year={2024},
  publisher={MDPI},
  doi={10.3390/electronics13234650}
}
```
