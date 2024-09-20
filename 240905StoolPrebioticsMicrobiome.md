# Stool Microbiome cultured with Prebiotics

## 1. Library

### Samples
- **Type:** Adult stool samples microbiome.
- Stool samples were cultured with or without three prebiotics in LSMMG or NG.

### Prebiotics
- **Control:** No prebiotics
- **2FL:** 2'-Fucosyllactose
- **3FL:** 3'-Fucosyllactose
- **GOS:** Galacto-oligosaccharides

### Gravity
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
- **Loading:** Loaded onto the sequencer

## 2. MiSeq Output

### Metrics
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

---

*Report generated on 2024-09-20*


## 3. Analysis

### DADA2 Version
- **Version Used:** 1.30.0

### Filtering and Trimming

Forward reads length: 290  
Reverse reads length: 230  
maxEE: both 2  
truncQ: 2  

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

## Standard Validation

### Detected Genera and Their Relative Abundance
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

