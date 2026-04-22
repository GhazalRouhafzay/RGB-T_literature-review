# RGB-T Multimodal Scene Understanding_literature-review


## Overview

This project presents a **systematic literature review** on **RGB-Thermal (RGB-T) multimodal fusion** for **scene understanding tasks** such as object detection, segmentation, and tracking under challenging conditions (e.g., night, fog, rain).

The goal is to identify and analyze relevant scientific articles using a structured and reproducible pipeline based on the **PRISMA methodology**.

---

## Project Structure (Explained)

The repository is organized to clearly reflect each step of the research pipeline:

- The `data/initial/` folder contains the **raw exported files** directly downloaded from databases such as IEEE, Scopus, and Google Scholar. These files are unprocessed and serve as the starting point of the pipeline.

- The `data/raw/` folder contains a **merged and structured dataset** (`articles_raw.xlsx`) obtained after parsing the initial files.

- The `data/processed/` folder includes intermediate datasets:
  - `RGB-T_Clean.xlsx` : cleaned version of the data  
  - `RGB-T_screened.xlsx` : results after keyword-based filtering  
  - `RGB-T_Verified.xlsx` : dataset after applying scoring and validation  

- The `data/final/` folder contains the final selected articles:
  - `articles-retenus.xlsx` : articles retained for analysis  

- The `notebooks/` folder contains Jupyter notebooks used at each stage:
  - parsing, deduplication, screening, and final selection  

- The `prisma` file contains the **PRISMA diagram**, summarizing the selection process visually.

- The `query.txt` stores the **search queries** used in the databases to ensure reproducibility.

---

## Search Strategy

To collect relevant articles, we searched multiple academic databases using carefully designed queries.

The queries are built using three main components:

### 1. Modality (What type of data?)
We target works involving **RGB and Thermal (Infrared) fusion**, such as:
- RGB-T
- visible-thermal fusion
- infrared-visible fusion
- multispectral fusion

---

### 2. Task (What problem is solved?)
We focus on **scene understanding tasks**, including:
- object detection  
- segmentation  
- tracking  
- pedestrian detection  
- person re-identification  
- autonomous driving  

---

### 3. Environment (In what conditions?)
We emphasize challenging real-world conditions:
- night  
- low light  
- fog / haze  
- rain / smoke / dust  
- camouflage  

---

## Scoring

Each article is assigned a score out of a **maximum of 6 points**, based on the presence of specific keywords.

- **RGB-T / fusion terms** (e.g., “rgb-t”, “fusion”, “infrared”): **+3 points**  
- **Scene understanding tasks** (e.g., detection, segmentation, tracking): **+2 points**  
- **AI / learning methods** (e.g., deep learning, CNN, transformer): **+1 point**

If only weaker multimodal terms are found (e.g., “thermal imaging”, “cross-modal”), the article receives **+1 point instead of +3**.

---

## Methodology

The pipeline follows these steps:

1. **Data collection** from IEEE, Scopus, and Google Scholar on three different files 
2. **Parsing and structuring** from three different files into a unified dataset  
3. **Deduplication** remove duplicate articles and exclude Google Scholar records due to missing structured metadata (e.g., abstracts and keywords).   
4. **Screening** using keyword-based filtering  
5. **Eligibility check** after 'Screening',a manual verification of potentially relevant articles is necessary to be sure if they are included or excluded using inclusion/exclusion criteria.  
6. **Final selection** based on a scoring system. Articles with a **Final Score ≥ 4** are considered relevant and included in the final analysis. 

---

## PRISMA Summary

- Records identified: **150**  
- After initial screening: **94**  
- Duplicates removed: **9**  
- Studies included: **72**  
- Studies excluded: **13**  
- Final retained for analysis: **78**

---

## Requirements

To run the notebooks and reproduce the pipeline, the following tools and libraries are required:

### Environment
- Python **3.8+**
- Jupyter Notebook or VS Code

### Libraries Used
-pandas -> data manipulation and filtering
-openpyxl -> reading/writing Excel files
-numpy -> basic numerical operations
-re (regex) -> keyword matching and text normalization

### Python Libraries
Install the required packages using:

```bash
pip install pandas openpyxl numpy


