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

## 4.1 DEGs in LSMMG  
Genes were sorted by their differential expression as below.
Genes without more than 1 CPM in at least 6 samples are insignificant and filtered out.
64060 of 73732 (86.88%) genes were filtered out for low expression.

Category | LogFC (Treated/Control) | Count
---- | ---- | ----
Total protein-coding genes | - | 9,672
Upregulated | LogFC > 1 and P-value < 0.05 | 312
Not significant | \|LogFC\| <= 1 or P-value >= 0.05 | 9,304
Downregulated | LogFC < -1 and P-value < 0.05 | 56

### 4.1.1. MDS plot & MD plot
<img src = "https://github.com/user-attachments/files/19314515/mdsplot_Gravity.pdf" width = "45%" height = "45%"><img src = "https://github.com/user-attachments/files/19314544/mdplot_LSMMG-NG.pdf" width = "45%" height = "45%" align = "right">

### 4.1.2. Top 20 DEG tables
Product | logFC | P value
---- | ---- | ----
hypothetical protein | 6.95 | 0.00017
hypothetical protein | 5.85 | 0.01564
Aldehyde-alcohol dehydrogenase | 5.75 | 0.047
Aldehyde-alcohol dehydrogenase | 5.51 | 0.02439
hypothetical protein | 5.36 | 0.00016
Aldose 1-epimerase | 4.77 | 0.03956
Amylosucrase | 4.35 | 0.00056
Putative universal stress protein | 4.18 | 0.00232
hypothetical protein | 3.95 | 0.0007
hypothetical protein | 3.86 | 0.00119
PTS system lactose-specific EIICB component | 3.8 | 0.02627
PTS system lactose-specific EIICB component | 3.72 | 0.00907
Putative universal stress protein | 3.72 | 0.00091
Elongation factor P | 3.67 | 0.02533
hypothetical protein | 3.66 | 0.00152
Elongation factor G%2C mitochondrial | 3.65 | 0.00284
Redox-sensing transcriptional repressor Rex | 3.65 | 0.00139
Chromosome partition protein Smc | 3.64 | 0.00233
hypothetical protein | 3.64 | 0.00373
hypothetical protein | -3.61 | 0.03999
