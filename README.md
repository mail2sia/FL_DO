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
- **Data Obfuscation (DO)** for privacy protection,
- **BERT** for high-accuracy emotion classification.

This system, **FL-BERT+DO**, effectively balances user privacy and model performance, outperforming traditional differential privacy approaches.

## Repository Structure

| File | Description |
|:-----|:------------|
| `Predictive_Analytics_in_Mental_Health_Using_FL_and_DP.ipynb` | Analysis and benchmarking of federated learning with differential privacy (FL-DP). |
| `sentiments_in_mental_health_using_fl_bart_dof.ipynb` | FL-BART model with data obfuscation. |
| `sentiments-fl-dof-roc-auc.ipynb` | ROC-AUC performance evaluation across models. |
| `sentiments-in-mental-health-fl-bigru-dof.ipynb` | FL-BiGRU model with data obfuscation experiments. |
| `sentiments-in-mental-health-using-fl-cnn-dof.ipynb` | FL-CNN model with data obfuscation training and evaluation. |
| `Privacy-enhanced sentiment analysis in mental health Federated learning with data obfuscation and bidirectional encoder representations from transformers.pdf` | Full published paper (Electronics 2024). |

## Main Contributions

- **FL-BERT+DO Framework**  
  - Combines federated learning with a novel data obfuscation strategy.
  - Achieves robust sentiment prediction while enhancing privacy.

- **Empirical Privacy Validation**  
  - Evaluated against membership inference and linkage attacks.
  - Global model membership inference AUC: 22.40% (low risk).

- **Superior Predictive Performance**  
  - Test Accuracy: **82.74%**
  - Precision: **83.30%**
  - Recall: **82.74%**
  - F1-Score: **82.80%**

- **Comparison to Differential Privacy (DP) Approaches**  
  - Outperforms FL-DP, which achieved only ~16.7% accuracy.

- **Support for Mental Health Monitoring**  
  - Enables decentralized, privacy-conscious mental health analytics.

## Dataset

- **Emotions in Text Dataset**  
  - 🔗 [Kaggle Link](https://www.kaggle.com/datasets/ishantjuyal/emotions-in-text)
  - Supplemented with a **synthetic obfuscated dataset** (rule-based generation) for privacy.

## Getting Started

### Requirements

```bash
pip install torch transformers sklearn matplotlib seaborn numpy pandas
```

### Running

Run the notebooks sequentially:
1. `Predictive_Analytics_in_Mental_Health_Using_FL_and_DP.ipynb` → (Baseline comparison)
2. `sentiments_in_mental_health_using_fl_bart_dof.ipynb` → (FL-BERT+DO model)
3. `sentiments-in-mental-health-fl-cnn-dof.ipynb` → (FL-CNN+DO model)
4. `sentiments-in-mental-health-fl-bigru-dof.ipynb` → (FL-BiGRU+DO model)
5. `sentiments-fl-dof-roc-auc.ipynb` → (ROC-AUC evaluation and comparisons)

## Results Summary

| Model           | Accuracy | Precision | Recall | F1-Score |
|:----------------|:--------:|:---------:|:------:|:--------:|
| FL-BERT+DO      | 82.74%   | 83.30%    | 82.74% | 82.80%   |
| FL-CNN+DO       | 61.34%   | 72.79%    | 61.34% | 62.40%   |
| FL-BiGRU+DO     | 57.83%   | 62.05%    | 57.83% | 58.32%   |
| FL-DP Baseline  | 16.73%   | 23.29%    | 16.73% | 18.18%   |

## Privacy Validation (Adversarial Attack Results)

| Attack Type | Model | AUC Score | Risk |
|:------------|:------|:---------:|:----:|
| Membership Inference (Global) | BERT | 22.40% | Low |
| Membership Inference (Local)  | BERT | 50.38% | Moderate |
| Linkage Attack (Macro Avg.)   | BERT | 51.29% | Moderate |

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
