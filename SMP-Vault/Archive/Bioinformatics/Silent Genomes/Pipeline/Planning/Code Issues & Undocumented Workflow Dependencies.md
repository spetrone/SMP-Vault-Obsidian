#VCP
- SV/SNV overlap not documented outside of code
	- e.g. line 187 in Hail_Variant_QC.py: 
	-
	`Remove small insertions / deletions (indel) of length > 50bp 
	`Goal : Avoid overlap with the SV pipeline` 

- XX/XY labelling
	- change from 0.2 cutoff to 0.5 to make sure XX not labelled as ambiguous
	- add histogram to show distribution and cutoff during a run

- in SNV_dat_organization.nf --> the chromosome number is not parsed correctly

- Dependency on sample_sex file from SNV in SV subworkflow
	- throughout , comments says\ " sample_sex file can be loaded by user", but it is coded in such a way that, in many layers of the nextflow implementation, it requires taking it from the output of the SNV pipeline; i.e. there is nowhere for a user to "load" the file and would require hours of configuration of the pipeline -- this is not "loading" a file
	  `or file with sample sex can be loaded by user` 

- Undocument and Inconsistent handling of ambiguous sex
	- filters out samples that had sex labelled as ambiguous in SNV in MT & SV subworkflows, but not in SNV subworkflow
		- not filtered out in SNV subworkflow because a patchwork of gnomad methods were used - and gnomad filters out ambiguous sex samples; This pipeline only uses is to create a sample_sex file that is used in the Hail_Variant_QC.py for annotation but not filtering
		- the Sample_Variant_QC.py file has code from gnomad that annotates variant frequencies for sex - this is also the source of the discrepency where some frequencies are not 80 (2 x 40) (*note that in the real data run by Phil, 40 were labelled as ambiguous*)

- HAIL Contig Issue
	- Try/Except blocks should be removed regarding the contig issue with Hail
	- this may be affecting Apache Spark
	- need this to be much cleaner
	- This is an all subworkflows where HAIL imports the vcf file to a matrix table
	
- Why is this removed from variant QC - genotype quality ? line 305 Hail_Variant_QC.py
	 `Adapted from gnomAD to remove adj and population specific`
    
 - Deep Variant
	 - are we doing only bi-allelic?
	- ensure that num-shard is getting the correct value for task-cpus and the full amount of CPU power allocated by slurm is used
	
- remove redundant code - e.g. symbolic links - maybe not after all
-
- In QC - percentages are being used to show how many samples or variants are being filtered but variables are not precise enough and 0.0% is being reported - should be changed to the discrete number rather than a percentage

-----------------------
- RAM for "align_sort_output_bam" also changed for others that may not need as much (and may slow it down or overflow it) - especially Hail_sample_QC.py --> uses a lot of RAM
	- although it may as well match the cpu count --> although I don't think it necessarily haaas to match? and will increase as needed --> perhaps put back to 12 and allow to expand??