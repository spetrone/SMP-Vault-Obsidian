- relatedness - what are they doing?
- variant QC - filtering metrics - what are they doing?
-
GQ of 20 - assuming that deepvariant modelling is perfect; and setting to 20 as genotyping, and that is a bit higher than he would like
- will see how they change when changing filtering


- what specific files would they like?
	- after our joint calling and after splitting?
	- I will try to also do it 

Somalier - similar Pidi
- runs on set of SNPs and relatedness IBS 2 and IBS0 and makes nice plots 
- KING is probably good too and newer
- good if have known information
- clouds of groups - e.g. siblings, cousins, etc. 
	- particularily with Mauri and population history with bottlenecks etc. so you get a strange cloud  --> can be overlap with cousins - was good to have known pedigree relationships to know where to cut clouds
	- splitting on first degree relations
		- can be difficult to split first and second degree relations
- discrepency with age fo sequencing 

Gnomad

- pop-max - stratified by population 
	- changed to group-max
- split up WES and WGS

GLNexus - can change config number for monoallelics - but probably higher compute time
- can configure for rarist alleles become mono-allelic or the size
- gives allele frequency for them - but if you want to manipulate for other variants, you re-calculate the mono-allelic as well 
	 - get diploid calls on XY - 
- GLNexus config - default - output rarist allele as mono-allelic; but with their modification it becomes the most common allele


- GLNexus bcf 

- it is illegal form BCF tools