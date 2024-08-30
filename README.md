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
+ Reference genomes used: GCF_904859905.1 (_C. freundii_), GCF_000982825.1 (_C. sakazakii_), GCF_000025565.1 (_E. cloacae_)

Genes without more than 5 CPM in at least 2 samples are insignificant and filtered out.  
Non-coding RNAs such as tRNA, rRNA, miRNA, lncRNA were excluded in analysis.



## 4.1 _C. freundii_ in LSMMG  
1105 of 4909 (22.51%) genes were filtered out for low expression.
+ Genes were sorted by their differential expression as below.

Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 3,804
Upregulated | LogFC > 1 and P-value < 0.05 | 99
Not significant | \|LogFC\| <= 1 or P-value >= 0.05 | 3,648
Downregulated | LogFC < -1 and P-value < 0.05 | 57

### 4.1.1. MDS plot & MD plot
<img src = "https://github.com/user-attachments/files/16814179/mdsplot_Gravity.pdf" width = "45%" height = "45%"><img src = "https://github.com/user-attachments/files/16814137/mdplot_LSMMG-NG.pdf" width = "45%" height = "45%" align = "right">

### 4.1.2. Top 20 DEG tables
Product | logFC | P value
---- | ---- | ----
chaperone NapD | 3.75 | 0.0075
nitrate reductase catalytic subunit NapA | 3.23 | 0.0465
NADPH-nitrite reductase large subunit | 3.1 | 0.0249
ferredoxin-type protein NapF | 3.04 | 0.0285
ferredoxin-type protein NapG | 2.97 | 0.0376
nitrate reductase cytochrome c-type subunit | 2.96 | 0.0382
quinol dehydrogenase ferredoxin subunit NapH | 2.87 | 0.0394
pseudouridine kinase | 2.6 | 0.0481
trimethylamine-N-oxide reductase 2 | 2.56 | 0.0053
universal stress protein UspF | 2.49 | 0.0234
galactose/glucose ABC transporter substrate-binding protein MglB | -3.78 | 0.0207
fatty acid oxidation complex subunit alpha FadB | -3.26 | 0.0114
maltose/glucose-specific PTS transporter subunit IIBC | -2.78 | 0.013
diaminopimelate decarboxylase | -2.05 | 0.0315
acyl-CoA dehydrogenase FadE | -2.02 | 0.0057
bifunctional 2-methylcitrate dehydratase/aconitate hydratase | -1.89 | 0.0293
class 1 fructose-bisphosphatase | -1.85 | 0.0074
Fe-S cluster assembly transcriptional regulator IscR | -1.84 | 0.0016
purine nucleoside transporter PunC | -1.79 | 0.001
YgdI/YgdR family lipoprotein | -1.75 | 0.0217



