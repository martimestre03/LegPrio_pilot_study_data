# Proprioception Assessment – Vicon Motion Capture Dataset

This repository contains the dataset used in the final degree project:  
**"Wearable System for Proprioception Assessment and Step Width Inference"**  
by Martí Mestre, Universitat Politècnica de Catalunya (UPC), 2025.

The dataset includes `.mat` files exported from the **Vicon Motion Capture System**, capturing 5 trials per subject under controlled walking conditions. The data was used to analyze proprioceptive errors, validate a wearable sensor system, and simulate step width prediction models.

---

## 📁 File Naming Convention

Each file follows this format:
S<subject_number>Crisscross_T<trial_number>.mat


| Segment         | Meaning                                      |
|-----------------|----------------------------------------------|
| `S3013`         | Subject ID                                   |
| `T1` to `T5`    | Trial number                                 |
| `right`, `left`, etc. | Walking condition (see below)          |

### 🔍 Example Filenames

- `S3013_Crisscross_T1_right.mat` — Right leg crossing over left at 0.7 m/s  
- `S3013_Crisscross_T2_left.mat` — Left leg crossing over right at 0.7 m/s  
- `S3013_Crisscross_T3_right.mat` — Right over left at 0.9 m/s  
- `S3013_Crisscross_T4_right.mat` — Right over left at 0.5 m/s  
- `S3013_Crisscross_T5_right.mat` — Right over left at 0.7 m/s, eyes closed  

> All trials are 2 minutes long, sampled at 150 Hz (~18,000 frames).

---

## 🧪 Trial Descriptions

| Trial | Condition             | Description                                  |
|-------|------------------------|----------------------------------------------|
| T1    | `right`               | 0.7 m/s — Right leg crossing over left       |
| T2    | `left`                | 0.7 m/s — Left leg crossing over right       |
| T3    | `right_09ms`          | 0.9 m/s — Right leg crossing over left       |
| T4    | `right_05ms`          | 0.5 m/s — Right leg crossing over left       |
| T5    | `right_closed`        | 0.7 m/s — Right over left with eyes closed   |

---

## 📦 File Contents

Each `.mat` file contains a structured Vicon export with the following top-level fields:

| Field        | Description                                                                 |
|--------------|-----------------------------------------------------------------------------|
| `Model`      | Includes marker set (`MkrSet`) and subject ID (`Subject`)                 |
| `Analog`     | Force plate signals (e.g., Bertec), units, labels                          |
| `FPlate`     | Force plate geometry, origin, and type (e.g., AMTI or Bertec)              |
| `Coor`       | 3D marker trajectories (`Signal`: [frames × markers × 3])                  |
| `Processing` | Biomechanical outputs including joint angles, gait events, and anthropometry |

### 🧠 Example `Processing` Fields

- `Bodymass`, `Height`
- `RSHN_R_Tibia_Z`, `LTHI_L_Femur_X`, etc. (segment angles)
- Heel strike and toe-off event timing (if available)

---

## 🔬 Usage

This dataset was used to:
- Evaluate proprioceptive error in leg-crossing detection
- Validate a 3D-printed wearable device with 9 distance sensors and 1 IMU
- Train and test polynomial models to infer ankle distance across the gait cycle
- Justify the need for step-width inference instead of direct measurement

---

## 📄 Citation

If you use this dataset, please cite:
Martí Mestre, Final Degree Project: "Wearable System for Proprioception Assessment and Step Width Inference," Universitat Politècnica de Catalunya, 2025.


---

## 📬 Contact

**Martí Mestre**  
📧 marti.mestre@estudiantat.upc.edu  
🔗 GitHub: [https://github.com/martimestre](https://github.com/martimestre)

