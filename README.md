# Does Resting-State EEG Add Value Beyond Neuropsychological Assessment in FASD and ADHD? A Multimodal Machine Learning Study

## Overview

This repository contains the analysis code and model outputs for a study testing whether resting-state EEG improves the classification of children with Fetal Alcohol Spectrum Disorder (FASD) versus Attention-Deficit/Hyperactivity Disorder (ADHD) beyond standardized neuropsychological assessment. 14 EEG feature families and 18 neuropsychological scores were evaluated in 112 models, using an L1-regularized linear support vector machine with nested leave-one-subject-out cross-validation.

## Repository Structure
```text
├── notebook.ipynb                      # Main analysis pipeline
├── requirements.txt                    # Python dependencies
├── LICENSE
├── Results/
│   ├── README.md                       # Description of each output file
│   ├── Neuropsychological baseline/
│   │   ├── c_selection.xlsx            # Selected C per fold
│   ├── Single-family EEG/
│   │   ├── nested_stability_haufe      # L1 selection stability & Haufe weights     
│   │   ├── c_selection.xlsx
│   ├── Paired-family EEG/
│   │   ├── nested_stability_haufe            
│   │   ├── c_selection.xlsx
│   ├── Multimodal EEG+NP/
│   │   ├── nested_stability_haufe
│   │   ├── c_selection.xlsx
└── data/                               # NOT included (patient data, confidential)
```

## Methods Summary

- **Sample:** 40 children aged 8–16 (20 FASD, 20 ADHD)
- **EEG:** eyes-closed resting state, 28 electrodes (10-20 system), 2-second epochs (2400 retained, balanced across groups)
- **Features:** 14 feature families × 28 electrodes = 392 features (band power, theta/beta ratio, Hjorth parameters, sample entropy, Higuchi fractal dimension)
- **Neuropsychological scores:** 18 candidate scores from the WISC-V, Five Digit Test, Stroop Test, and Faces Test
- **Classifier:** L1-regularized linear SVM, nested LOSO cross-validation
- **Models (112):** neuropsychological baseline (1), single-family EEG (14), paired-family EEG (91), multimodal (6)

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
