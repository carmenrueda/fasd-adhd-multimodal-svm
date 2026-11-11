# Does Resting-State EEG Add Value Beyond Neuropsychological Assessment in FASD and ADHD? A Multimodal Machine Learning Study

## Overview

This repository contains the full analysis pipeline for the differential diagnosis 
of Fetal Alcohol Spectrum Disorder (FASD) and Attention-Deficit/Hyperactivity Disorder 
(ADHD) using resting-state EEG and neuropsychological scores within a nested 
Leave-One-Subject-Out (LOSO) L1-SVM classification framework.

## Repository Structure
```text
├── notebook.ipynb        # Main analysis pipeline
├── requirements.txt      # Python dependencies
├── Results/              # Classification outputs (Excel, figures)
│   ├── Single-family EEG/
│   ├── Paired-family EEG/
│   ├── Multimodal EEG+NP/
│   └── NP Features/
    └── AUC bootstrap comparisons.xlsx
└── data/                 # NOT included (patient data, confidential)
```

## Methods Summary

- **Sample:** 40 children aged 8–16 (20 FASD, 20 ADHD)
- **EEG:** Eyes-closed resting-state, 28 electrodes (10-20 system)
- **Features:** 14 EEG metrics × 28 electrodes = 392 features  
  (Spectral powers, TBR, Hjorth parameters, SampEn, HFD)
- **NP scores:** 18 candidate scores from WISC-V, FDT, Stroop, and Faces Test
- **Classifier:** L1-regularized linear SVM, nested LOSO cross-validation
- **Models:** Single-family EEG (14), Paired-family EEG (91), Multimodal (6)

## Data Availability

Raw EEG and neuropsychological data are not publicly available due to 
participant confidentiality. To run the notebook, set the environment variable:

```bash
export FASD_ADHD_DATA=/path/to/your/data
```

## Requirements

```bash
pip install -r requirements.txt
```
