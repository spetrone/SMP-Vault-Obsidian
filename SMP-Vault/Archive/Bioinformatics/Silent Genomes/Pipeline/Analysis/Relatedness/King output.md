```The following parameters are in effect:
                   Binary File :      sgp_37.bed (-bname)

Additional Options
         Close Relative Inference : --related [ON], --duplicate
   Pairwise Relatedness Inference : --kinship, --ibdseg, --ibs, --makeGRM
              Inference Parameter : --degree [4], --noscreen, --seglength,
                                    --minConc [0.80]
         Relationship Application : --unrelated, --cluster, --build
                        QC Report : --bysample, --bySNP, --roh, --autoQC
                     QC Parameter : --callrateN, --callrateM
             Population Structure : --pca, --mds
              Structure Parameter : --projection, --pcs
          Quantitative Trait GWAS : --lmm
                Binary Trait GWAS : --tdt, --gdt
                Association Model : --trait [], --covariate [], --maxP
     Association Method Parameter : --invnorm
               Genetic Risk Score : --risk, --model [], --prevalence, --noflip
              Computing Parameter : --cpus
                   Optional Input : --fam [], --bim [], --phefile [],
                                    --covfile [], --prunedsnp [],
                                    --sexchr [23]
                           Output : --rplot [ON], --pngplot, --plink
                 Output Parameter : --prefix [king], --rpath []

KING starts at Mon Sep  9 17:53:49 2024
Loading genotype data in PLINK binary format...
Read in PLINK fam file sgp_37.fam...
  PLINK pedigrees loaded: 596 samples
Read in PLINK bim file sgp_37.bim...
  Genotype data consist of 26165623 autosome SNPs, 975944 X-chromosome SNPs, 86383 Y-chromosome SNPs, 650 mitochondrial SNPs
  PLINK maps loaded: 27228600 SNPs
Read in PLINK bed file sgp_37.bed...
  PLINK binary genotypes loaded.
  KING format genotype data successfully converted.
Autosome genotypes stored in 408838 words for each of 596 individuals.

Options in effect:
	--related
	--degree 4
	--rplot

Total length of 39 chromosomal segments usable for IBD segment analysis is 2696.4 Mb.
  In addition to autosomes, 2 segments of length 152.1 Mb on X-chr can be further used.
  Information of these chromosomal segments can be found in file kingallsegs.txt

Each family consists of one individual.
Relationship inference across families starts at Mon Sep  9 17:54:56 2024
40 CPU cores are used...
                               Inference ends at Mon Sep  9 17:55:34 2024
  1070 pairs of relatives (up to 4nd-degree) are identified

Relationship summary (total relatives: 0 by pedigree, 1070 by inference)
        	MZ	PO	FS	2nd	3rd	4th
  =========================================================
  Inference	1	0	141	328	600	0


Between-family relatives (kinship >= 0.02210) saved in file king.kin0
  X-Chr IBD-sharing inference saved in file kingX.kin0
--related is done but R code king_relplot.R failed.

  No pedigrees found in the dataset.
KING ends at Mon Sep  9 17:55:35 2024

```