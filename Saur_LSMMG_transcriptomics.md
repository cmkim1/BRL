# Bacterial transcriptomics in LSMMG

## 1. Bacterial strains and conditions
+ _Staphlyococcus aureus_ NRS 111

3 replicates were cultured in LSMMG (low shear modeled micro-gravity) and NG (normal gravity).  

## 2. Library preparation & Sequencing
+ RNA prep: RNA was extracted using QiAGEN RNA mini-prep kit.
+ Library prep: Zymo-Seq RiboFree® Total RNA Library Kit (Zymo Research).
+ Sequencing: MiSeq, Reagent V2 (150 PE)
+ Actual yield: 2.77GB
+ % PF: 98.131%
+ % >= Q30: 94.53%
    
Species | Condition | Total reads | Total bases (Mbp)
--- | --- | --- | ---
_S. aureus_ NRS 111 | NG1 | 1,710,851 | 513
_S. aureus_ NRS 111 | NG2 | 1,436,064 | 431
_S. aureus_ NRS 111 | NG3 | 1,682,246 | 505
_S. aureus_ NRS 111 | LSMMG1 | 1,485,300 | 446
_S. aureus_ NRS 111 | LSMMG2 | 1,489,052 | 447
_S. aureus_ NRS 111 | LSMMG3 | 1,991,733 | 598

## 3. Adapter trimming, alignment, DEG analysis  
All processes were conducted in Galaxy server.  
+ Adapter trimming: Trim Galore! (Galaxy Version 0.6.7+galaxy0)
+ Alignment BWA-MEM2 (Galaxy Version 2.2.1+galaxy1)
+ Count: featureCounts (Galaxy Version 2.0.3+galaxy2)
+ DEG analysis: edgeR (Galaxy Version 3.36.0+galaxy4)
+ Reference genomes used: [PRJNA289526](https://www.ncbi.nlm.nih.gov/Traces/study/?acc=SAMN03859750&o=acc_s%3Ad)


## 4.1 _S. aureus_ in LSMMG  
Genes were sorted by their differential expression as below.

Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 3297
Upregulated | LogFC > 1 and P-value < 0.05 | 33
Not significant | \|LogFC\| <= 1 or P-value >= 0.05 | 3249
Downregulated | LogFC < -1 and P-value < 0.05 | 15

### 4.1.1. MDS plot & MD plot
<img src = "https://github.com/user-attachments/files/18814763/mdsplot_Gravity.pdf" width = "45%" height = "45%"><img src = "https://github.com/user-attachments/files/18814764/mdplot_LSMMG-NG.pdf" width = "45%" height = "45%" align = "right">

### 4.1.2. Top 20 DEG tables
Product | logFC | P value
---- | ---- | ----
DUF443 family protein | 3.11 | 0.0212
Antibacterial protein 3 | -2.95 | 2.79E-06
PTS system glucose-specific EIICBA component | -2.71 | 0.0358
L-threonine dehydratase catabolic TdcB | 1.97 | 5.49E-11
Alanine dehydrogenase 1 | 1.92 | 1.25E-08
**Quinolone resistance protein NorB** | 1.9 | 6.29E-11
L-threonine dehydratase catabolic TdcB | 1.8 | 8.20E-09
Serine/threonine exchanger SteT | 1.71 | 3.15E-07
Antibacterial protein 3 | -1.67 | 8.18E-08
Alanine dehydrogenase 1 | 1.66 | 2.84E-07
Serine/threonine exchanger SteT | 1.63 | 6.46E-07
hypothetical protein | -1.57 | 0.0302
**Enterotoxin type C-3** | 1.57 | 0.0335
hypothetical protein | 1.55 | 0.0145
Quinol oxidase subunit 3 | 1.34 | 0.0001
Catabolite control protein A | 1.3 | 0.0158
Bax inhibitor-1/YccA family protein | -1.28 | 0.0007
Formate dehydrogenase | -1.27 | 1.44E-05
N-acetylmuramoyl-L-alanine amidase sle1 | 1.24 | 9.98E-07
Quinol oxidase subunit 4 | 1.23 | 3.49E-05

