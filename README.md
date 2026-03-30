# Kazakh Missing Word Challenge — WISH Women in STEM Hackathon 2026

## 🏆 Result: Top 20| Accuracy: 53%

## Overview
NLP competition to predict the position of a missing word in Kazakh sentences.
Given a sentence with one word removed, the model predicts the 0-indexed position 
of the missing word.

## Task
- **Input:** Kazakh sentence with one missing word (no marker)
- **Output:** 0-indexed position of the missing word
- **Train set:** 554k full Kazakh sentences
- **Labeled set:** 99k sentences with position labels
- **Test set:** 15,000 sentences

## Model Architecture
```
Input → XLM-RoBERTa-base (278M params) → CLS + Mean Pooling → Linear Head → Position
```

Key innovation: **Token Alignment** — maps each word to its first subword token,
helping the model understand word boundaries in agglutinative Kazakh language.

## Results
| Version | Data | Epochs | Score |
|---------|------|--------|-------|
| Baseline | 50k | 3 | 0.307 |
| Improved | 99k | 3 | 0.530 |

## How to Reproduce
1. Install dependencies:
```bash
pip install transformers torch pandas scikit-learn
```

2. Download the dataset from Kaggle:
```
https://www.kaggle.com/competitions/kazakh-missing-words-challenge-for-wish
```

3. Run the notebook:
```
notebook_Merey (3).ipynb
```

Training time: ~3 hours on GPU Tesla T4

## Tech Stack
- Python, PyTorch
- HuggingFace Transformers (XLM-RoBERTa-base)
- Kaggle GPU (Tesla T4 x2)
- scikit-learn, pandas, numpy

## Files
```
├── notebook_Merey (3).ipynb      # Main training notebook
├── presentation.pptx         # Project presentation
└── README.md
```

## Competition
**WISH Women in STEM Hackathon 2026**  
Kazakh Missing Word Challenge  
Organized by: Freedom Lifestyle and Freedom AI Labs
