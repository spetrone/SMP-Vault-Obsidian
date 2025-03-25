output vcf from pipeline for chr22: /mnt/scratch/SILENT/Act3/QC_Analysis/data/SGP/2023_1_1.0_GRCh37/pop_vcf/SNV_filtered_frequ_only_22.vcf.bgz'

Liftover using hail
guide here: https://hail.is/docs/0.2/guides/genetics.html#liftover-howto
using chain file in their gs bucket downloaded with gsutil

ibvl chr22 before liftover count:  365442
ibvl chr22 after liftover count:  364518


Gnomad Genomes:
gnomad intersect count: 

SNPs and INDELs
chr 22 concordance: 299382/364518 = 82.13% of IBVL variants are captured in gnomad

SNPs ONLY
ibvl_chr22 after liftover snps count: 285184
gnomad intersect: 252660
SNP concordance: 252660/285184 = 88.60% of IBVL SNPs are captured in gnomad


INDELs only
ibvl chr22 after liftover indels (with is_indel): 74478
ibvl chr22 after liftover indels (complement is is_snp) - then sums to all variants in dataset: 79334
intersect with gnomad v4: 46722
INDEL concordance: 46722/79334 = 58.89% of IBVL SNPs are captured in gnomad (likely not accurate)


Gnomad JOINT:

SNPs and INDELs
ibvl all (after liftover): 364518
intersect with gnomad: 301225
chr 22 concordance: 301225/364518 = 82.64% of IBVL variants are captured in gnomad

SNPs ONLY
IBVL snps: 285184
gnomad intersect: 254397
SNP concordance: 254397/285184 = 


INDELs only

IBVL indels: 79334
intersect with gnomad v4: 46828
INDEL concordance:  46828/79334 = 
