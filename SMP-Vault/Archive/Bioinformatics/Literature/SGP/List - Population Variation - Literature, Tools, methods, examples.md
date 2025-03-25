
## Literature

Multi-allelic Variants:
1. [ Multiallelic Positions in the Human Genome: Challenges for Genetic Analyses](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4752396/)

Benchmarking
1. [ Best Practices for Benchmarking Germline Small Variant Calls in Human Genomes](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6699627/)
2. [Truth Challenge V2: Calling Variants from Short and Long Reads in Difficult-to-Map Regions](https://precision.fda.gov/challenges/10#datasets) 
3. [Benchmarking challenging small variants with linked and long reads](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9706577/) 


Pipelines, best practices and filtering
1. [Best practices for variant calling in clinical sequencing](https://genomemedicine.biomedcentral.com/articles/10.1186/s13073-020-00791-w)
2.  [Accurate, scalable cohort variant calls using DeepVariant and GLnexus](https://academic.oup.com/bioinformatics/article/36/24/5582/6064144) 
3.  [Variant interpretation using population databases: Lessons from gnomAD](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC9160216/#:~:text=Variants%20reported%20in%20gnomAD%20have,the%20variant%20and%20the%20site.) 
4. [ Effective variant filtering and expected candidate variant yield in studies of rare human disease](https://www.nature.com/articles/s41525-021-00227-3)
5. [ ForestQC: Quality control on genetic variants from next-generation sequencing data using random forest](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6938691/)
6. [Best practices for evaluating single nucleotide variant calling methods for microbial genomics](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4493402/)
7. 

contamination:
1. [CHARR efficiently estimates contamination from DNA sequencing data](https://www.biorxiv.org/content/10.1101/2023.06.28.545801v1)

Sex Imputation 



## Tools:
#### DeepVariant
- [Docs home](https://github.com/google/deepvariant/tree/r1.6.1/docs)
- [Best Practices for Cohorts]()
- Hap.py 
	- ROC plots
	- normalization 
#### Benchmarking 
Overview (GA4GH) -  https://github.com/ga4gh/benchmarking-tools/tree/master 
	- comparison methods and performance metrics definitions: https://github.com/ga4gh/benchmarking-tools/blob/master/doc/standards/GA4GHBenchmarkingPerformanceMetricsDefinitions.md 
#### GLNexus
- read up on population vcfs and GLNexus process for complex variants:
	- https://www.biorxiv.org/content/10.1101/343970v1.full.pdf 

## Methods
#### Gnomad
	v. 2.1
	v. 3.0
	v. 3.1
	v. 4.0 : https://gnomad.broadinstitute.org/news/2023-11-gnomad-v4-0/ 
	- general:
		- variant QC: http://gnomad-sg.org/help/variant-qc 

#### Variant Filtering & QC
[Evaluating the quality of a germline short variant callset](https://gatk.broadinstitute.org/hc/en-us/articles/360035531572-Evaluating-the-quality-of-a-germline-short-variant-callset) - gnomad documentation

[(How to) Filter variants either with VQSR or by hard-filtering](https://gatk.broadinstitute.org/hc/en-us/articles/360035531112--How-to-Filter-variants-either-with-VQSR-or-by-hard-filtering)


***WHAT IS USED IN Gnomad V4.0***
[Allele-specific annotation and filtering of germline short variants](https://gatk.broadinstitute.org/hc/en-us/articles/360035890551-Allele-specific-annotation-and-filtering-of-germline-short-variants) 

Explanation of callset evaluation and filtering:
https://qcb.ucla.edu/wp-content/uploads/sites/14/2016/03/IntroductiontoVariantCallsetEvaluationandFilteringTutorialAppendix-LA2016.pdf 

