# Bacterial transcriptomics in LSMMG

## 1. Bacterial strains and conditions
+ _Cronobacter sakazakii_ ATCC 29544
+ _Enterobacter cloacae_ ATCC 13047
+ _Citrobacter freundii_ KCTC 2195

Each strain was cultured in LSMMG (low shear modeled micro-gravity) and NG (normal gravity).  
Replicates 1, 2 and 3 of _C. sakazakii_ and _E. cloacae_ were from [previous RNA-seq result](https://github.com/cmkim1/BRL/blob/main/RNAseq240618.md).  

## 2. Library preparation & Sequencing
+ RNA prep: RNA was extracted using QiAGEN RNA mini-prep kit.
+ Library prep: Zymo-Seq RiboFree® Total RNA Library Kit (Zymo Research).
+ Sequencing: MiSeq, Reagent V3 (300 PE)
+ Actual yield: 14.64GB
+ % PF: 90.50%
+ % >= Q30: 84.53%
    
Species | Condition | Total reads | Total bases (Mbp)
--- | --- | --- | ---
_C. freudii_ | NG1 | 1,690,071 | 1014.0
_C. freudii_ | NG2 | 2,273,462 | 1364.1
_C. freudii_ | NG3 | 2,319,495 | 1391.7
_C. freudii_ | NG4 | 2,097,443 | 1258.5
_C. freudii_ | LSMMG1 | 2,024,698 | 1214.8
_C. freudii_ | LSMMG2 | 2,007,526 | 1204.5
_C. freudii_ | LSMMG3 | 1,454,424 | 872.7
_C. freudii_ | LSMMG4 | 1,476,844 | 886.1
_C. sakazakii_ | NG4 | 1,716,307 | 1029.8
_C. sakazakii_ | LSMMG4 | 1,464,680 | 878.8
_E. cloacae_ | NG4 | 1,902,343 | 1141.4
_E. cloacae_ | LSMMG4 | 2,562,535 | 1537.5

## 3. Adapter trimming, alignment, DEG analyssi  
All processes were conducted in Galaxy server.  
+ Adapter trimming: Trim Galore! (Galaxy Version 0.6.7+galaxy0)
+ Alignment BWA-MEM2 (Galaxy Version 2.2.1+galaxy1)
+ Count: featureCounts (Galaxy Version 2.0.3+galaxy2)
+ DEG analysis: edgeR (Galaxy Version 3.36.0+galaxy4)
+ Reference genomes used: in-lab sequenced genome (_C. freundii_), GCF_000982825.1 (_C. sakazakii_), GCF_000025565.1 (_E. cloacae_)
+ **_C. freundii_ KCTC2195 was identied as _C. braakii_ by result of ANI analysis.**

Genes without more than 5 CPM in at least 2 samples are insignificant and filtered out.  
Non-coding RNAs such as tRNA, rRNA, miRNA, lncRNA were excluded in analysis.



## 4.1 _C. braakii_ in LSMMG  
88 of 4551 (1.93%) genes were filtered out for low expression.
+ Genes were sorted by their differential expression as below.

Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 4463
Upregulated | LogFC > 1 and P-value < 0.05 | 101
Not significant | \|LogFC\| <= 1 or P-value >= 0.05 | 4306
Downregulated | LogFC < -1 and P-value < 0.05 | 56

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
