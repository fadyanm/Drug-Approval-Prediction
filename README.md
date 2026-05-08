# FDA Drug Approval Prediction System

## Overview

This project is a machine learning system designed to predict whether a drug candidate is likely to be approved by the FDA based on its molecular structure.

It uses cheminformatics techniques (RDKit) to extract molecular descriptors from SMILES representations and applies multiple machine learning models to perform binary classification.

The system supports drug prediction through:
- Drug name lookup via PubChem
- SMILES string input
- Manual molecular feature input

---

## Problem Statement

Drug discovery is expensive and time-consuming. Early prediction of regulatory approval can help:

- Reduce failed experimental trials
- Optimize research and development costs
- Improve early-stage drug screening

This project builds a predictive model that classifies whether a compound is likely to receive FDA approval.

---

## Dataset

- Source: Hugging Face Datasets
- Dataset: Moreza009/drug_approval_prediction
- Input: SMILES (chemical structure format)
- Output: Binary label (Approved / Not Approved)

---

## Methodology

### Data Processing

- Loaded dataset from Hugging Face
- Extracted molecular descriptors using RDKit:
  - Molecular Weight
  - LogP
  - TPSA
  - Hydrogen Bond Donors
  - Hydrogen Bond Acceptors
  - Rotatable Bonds
  - Ring Count

---

## Best Model

- Model: Random Forest Classifier
- Selection Metric: ROC-AUC (Validation Set)

---

## Results

The best-performing model achieved strong generalization performance on the test set after hyperparameter tuning.

---

## System Workflow

1. User inputs drug information (name, SMILES, or manual features)
2. SMILES is converted into molecular descriptors using RDKit
3. Features are preprocessed and standardized
4. Machine learning model predicts approval probability
5. Output includes:
   - FDA approval probability
   - Binary classification result

---

## Features

### Drug Lookup
Integration with PubChem for retrieving molecular structures using drug names.

### SMILES Prediction
Direct prediction from chemical structure representation.

### Manual Input Mode
Allows users to input molecular features manually for simulation.

### Explainability
Provides feature-level contribution analysis for prediction interpretation.

---

## Installation

```bash
git clone https://github.com/your-username/Drug-Approval-Prediction.git
cd Drug-Approval-Prediction
pip install -r requirements.txt
```
---

## How to Use

### 1. Run Jupyter Notebook
```bash
jupyter notebook
```
Then open the main notebook and run all cells.

### 2. Run Python Script (if available)
```bash
python main.py
```
### 3. Using the System

After running the program, choose one of the following options:

**Option 1: Drug Name Search**
1) Enter a drug name (e.g., Aspirin)
2) System fetches data from PubChem
3) Predicts FDA approval probability

**Option 2: SMILES Input**

1) Enter a SMILES string  
2) System computes molecular descriptors  
3) Outputs prediction result  

Example SMILES:

```text
CC(=O)OC1=CC=CC=C1C(=O)O
```

**Option 3: Manual Feature Input**
1) Enter molecular properties manually
2) System predicts approval likelihood

### 4. Output Interpretation
- FDA Approved (Likely Approved): High probability of approval
- Not FDA Approved (Likely Rejected): Low probability of approval

## Notes
- Ensure all dependencies are installed before running
- RDKit installation may require Conda on some systems
- Internet connection required for PubChem lookup

