# Bacterial metatranscriptomics in LSMMG

## 1. Samples and conditions
+ Stool samples from adult.

3 replicates of stools samples were cultured in rich medium supplemented with 2-fucosyllactose (2`-FL) in LSMMG (low shear modeled micro-gravity) and NG (normal gravity).  

## 2. Library preparation & Sequencing
+ RNA prep: RNA was extracted using QiAGEN RNA mini-prep kit.
+ Library prep: Zymo-Seq RiboFree® Total RNA Library Kit (Zymo Research).
+ Sequencing: MiSeq, Reagent V2 (150 PE)
+ Total reads: 13,212,487
+ % PF: 98.131%
+ % >= Q30: 94.53%
    
Sample | Condition | Total reads | Total bases (Mbp)
--- | --- | --- | ---
Stool cultured with 2`-FL | NG1 | 2,067,933 | 620
Stool cultured with 2`-FL | NG2 | 2,297,703 | 689
Stool cultured with 2`-FL | NG3 | 2,574,131 | 772
Stool cultured with 2`-FL | LSMMG1 | 2,112,949 | 634
Stool cultured with 2`-FL | LSMMG2 | 2,215,642 | 665
Stool cultured with 2`-FL | LSMMG3 | 1,944,138 | 583

## 3. Assembly, alignment, DEG analysis  
All processes were conducted in Galaxy server.  
Whole reads were assembled to make transcript contigs and used as reference sequences.
+ Assembly: rnaSPAdes (Galaxy Version 3.15.5+galaxy3)
+ Annotation: Prokka (Galaxy Version 1.14.6+galaxy1)
+ Alignment: BWA-MEM2 (Galaxy Version 2.2.1+galaxy1)
+ Count: featureCounts (Galaxy Version 2.0.3+galaxy2)
+ DEG analysis: edgeR (Galaxy Version 3.36.0+galaxy4)

## 4.1 Gut microbiome in LSMMG  
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
