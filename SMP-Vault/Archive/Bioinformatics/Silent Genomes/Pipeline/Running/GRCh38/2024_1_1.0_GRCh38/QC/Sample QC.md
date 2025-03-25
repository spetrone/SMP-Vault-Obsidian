/mnt/scratch/SILENT/Act3/QC_Analysis/data/SGP/2024_1_1.0_GRCh38/SNV/pop_vcf

Pop vcf:
/mnt/scratch/SILENT/Act3/QC_Analysis/data/SGP/2024_1_1.0_GRCh38/SNV/pop_vcf/DeepVariant_GLnexus_2024_1_1.0_GRCh38.vcf.gz


(1) Fastq files
	look at multi-QC report
(2) vcf file
	 look at bcftools_stats report
(3) hail_sample_QC
	- add contamination? AB?
	-  flag samples & output in a flagged sample tsv
	- output a sample sex tsv with the f-stat & make sure it is published
(4) relatedness analysis
(5) sample filtering
- samples filtered for QC:
- samples filtered for relatedness: 


Gnomad hard filtering:
- Contamination (mean AB biallelic SNPs) > 1.5%
- Number of singletons > 5000
- Heterozygous: homozygous ratio > 10
- Bases with DP over 1X < 5x107
- Bases with DP over 20X < 4x107
- Proportion chimera > 0.05
- Mean chromosome 20 DP < 10X
- Callrate calculated over high quality sites < 0.8
- https://gnomad.broadinstitute.org/news/2023-11-gnomad-v4-0/

MANUAL:
sex counts (initial dataset)
XX: 377
XY: 219
ratio XY:XX : 0.581
percent: 36.7%

sex counts (filtered): 
XX:305
XY:144
ratio XX:XY: 0.472
percent: 24.2%

Before filtering: