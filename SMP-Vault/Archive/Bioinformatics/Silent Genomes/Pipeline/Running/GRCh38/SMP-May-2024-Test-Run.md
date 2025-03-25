#VCP
Information:

### Input Data
genomes source:

genome IDs:


### Run Notes

- Issue with hail version, changed to hail2 (newer version?)

- contig naming issue with HAIL --> GRCh38 vcf is using GRCh37 contig naming
	- used this information to recode when first loading matrix table:
	- https://discuss.hail.is/t/locus-erring-about-the-wrong-reference-genome/1013/13 
	- Import a VCF with GRCh38 as the reference genome that incorrectly uses the contig names from GRCh37 (i.e. uses contig name “1” instead of “chr1”).
	- from https://hail.is/docs/0.2/methods/impex.html#hail.methods.import_vcf :

>>> 		`recode = {f"{i}":f"chr{i}" for i in (list(range(1, 23)) + ['X', 'Y'])}`
>>> 		`ds = hl.import_vcf('data/grch38_bad_contig_names.vcf', reference_genome='GRCh38', contig_recoding=recode)



Attempt 1

	Use chr = {... with chr} 
	
	Apply recode = {f"{i}":f"chr{i}" for i in (list(range(1, 23)) + ['X', 'Y'])}

Attemp 2

- same as attempt one but only SNV subworkflow

- added “MT”:”chrM”, to recoding

Now in try block: `{ “MT”:”chrM”, **{f"{i}":f"chr{i}" for i in (list(range(1, 23)) + ['X', 'Y'])} }`


- MT sub-workflow had error with hail - could not read file - because the sample_sex file had not been created yet from the SNV sub-workflow. 
	- I commented out the MT and SV workflow and resumed the SNV subworkflow - and debugged it and ran it until completion
	- after then resuming the MT subworkflow I noticed that the cache was not totally accurate (said that the SNV subworkflow was not complete when it was) - this is bad use of nextflow - having to comment out code and use resume for flow control, could cause unexpected behaviour
	- once the sample_sex file was created, the MT subworkflow completed without errors


- file name parsing issue with hard-coded file names caused VCF files to not be opened by R in the data organisation settings
	- changed: **- SNV_data_organization.nf, SNV_data_organization.R
    
	- Issue: the chromosome number was not being parsed correctly, and so the fread(gfile) function call was being passed a correct file name
	    
	- Fix: created a testing space on local machine - used GREP instead of sed to parse chromosome number from .vcf file
	    
	- Altered the two scripts (listed above), so that the .nf uses the new parsing code and passes the chromosome number, and the R script uses it as an argument (args[2]).**