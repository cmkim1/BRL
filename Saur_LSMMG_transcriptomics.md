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

## 3. Adapter trimming, alignment, DEG analyssi  
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
<img src = "https://github.com/user-attachments/files/17375120/mdsplot_Gravity.pdf" width = "45%" height = "45%"><img src = "https://github.com/user-attachments/files/17375123/mdplot_LSMMG-NG.pdf" width = "45%" height = "45%" align = "right">

### 4.1.2. Top 20 DEG tables
Product | logFC | P value
---- | ---- | ----
Chaperone NapD | 3.81 | 0.0086
L-arabinose isomerase | 3.69 | 0.0125
Nitrite reductase [NAD(P)H] | 3.11 | 0.0295
Ferredoxin-type protein NapF | 3.07 | 0.0322
Periplasmic nitrate reductase, electron transfer subunit | 2.97 | 0.0439
Ferredoxin-type protein NapG | 2.97 | 0.0443
Ferredoxin-type protein NapH | 2.88 | 0.0455
Trimethylamine-N-oxide reductase 2 | 2.61 | 0.0066
Universal stress protein F | 2.53 | 0.0273
Nitrite reductase (NADH) small subunit | 2.34 | 0.0085
D-galactose-binding periplasmic protein | -3.75 | 0.0207
Fatty acid oxidation complex subunit alpha | -3.22 | 0.0114
PTS system maltose-specific EIICB component | -2.73 | 0.0136
Diaminopimelate decarboxylase | -2.17 | 0.0281
2-methylcitrate dehydratase | -2.1 | 0.0197
Acyl-coenzyme A dehydrogenase | -1.98 | 0.0078
2-methylcitrate synthase | -1.88 | 0.0418
HTH-type transcriptional regulator IscR | -1.85 | 0.0025
Fructose-1,6-bisphosphatase class 1 | -1.81 | 0.01
Inner membrane transport protein YdhC | -1.78 | 0.0017
