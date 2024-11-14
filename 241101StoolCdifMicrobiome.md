# Stool Microbiome cultured with _C. difficile_

## 1. Library

### Samples
- Adult stool samples microbiome.
- Stool samples were cultured with _C. difficile_ in LSMMG or NG.
#### _C. difficile_
- **T:** ATCC9689
- **20:** NCCP11820
- **70:** ATCC700057
#### Gravity
- **N:** Normal Gravity
- **L:** Low Shear Modeled Microgravity

### PCR Details
- **Master Mix:** Vazyme Phanta Max Super Fidelity PCR Master Mix
- **Target Region:** V3-V4 (~440 bp)
- **Indexes:** In-house 96 CD indexes
- **Cycling Conditions:** 25 cycles - 12 cycles

### Mock Control
- **Standard Used:** ZymoBIOMICS Microbial Community DNA Standard II (Log Distribution)

### Library Preparation
- **Dilution:** 7 pM diluted library
- **PhiX Spike-In:** 30% PhiX
- **Loading:** Library was mixed with samples from other project (soil microbiome samples from Prof. KJCho).

## 2. MiSeq Output

### Yields
- **Actual Yield:** 9.12 GB
- **Average % ≥ Q30:** 81.85%
- **% Cluster PF:** 92.43%
- **% Aligned to PhiX:** 35.01%

### Read Counts
- **Total Reads:** 16,074,930
- **PF Reads:** 14,858,163
- **% Reads Identified:** 62.127

## 3. Analysis

**R packages and database used**  
- [dada2 (ver. 1.30.0)](https://benjjneb.github.io/dada2/index.html)
- [ggplot2 (ver. 3.5.1)](https://ggplot2.tidyverse.org)
- [silva_nr99_v138.1_train_set](https://zenodo.org/records/4587955)
- [silva_species_assignment_v138.1](https://zenodo.org/records/4587955)

### Filtering/Trimming and Merging

Forward reads length: 290  
Reverse reads length: 230  
maxEE: both 2  
truncQ: 2  

### Standard Validation

**Detected Genera and Their Relative Abundance**
| **Genus**                       | **Actual Abundance (%)** | **Standard**                      | **Standard Abundance (%)** |
|----------------------------------|---------------------------|-------------------------------------|---------------------------|
| Listeria                        | 96.10                     | Listeria monocytogenes             | 95.9                      |
| Pseudomonas                     | 2.61                      | Pseudomonas aeruginosa             | 2.8                       |
| Bacillus                        | 1.09                      | Bacillus subtilis                  | 1.2                       |
| Escherichia-Shigella           | 0.10                      | Escherichia coli                   | 0.069                     |
| Salmonella                      | 0.09                      | Salmonella enterica                | 0.07                      |
| Limosilactobacillus                  | 0.008                      | Lactobacillus fermentum            | 0.012                     |
| Staphylococcus             | -                      | Staphylococcus aureus              | 0.00067                   |
| Enterococcus                               | -                         | Enterococcus faecalis              | 0.0001                    |


Abundance below 0.01% were not detected.  

## 4. Results

### Alpha Diversity
- <img src = "https://github.com/user-attachments/assets/ac1ae62a-3128-4fb4-8c2e-83e217497c01">
### Ordinates Plot ### 
- **NMDS plot colored by samples**
  - <img src = "https://github.com/user-attachments/assets/1dca6fdb-f1c7-4b55-91c9-767c9b555f64">

- **NMDS plot colored by gravity** 
  - <img src = "https://github.com/user-attachments/assets/00778ef5-605c-4023-97f0-daa7fe282670">

- **NMDS plot colored by strains of _C.difficile_**
  - <img src = "https://github.com/user-attachments/assets/3995f55e-428c-45f3-a0ea-514494c06a0b">

- **NMDS plot colored by replicate number**
  - <img src = "https://github.com/user-attachments/assets/7c5a859d-f82a-444e-a2b8-3d90b74922eb">

### Composition Bar Plot ###
- **Genus level**
  - <img src = "https://github.com/user-attachments/assets/e4cc32ba-eed4-44f2-a151-399116a54ceb">
