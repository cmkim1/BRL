# Stool Microbiome cultured with Prebiotics

## 1. Library

### Samples
- Adult stool samples microbiome.
- Stool samples were cultured with or without three prebiotics in LSMMG or NG.
#### Prebiotics
- **Control:** No prebiotics
- **2FL:** 2'-Fucosyllactose
- **3FL:** 3'-Fucosyllactose
- **GOS:** Galacto-oligosaccharides
#### Gravity
- **NG:** Normal Gravity
- **LSMMG:** Low Shear Modeled Microgravity

### PCR Details
- **Master Mix:** Vazyme Phanta Max Super Fidelity PCR Master Mix
- **Target Region:** V3-V4 (~440 bp)
- **Indexes:** In-house 96 CD indexes
- **Cycling Conditions:** 25 cycles

### Mock Control
- **Standard Used:** ZymoBIOMICS Microbial Community DNA Standard II (Log Distribution)

### Library Preparation
- **Dilution:** 7 pM diluted library
- **PhiX Spike-In:** 30% PhiX
- **Loading:** Library was mixed with samples from other project (_D. magna_, kimi)

## 2. MiSeq Output

### Yields
- **Actual Yield:** 10.01 GB
- **Average % ≥ Q30:** 83.19%
- **% Cluster PF:** 92.83%
- **% Aligned to PhiX:** 32.5%

### Read Counts
- **Total Reads:** 17,563,464
- **PF Reads:** 16,305,034
- **Reads Identified:** 64.592

### Index Distribution
- **Index CV:** 0.481
- **Index Min:** 0.170
- **Index Max:** 2.601  
  


## 3. Analysis

**R packages and database used**  
- [dada2 (ver. 1.30.0)](https://benjjneb.github.io/dada2/index.html)
- ggplot2 (ver. 3.5.1)
- [silva_nr99_v138.1_train_set](https://zenodo.org/records/4587955)
- [silva_species_assignment_v138.1](https://zenodo.org/records/4587955)

### Filtering/Trimming and Merging

Forward reads length: 290  
Reverse reads length: 230  
maxEE: both 2  
truncQ: 2  

- before filtering: forward (left) and reverse (right)  
  <img src = "https://github.com/user-attachments/files/17070173/1_qplot_before_forward.pdf"  width="45%" height="45%" align="left"><img src = "https://github.com/user-attachments/files/17070210/1_qplot_before_reverse.pdf" width="45%" height="45%">  
  
- after filtering: forward (left) and reverse (right)  
  <img src = "https://github.com/user-attachments/files/17070222/1_qplot_after_forward.pdf"  width="45%" height="45%" align="left"><img src = "https://github.com/user-attachments/files/17070223/1_qplot_after_reverse.pdf"  width="45%" height="45%" align="righ">  
  

- Merged reads length distribution:  
  <img src = "https://github.com/user-attachments/files/17070259/3_mergers_length_distribution.pdf">



### Tracking Summary
| **Step**        | **Count**      |
|------------------|----------------|
| **Input**        | 5,773,923      |
| **Filtered**     | 4,758,002      |
| **Denoised F**   | 4,723,539      |
| **Denoised R**   | 4,738,739      |
| **Merged**       | 4,624,264      |
| **Non-chimera**  | 4,402,735      |  

In total, 76% of input reads were taxonomy-assigned.

### Standard Validation

**Detected Genera and Their Relative Abundance**
| **Genus**                       | **Actual Abundance (%)** | **Standard**                      | **Standard Abundance (%)** |
|----------------------------------|---------------------------|-------------------------------------|---------------------------|
| Listeria                        | 95.95                     | Listeria monocytogenes             | 95.9                      |
| Pseudomonas                     | 3.12                      | Pseudomonas aeruginosa             | 2.8                       |
| Bacillus                        | 0.72                      | Bacillus subtilis                  | 1.2                       |
| Escherichia-Shigella           | 0.10                      | Escherichia coli                   | 0.069                     |
| Salmonella                      | 0.09                      | Salmonella enterica                | 0.07                      |
| Staphylococcus                  | 0.01                      | Lactobacillus fermentum            | 0.012                     |
| Limosilactobacillus             | 0.01                      | Enterococcus faecalis              | 0.00067                   |
| -                               | -                         | Staphylococcus aureus              | 0.0001                    |


Abundance below 0.01% were not detected.  

## 4. Results

### Alpha Diversity
- <img src = "https://github.com/user-attachments/assets/5b7ff43d-d6f1-4b92-a92f-8254e5eb519b">
### Ordinates Plot ### 
- **NMDS plot**
  - <img src = "https://github.com/user-attachments/assets/a689702a-d71f-4b8d-9718-1e2bce922513">

- **Ordinates Plots from Other Methods:** 
  - <img src = "https://github.com/user-attachments/assets/e6e14d5d-6cf0-46e4-87fd-09278ddac6ec">

- **NMDS plots of each treament**
  - <img src = "https://github.com/user-attachments/assets/9ec53777-1cb3-4f04-9ff9-7f76f6c812bb">

### Composition Bar Plot ###
- **Genus level**
  - <img src = "https://github.com/user-attachments/assets/8d3e6bf7-faa1-48f0-8bba-e1b74aa38b75">
- **Family level**
  - <img src = "https://github.com/user-attachments/assets/808681f0-f412-4052-977b-93404cfba201">
