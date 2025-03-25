Done with GIAB samples HG002-4


### 1. Hap.py Benchmarking on Individual Samples

 a. with default xcmp
 b. with vcfeval (reccommended)

on GPCC:
HG002-4_GRCh38_2.0 - no option for bwa mem 
HG002-4_GRCh38_3.0 - -k 23 for bwa mem

Summaries are available in directories, found under here:

	/mnt/scratch/SILENT/Act3/QC_Analysis/variant_analysis/benchmarking 

##### Summary 

![[Pasted image 20240909171555.png]]


### 2. bcftools intersect comparison of aggregate vcf
- done after GL nexus after the bcftools norm step

Location:
```/mnt/scratch/SILENT/Act3/QC_Analysis/variant_analysis/benchmarking/2.0_3.0_comparison/results ```

##### Count summary of private and shared variants:

0000.txt - private to HG002-4_2.0 : **10537**
0001.txt - private to HG002-3_3.0 : **11253**
0002.txt and 0003.txt - shared by both runs:  **6527229**

furhter - could benchmark against eachother