# Bacterial transcriptomics in LSMMG

## 1. Bacterial strains and conditions
+ _Cronobacter sakazakii_ ATCC 29544
+ _Enterobacter cloacae_ ATCC 13047

Each strain was cultured in LSMMG (low shear modeled micro-gravity) and NG (normal gravity).


## 2. Library preparation & Sequencing
+ RNA prep: RNA was extracted using QiAGEN RNA mini-prep kit.
+ RNA library prep: rRNA-depleted total RNA library was prepared using Zymo-Seq RiboFree® Total RNA Library Kit (Zymo Research).
+ Sequencing: MiSeq, Reagent V3 (300 PE)
+ Actual yield: 14.57GB
+ % PF: 92.42%
+ % >= Q30: 88.98%

Species | Condition | Total reads | Total bases (Mbp)
--- | --- | --- | ---
_C. sakazakii_ | NG1 | 4,486,016 | 1350.2
_C. sakazakii_ | NG2 | 3,365,112 | 1012.8
_C. sakazakii_ | NG3 | 3,126,258 | 941
_C. sakazakii_ | LSMMG1 | 3,735,600 | 1124.4
_C. sakazakii_ | LSMMG2 | 4,085,134 | 1229.6
_C. sakazakii_ | LSMMG3 | 4,476,162 | 1347.2
_E. cloacae_ | NG1 | 3,413,308 | 1027.4
_E. cloacae_ | NG2 | 3,290,360 | 990.2
_E. cloacae_ | NG3 | 3,810,916 | 1147.0
_E. cloacae_ | LSMMG1 | 3,884,188 | 1169.0
_E. cloacae_ | LSMMG2 | 4,456,352 | 1341.2
_E. cloacae_ | LSMMG3 | 3,347,922 | 1007.6


## 3. Read adapter trimming & alignment
+ Adapter trimming and alignment were conducted in Galaxy server [workflow](https://usegalaxy.org.au/u/cmkim/w/copy-of-deg-from-bacterial-rna-sequecing-result)
+ Trim Galore! (Galaxy Version 0.6.7+galaxy0) was used.
+ Trmmed reads were aligned to reference genome by BWA-MEM2 (Galaxy Version 2.2.1+galaxy1).
+ Reference genomes used: GCF_000982825.1 (_C. sakazakii_), GCF_000025565.1 (_E. cloacae_)


## 4. DEG analysis
+ DEG analysis was carried out using edgeR, as described in [here](https://github.com/igchoi/IBT618-SystemsBiotechnology/tree/main/2024-spring/msan) with a few modifications.
+ non-coding RNAs such as tRNA, rRNA, miRNA, lncRNA were excluded in analysis.
+ **Condition1: LSMMG; Condition2:NG**


### 4.1 _C. sakazakii_
+ Genes were sorted by their differential expression as below.


Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 4,319
Upregulated | LogFC > 1 and P-value < 0.05 | 61
Not significant | \|LogFC\| <= 2 or P-value >= 0.05 | 4,173
Downregulated | LogFC < -1 and P-value < 0.05 | 85


### 4.1.1. MDS plot
<img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/7e90fe0d-6f53-4ae3-9b33-a002bebbeec9" width="60%" height="60%">

+ Dimension1: 22%; Dimension2: 50%


### 4.1.2. MA plot & Volcano plot
+ In volcano plot, genes with absolute value of logFC > 2 and p < 0.05 were considered statistically significant and colored red.

<img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/32769426-f39e-4277-a914-6e6cfb8d0630" width="45%" height="45%" align="left"><img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/19a8fc04-9129-4d39-9d38-1ab4345ad4b5" width="45%" height="45%" align="right">



### 4.1.3. Top 20 differentially expressed genes
<img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/67fd02b9-665f-42d3-bd54-e848a4ad645c">


### 4.2 _E. cloacae_
+ Genes were sorted by their differential expression as below.


Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 5,239
Upregulated | LogFC > 1 and P-value < 0.05 | 51
Not significant | \|LogFC\| <= 2 or P-value >= 0.05 | 5,052
Downregulated | LogFC < -1 and P-value < 0.05 | 136


### 4.2.1. MDS plot
<img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/9642f331-521d-4126-9fe2-2f5bb4566060" width="60%" height="60%">

+ Condition1: LSMMG; Condition2:NG
+ Dimension1: 20%; Dimension2: 48%


### 4.2.2. MA plot & Volcano plot  
+ In volcano plot, genes with absolute value of logFC > 2 and p < 0.05 were considered statistically significant and colored red.
<img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/7d093732-702e-43bd-8c25-798f5edde33a" width="45%" height="45%" align="left"><img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/dec4efbc-c052-4062-a456-da916bb7376d" width="45%" height="45%" align="right">  
   
   
   
### 4.2.3. Top 20 differentially expressed genes
<img src = "https://github.com/cmkim1/BRL-RNA-sequencing/assets/119988478/b10f3815-2798-4bf9-af62-dbb30a03e226">

