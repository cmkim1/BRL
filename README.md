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


## 4.1 _C. sakazakii_
+ Genes were sorted by their differential expression as below.


Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 4,319
Upregulated | LogFC > 1 and P-value < 0.05 | 29
Not significant | \|LogFC\| <= 2 or P-value >= 0.05 | 4,270
Downregulated | LogFC < -1 and P-value < 0.05 | 20


### 4.1.1. MDS plot
<img src = "https://github.com/cmkim1/BRL/assets/119988478/36adc56b-cc9f-4939-8ba2-28016f6e40b1" width="60%" height="60%">

+ Dimension1: 22%; Dimension2: 50%


### 4.1.2. MA plot & Volcano plot


<img src = "https://github.com/cmkim1/BRL/assets/119988478/3077f536-40f1-404e-bb46-544811c078f2" width="45%" height="45%"><img src = "https://github.com/cmkim1/BRL/assets/119988478/d1534f83-68ce-4fe8-a814-1405eaf0ec08" width="45%" height="45%" align="right">
+ In volcano plot, genes with absolute value of logFC > 2 and p < 0.05 were considered statistically significant and colored red.


### 4.1.3. DEG Heatmap
<img src = "https://github.com/cmkim1/BRL/assets/119988478/00b0b768-9ce4-4798-920e-d55a3b12da22" width="45%" height="45%" align="right"><img src = "https://github.com/cmkim1/BRL/assets/119988478/9a3a8a77-7c08-4001-aa9d-a99bc509238d" width="27%" height="27%">   
+ Heatmap of significant DEG.
+ Left: average of triplicates; right: all samples.




### 4.1.4. Top 20 differentially expressed genes
<img src = "https://github.com/cmkim1/BRL/assets/119988478/bd9fd9e5-c493-44ed-bdaa-a4e81e0cc080₩">


## 4.2 _E. cloacae_
+ Genes were sorted by their differential expression as below.


Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 5,239
Upregulated | LogFC > 1 and P-value < 0.05 | 54
Not significant | \|LogFC\| <= 2 or P-value >= 0.05 | 5,176
Downregulated | LogFC < -1 and P-value < 0.05 | 9


### 4.2.1. MDS plot
<img src = "https://github.com/cmkim1/BRL/assets/119988478/4e91c3b3-46c2-4acd-8309-7a0b9e6acf75" width="60%" height="60%">

+ Condition1: LSMMG; Condition2:NG
+ Dimension1: 20%; Dimension2: 48%


### 4.2.2. MA plot & Volcano plot  

<img src = "https://github.com/cmkim1/BRL/assets/119988478/68ceea5b-e949-4121-87ab-29197749aeae" width="45%" height="45%"><img src = "https://github.com/cmkim1/BRL/assets/119988478/670fc321-4459-438d-939e-94bf2be04b33" width="45%" height="45%" align="right">  

+ In volcano plot, genes with absolute value of logFC > 2 and p < 0.05 were considered statistically significant and colored red.
   


### 4.2.3. DEG Heatmap
<img src = "https://github.com/cmkim1/BRL/assets/119988478/e61dfac4-4c73-4d8a-899c-4d500cd8b6e3" width="45%" height="45%" align="right"><img src = "https://github.com/cmkim1/BRL/assets/119988478/6db7cd70-57d0-4330-9d76-bc31ee84c01b" width="27%" height="27%">   
+ Heatmap of significant DEG.
+ Left: average of triplicates; right: all samples.



### 4.2.4. Top 20 differentially expressed genes
<img src = "https://github.com/cmkim1/BRL/assets/119988478/c62c01dc-bbea-4371-89a8-8d9fc69e4102">

