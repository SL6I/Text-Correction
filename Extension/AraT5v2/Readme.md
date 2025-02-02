Updating AraT5 to a new version for fine-tuning Arabic GEC tasks involves using customized scripts for training and predictions.
# AraT5v2: Fine-Tuning for Arabic GEC
Working through scripts for Arab T5 version 2 to tackle Arabic Grammatical Error Correction. Training involves using `finetune_arat5v2.py`, while predictions are handled with `predict_arat5v2.py`.

---

## Table of Contents
1. [Introduction](#introduction)
2. [Requirements](#requirements)
3. [Data Format](#data-format)
4. [Usage](#usage)
5. [Train](#training)
6. [Prediction](#prediction)
7. [Evaluation](#evaluation)
8. [Result](#result)

---

## Introduction

Significant advancements have been made in AraT5v2, including faster convergence, larger sequence length, and enhanced Arabic grammatical error correction. I am assessing its improved capabilities on the Qalb-2014 dataset.

---

## Requirements

1. **Python 3.x**
2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```
   Minimal packages:
   - `transformers`
   - `datasets`
   - `sentencepiece`
   - `tqdm`
3. **GPU (recommended)** for faster training.
- **Navigate to the directory**: Move into the directory containing the files:
  ```bash
  cd Extension/AraT5v2
   ```
---

## Data Format

Each JSON file (train/dev/test) follows:
```json
[
  { "raw": "أنا لكتاب الكتاب", "cor": "أنا كاتب الكتاب" },
  { "raw": "هذه بعض الكلمات الخاطأة", "cor": "هذه بعض الكلمات الخاطئة" }
]
```
- **raw**: Uncorrected Arabic sentence.
- **cor**: Corrected sentence.

---
# Usage
In the following code, we will guide you on how to run the code:
## Training

Run `finetune_arat5v2.py`:
```bash
python finetune_arat5v2.py \
  --train_file "../../Dataset/finetuning/AraT5-AraT5v2/train.json" \
  --dev_file "../../Dataset/finetuning/AraT5-AraT5v2/dev.json" \
  --output_dir "arat5v2_gec_checkpoints" \
  --epochs 5 \
  --learning_rate 1e-4
```

**Parameters**:
- `--train_file`: Path to the training set.
- `--dev_file`: Path to dev set.
- `--output_dir`: Directory for checkpoints.
- `--epochs`: Training epochs (default 5).
- `--learning_rate`: Default `1e-4`.

---

## Inference

Run `predict_arat5v2.py`:
```bash
python predict_arat5v2.py \
  --model_dir "arat5v2_gec_checkpoints\saved_model" \
  --dev_file "../../Dataset/finetuning/AraT5-AraT5v2/dev.json" \
  --test_file "../../Dataset/finetuning/AraT5-AraT5v2/test.json" \
  --output_dir "predictions" \
  --max_length 1024 \
  --num_beams 5
```

**Parameters**:
- `--model_dir`: Folder of our fine-tuned model.
- `--dev_file`: Path to dev set.
- `--test_file`: Path to test set.
- `--output_dir`: Stores predictions.
- `--num_beams`: Beam parameter.

---

## Evaluation

Using `m2scorer`:
```bash
python ../../Evaluation/Scripts/m2scorer.py \
  predictions/test_predictions.txt \
  ../../Dataset/Test/QALB-2014-L1-Test.m2
```

---

## Result:
![image](https://github.com/user-attachments/assets/88ac5d0d-7c07-4336-bb98-972c739d9f2b)


**Happy Fine-Tuning!**

