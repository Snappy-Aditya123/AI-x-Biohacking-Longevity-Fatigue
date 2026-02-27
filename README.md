# Longevity Fatigue Index (LFI)
### Multimodal Fatigue & Recovery Estimation Using Computer Vision and Camera-Based Physiology

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#license)
[![Status](https://img.shields.io/badge/Status-Research%20Prototype-orange.svg)](#)

---

## Abstract

**Longevity Fatigue Index (LFI)** is a multimodal AI system designed to estimate cognitive and physiological fatigue using non-invasive consumer hardware.

The system integrates:

- Remote photoplethysmography (rPPG) for heart rate extraction  
- Facial and periocular visual biomarkers  
- Blink dynamics and ocular metrics  
- Lightweight machine learning fusion  

The objective is to quantify fatigue-related physiological signals and provide interpretable readiness indicators aligned with longevity and health optimization principles.

---

## Motivation

Chronic fatigue, autonomic imbalance, and stress accumulation are strongly associated with:

- Reduced performance  
- Increased injury risk  
- Cardiovascular strain  
- Long-term health decline  

Most individuals rely on subjective perception to assess fatigue, which is often inaccurate.

LFI provides:

- Objective fatigue metrics  
- Non-contact physiological sensing  
- Early drift detection  
- Interpretable risk indicators  

---

## System Architecture

### 1️⃣ Remote Photoplethysmography (rPPG)

Using a phone camera (rear camera + flash), LFI:

- Extracts green-channel intensity fluctuations
- Applies band-pass filtering (~0.7–4 Hz)
- Detects pulse peaks
- Estimates:
  - Heart Rate (BPM)
  - Inter-beat intervals
  - HRV proxy (e.g., RMSSD)

---

### 2️⃣ Facial & Ocular Biomarkers

Using MediaPipe Face Mesh or equivalent:

- Eye aspect ratio (EAR)
- Blink rate and blink duration
- Periocular redness index
- Micro head instability
- Facial texture deviation

These features are associated with cognitive load, fatigue, and autonomic stress.

---

### 3️⃣ Feature Engineering

Extracted features include:

- Resting HR deviation from baseline
- HRV proxy
- Blink frequency per minute
- Blink duration variability
- Ocular redness ratio
- Head micro-movement variance

---

### 4️⃣ Fatigue Fusion Model

A lightweight classifier (e.g., logistic regression or random forest) combines multimodal features to output:

- Fatigue Probability Score (0–1)
- Autonomic Stress Index
- Cognitive Readiness Category:
  - 🟢 Optimal
  - 🟡 Moderate Fatigue
  - 🔴 High Fatigue Risk

---

## Core Metrics

| Category | Metric | Description |
|----------|--------|------------|
| Cardiovascular | Heart Rate (BPM) | Pulse extracted via rPPG |
| Cardiovascular | HRV Proxy | RMSSD from inter-beat intervals |
| Ocular | Blink Rate | Blinks per minute |
| Ocular | Blink Duration | Mean and variance |
| Ocular | Redness Index | Scleral color shift |
| Motor | Head Stability | Micro movement variance |
| Composite | Fatigue Score | ML-based fusion output |

---

## Example Workflow

1. Record 20–30 seconds of rPPG using phone camera  
2. Record 15–20 seconds of face video  
3. System extracts physiological and ocular features  
4. Model computes fatigue score  
5. Dashboard displays:
   - HR + HRV
   - Blink metrics
   - Fatigue classification
   - Recommendation

---

## Longevity Relevance

Chronic physiological fatigue is linked to:

- Autonomic dysregulation  
- Stress-related cardiovascular strain  
- Cognitive decline  
- Overtraining syndrome  

By quantifying fatigue non-invasively, LFI supports:

- Sustainable training decisions  
- Cognitive performance optimization  
- Preventive health monitoring  

---

## Tech Stack

- Python
- OpenCV
- MediaPipe Face Mesh
- NumPy / SciPy
- Scikit-learn
- Streamlit (optional UI)

---

## Project Structure (Suggested)

```text
longevity-fatigue-index/
  ppg/
    capture.py
    preprocess.py
    hr_estimation.py
  vision/
    face_tracking.py
    blink_analysis.py
    redness_metrics.py
  features/
    feature_engineering.py
  model/
    fatigue_model.py
  ui/
    dashboard.py
  main.py
  requirements.txt
  README.md# Longevity Fatigue Index (LFI)
### Multimodal Fatigue & Recovery Estimation Using Computer Vision and Camera-Based Physiology

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](#license)
[![Status](https://img.shields.io/badge/Status-Research%20Prototype-orange.svg)](#)

---

## Abstract

**Longevity Fatigue Index (LFI)** is a multimodal AI system designed to estimate cognitive and physiological fatigue using non-invasive consumer hardware.

The system integrates:

- Remote photoplethysmography (rPPG) for heart rate extraction  
- Facial and periocular visual biomarkers  
- Blink dynamics and ocular metrics  
- Lightweight machine learning fusion  

The objective is to quantify fatigue-related physiological signals and provide interpretable readiness indicators aligned with longevity and health optimization principles.

---

## Motivation

Chronic fatigue, autonomic imbalance, and stress accumulation are strongly associated with:

- Reduced performance  
- Increased injury risk  
- Cardiovascular strain  
- Long-term health decline  

Most individuals rely on subjective perception to assess fatigue, which is often inaccurate.

LFI provides:

- Objective fatigue metrics  
- Non-contact physiological sensing  
- Early drift detection  
- Interpretable risk indicators  

---

## System Architecture

### 1️⃣ Remote Photoplethysmography (rPPG)

Using a phone camera (rear camera + flash), LFI:

- Extracts green-channel intensity fluctuations
- Applies band-pass filtering (~0.7–4 Hz)
- Detects pulse peaks
- Estimates:
  - Heart Rate (BPM)
  - Inter-beat intervals
  - HRV proxy (e.g., RMSSD)

---

### 2️⃣ Facial & Ocular Biomarkers

Using MediaPipe Face Mesh or equivalent:

- Eye aspect ratio (EAR)
- Blink rate and blink duration
- Periocular redness index
- Micro head instability
- Facial texture deviation

These features are associated with cognitive load, fatigue, and autonomic stress.

---

### 3️⃣ Feature Engineering

Extracted features include:

- Resting HR deviation from baseline
- HRV proxy
- Blink frequency per minute
- Blink duration variability
- Ocular redness ratio
- Head micro-movement variance

---

### 4️⃣ Fatigue Fusion Model

A lightweight classifier (e.g., logistic regression or random forest) combines multimodal features to output:

- Fatigue Probability Score (0–1)
- Autonomic Stress Index
- Cognitive Readiness Category:
  - 🟢 Optimal
  - 🟡 Moderate Fatigue
  - 🔴 High Fatigue Risk

---

## Core Metrics

| Category | Metric | Description |
|----------|--------|------------|
| Cardiovascular | Heart Rate (BPM) | Pulse extracted via rPPG |
| Cardiovascular | HRV Proxy | RMSSD from inter-beat intervals |
| Ocular | Blink Rate | Blinks per minute |
| Ocular | Blink Duration | Mean and variance |
| Ocular | Redness Index | Scleral color shift |
| Motor | Head Stability | Micro movement variance |
| Composite | Fatigue Score | ML-based fusion output |

---

## Example Workflow

1. Record 20–30 seconds of rPPG using phone camera  
2. Record 15–20 seconds of face video  
3. System extracts physiological and ocular features  
4. Model computes fatigue score  
5. Dashboard displays:
   - HR + HRV
   - Blink metrics
   - Fatigue classification
   - Recommendation

---

## Longevity Relevance

Chronic physiological fatigue is linked to:

- Autonomic dysregulation  
- Stress-related cardiovascular strain  
- Cognitive decline  
- Overtraining syndrome  

By quantifying fatigue non-invasively, LFI supports:

- Sustainable training decisions  
- Cognitive performance optimization  
- Preventive health monitoring  

---

## Tech Stack

- Python
- OpenCV
- MediaPipe Face Mesh
- NumPy / SciPy
- Scikit-learn
- Streamlit (optional UI)
