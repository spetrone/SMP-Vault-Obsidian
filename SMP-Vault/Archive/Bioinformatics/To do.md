
 



list of improvements
- check for aneuploidy
- genotype level filtering
- splitting pipeline
- reference genome
- mono-allelic variants
- re-run PAR region

- remove single NA from genes table --> don't know why it is there still ahhahahah
- add benchmarking info to documentation
-


VARIANT ANALYSIS
- compare to gnomad + make figures
- run filtering capacity calculations

- remove SOPs from Confluence

- look at file headers for IDs, or look at metadata file

- see how many of the ibvl variants will have a gnomad flag
- look into PAR liftover Y --> X
- are detailed protocols - methods?

- Documentation !!!
	- Data: what has been done to the data
	- Process/Pipeline:
		- explanation 
		- improvements 
		- problems
- organize files
	- QC analysis
	- indigenous vcf from relatedness
	- relatedness analysis files (delete old files too)


VARIANTS


- MONO-ALLELIC --> see what GLNexus is using to calculate AN and therefore AF, because it looks like it is doing something more sophisticated than setting all NAN genotypes to ref and calculating too low of an AF - perhaps using the counts of the other variant calls around that locus when making the mono-allelic call.
	- must make sure though, if keeping it, that it does not get over-ridden at later stages (e.g. with hail's built-in function ), because then the AF will be 1 because AC == AN when calculated from genotypes (GLNexus leaves out this information, just addes MONO-ALLELIC flag)




 - move /mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/KING/plink_analysis/sgp_37_bi_snp.vcf.gz to /mnt/scratch/SILENT/Act3/QC_Analysis/relatedness/data/2023_1_1.0_GRCh37/ and add to readme
 

 - write script for GL nexus for each sub pop


- process other populations with GLNexus
	-  - write script for QC for each sub pop?
	- deg 1 filtered populations?



ADMIN

- investigate AF 0.95 - 1.0 peak - may be from rare allele on reference
- make visualization of novelty in IBVL vs gnomad for clinical analysus (done for new sampling)

- checksum fastq files
- delete fastq files
- checksum important vcf files


- find CPU hours for 20 genomes





WRITING
- Compile papers
- Compile References
- Install Zotero
- start draft



 - update documentation on variant calling in run docs
- visualize KING PO relationships
- visualize KING inference

- make Indigenous data tracking sheet - STARTED

- - Deepvariant XY issue
	- TEST new deepvariant
- will I need to have an aggregate vcf without relatives filtered out

- need for data:
	- BAM for verifying data 
	- vcf for GLNexus re-run & for analysis of db coverage

- install and test Truvari

- Make figures for paper
	- stats on variants
	- compare to gnomad & popDB's
- download gnomad v4.0
- - checksum work files ---> postponed until after run




Manage V38 Run
- Document benchmarking with -k 23 and our current process
	- look into ROC plots
- document findings for variants (here in Obsidian)

Changes for pipeline run
- publish the tsv with both sample sex AND F-stat, AND publish the sample_sex file (without the F-stat)
- - change code in hail_sample_QC to report the list of samples removed not just the count
- Change variant QC to show tables for each chromosome (or run it for entire )
- - update pipeline to publish aggregate vcf


-----------------------------------------------------------------------


- Variant & Sample QC
	- look into splitting complex multi-allelic variants after GLNexux
		- try hail?
		- look at xcmp from Hap.py?
	- make plan for XY issue


- SOPs, methods, & Documentation

	1. Nextflow and pipeline management
		1. caching
			1. + what to do if cache breaks
				1. try to fix
				2. if fully broken - how to proceed
	2. Document each tools & parameters 
		1. put in more in-depth flow diagram
	3. Summarize aggregation steps in more detail, especially QC

	

- Look into determining if a variant comes from a region that has poor map-ability 




DONE
- pull pipeline development out of pipeline data processing in flow diagram
	- partly done - pulled out but SDE part not implemented yet
- create sheet for tracking Indigenous data
- - Verify the Fastq files
-  - add gnomad v4.1 to GPCC 
-  - Inform team about filtered gnomad variants in the genomic gnomad files (e.g. 22_16053758_G_A has filter "RF" == Random Forest)
	- `awk '{print $7}' gnomad_frequency_table_chr22.tsv | sort | uniq -c
- - create GIAB test data - filtered and unfiltered
- test QC script for X and Y
- look into output vcfs
- change pipeline for changes and new outputs
	- remove "output" for outputted files so it works with the pipeline publishing
- add filter step for hail sample QC - in nf part - done already in script with run option/arg
- test on full-size dataset - for autosomal
`
-  - calculate contribution with SNPs only - #Calculate SNPs only
ibvl_snps = ht.filter(hl.is_snp(ht.alleles[0], ht.alleles[1])) 
 - Check GLNexus Filter column - filter out not passed needed? or already done? - only filter is monoallelic
- figure out how to pass files to annotation .nf workflow, so they are in their own directories for autosomal

- RELATEDNESS
 -  - relatedness with multi-allelics filtered out instead of split
 - create sample quality ranking file --> probably will not do
 - calculate new maximal independent set
	 - visualize and verify
	 - run with built-in function and compare
VARIANT QC
- apply AC0 filter:
	- - AC0: No sample had a high quality genotype at this variant site (GQ>=20, DP>=10 and allele balance > 0.2 for heterozygotes) (gnomad v4)
-  - manually check filtered samples
	 - manually select samples to filter or manually set the criteria
- - set Y-non par to no_call for XX samples

- - publish additional files in pipeline
	- glnexus output 
		- create additional vcf.gz out of the bcf too?: -- DONE it bcf to vcf - creates an additional file.
	- tsv file in sample_qc with f-stat -DONE
	- also publishing .txt files

- QC ANALYSIS
- re-do QC script for variants - hard filtering
- adjust sample QC as needed - LOOK AT DATA


- - add "FILTER", "exomes_filters", "genomes_filters" to codebase for gnomad table

- make sure changes have been made in it for genes, transcripts (refseq)
- run it
- then push to github, pull and re-run on GIAB data (version 7.0) on filtered data

- Add sequencing QC to run documentation for 2024_1_1.0_GRCh38
- Add documentation pages for 2024_1_1.2_GRCh38

- document that MT is unfiltered

- change gnomad in code


- use v4.1 gnomad?
	- joint gnomad tables - change headers to remove "joint" from AF, AC, AN, nhom_alt
	
RELATEDNESS
- visualise family clusters - 1st and also one with 2nd and 3rd degree relatives
- REPORT & document final analysis when done

DOUBLE CHECL:
(after stratification step, index 0 is alt allele for whole population) ????
e.g. no variants: SNV_mt_var_filtered.info.AC_tot_XX_XY[0] == 0? 
--> RERUN autosomal with this fix (was [1] before which was only AC==0 for XX samples)
--> remove the output directory name and output files to current directory

 -
 - XX samples: 
	 -  set Y values to NAN for all XX samples
	 - PAR Regions - BAD
- XY samples:
	- PAR regions BAD
	- set Y non-par and X non-par to haploid
 - Fix deepvariant ploidy issue
-  - check bams --> pars poorly mapped
 - check vcf --> NO PAR calls
 - - Download gnomad v4.0 - done for matrix tables
 - 

- make changes to data QC documentation SOP - done - double check
- organize and backup files (glnexus output) for 2023_1_1.0_GRCh37??
- run 2024_1_1.2_GRCh38
- - finish SOPS
- - document 2024_1_1.2_GRCh38
- - put king version in documentation  KING 2.3.2
- - delete deepvariant intermediate files,

- - merge dev branch with main --> first consolidate commits


- Add documentation pages for  2024_1_1.2_GRCh38

- make sure to report to vcf files published (DOCUMENTED)
	- pop vcf - pre-normalization and post normalization
	- indels > 50bp - from hail
	- autosomal post-hail
- describe processes and methods added
- create improvement sheet
- ensure 2024_1_1.1_GRCh37 is backed up
-  re-analyze data
- email Brad nad wyeth about crashing process and include error log path
-  document deleting deepvariant intermediates in pipeline documentation
command:
- delete files
-