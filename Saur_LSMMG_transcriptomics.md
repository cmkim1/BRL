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
Quinol oxidase subunit 3 | 1.34 | 0.0001
Lipase 2 | -1.02 | 0.0002
30S ribosomal protein S10 | 1.18 | 0.0002
teichoic acid D-Ala incorporation-associated protein DltX | 1.06 | 0.0002
sterile alpha motif-like domain-containing protein | 1.1 | 0.0002
Leucotoxin LukDv | -1.02 | 0.0005
50S ribosomal protein L4 | 1.02 | 0.0005
Mn2 and Fe2 transporter | -1.28 | 0.0007
Staphyloferrin B synthase | -1.17 | 0.0007
50S ribosomal protein L11 | 1.04 | 0.0009
Ribosome hibernation promotion factor | -1.06 | 0.0012
50S ribosomal protein L3 | 1.04 | 0.0015
Bifunctional autolysin | 1.18 | 0.0015
Molybdate-binding protein ModA | 1.1 | 0.0017
Glyceraldehyde-3-phosphate dehydrogenase 1 | 1.12 | 0.0018
putative quinol oxidase subunit 1 | 1.14 | 0.0023
Phosphoribosylformylglycinamidine cyclo-ligase | -1.04 | 0.0025
DNA-binding protein HU | 1.07 | 0.0027
Putative sulfur carrier protein YeeD | -1.01 | 0.0031
putative quinol oxidase subunit 2 | 1.04 | 0.0033
