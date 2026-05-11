# Curriculum Learning Session-Based Recommendation System (CL)

This project implements a Curriculum Learning-based Session Recommendation System. The workflow requires generating TransE embeddings first, then using them during model training inside the notebook.

---

# Project Structure

```bash
CL/
│
├── Notebooks/
│   └── CL Train.ipynb          # Main training notebook
│
├── Data/
│   ├── yoochoose1_64/          # Dataset folder
│   └── sample.json             # Sample dataset preview (10 samples)
│
├── create_transe_emb.py        # Script to generate TransE embeddings
│
├── requirements.txt            # Required dependencies
│
└── README.md                   # Project documentation
```

---

# Installation

## 1. Clone or Download the Project

```bash
git clone <your-repo-link>
cd CL
```

## 2. Install Requirements

Open CMD or terminal in the project root folder and run:

```bash
pip install -r requirements.txt
```

---

# Dataset Preparation

Ensure your dataset file:

```bash
all_train_seq.txt
```

is available in the correct directory before generating embeddings.

---

# Step 1: Generate TransE Embeddings

Run the following script first:

```bash
python create_transe_emb.py
```

### Input:

```bash
all_train_seq.txt
```

### Output:

```bash
transe_emb
```

---

# Why This Step is Important

The generated `transe_emb` file contains TransE embeddings that are later used during curriculum learning model training.

Without this file, training in the notebook may fail or produce incomplete results.

---

# Step 2: Train the Model

After generating embeddings:

1. Open:

```bash
Notebooks/CL Train.ipynb
```

2. Run all notebook cells sequentially.

---

# Sample Data

A sample preview is available here:

```bash
Data/sample.json
```

This contains 10 example samples to help understand dataset formatting.

---

# Workflow Summary

```bash
all_train_seq.txt
        │
        ▼
create_transe_emb.py
        │
        ▼
    transe_emb
        │
        ▼
CL Train.ipynb
        │
        ▼
Model Training
```

---

# Notes

* Make sure all dependencies from `requirements.txt` are installed.
* Run embedding generation before notebook training.
* Recommended environment:

  * Python 3.10
  * TensorFlow 2.10
  * CUDA (optional for GPU acceleration)

---

# Troubleshooting

## Missing package:

```bash
pip install -r requirements.txt
```

## Notebook errors:

* Verify `transe_emb` exists
* Verify `all_train_seq.txt` path
* Check dataset folder structure

---

# Purpose

This repository focuses on Curriculum Learning for session-based recommendation, where TransE embeddings are used to enrich item relationships before training.
