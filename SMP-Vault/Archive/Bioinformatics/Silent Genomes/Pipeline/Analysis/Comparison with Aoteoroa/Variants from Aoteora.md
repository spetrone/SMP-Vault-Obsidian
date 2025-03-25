
## Summary of issues:

Bed file:
`chr1	45831779	45831781	#Monoallelic`
`chr1    60541380	60541395	#Repeatthatneedssplittingandsimplifying`  
`chr19   7122375	7123191	#Decompositionerror` 
`chrX	146543960	146543962	#MonoallelicchrX` 


## My analysis
- no spanning deletions in population vcf? --> look into unifying deletions
- look for monoallelic sites - how is hail handling them? how are they being counted in AF, AC, and AN
- Look into overlaps and multi-allelic variants - how is our current splitting method working
- look more deeply into our QC process


note from GLNexus [link](https://www.biorxiv.org/content/10.1101/343970v1.full.pdf ): "We also compared unity of variant representation. The GLnexus pVCF included a higher proportion of sites with multiple alternate alleles (5.9% vs. 4.5%), and a smaller proportion of sites overlapping one or more others (1.5% vs. 2.8%); these differences were mostly due to GLnexus' inclusion of deletions at multiallelic sites, when possible. Monoallelic sites, generated when multiallelic unification was not possible, comprised 0.35% of sites in the GLnexus pVCF, overlapping 1.1% of the primary sites. ""



### "Monoallelic"
- see https://discuss.hail.is/t/import-glnexus-pvcf/2306  --> ./\<some allele> may cause downstream errors in hail (labelled as NA)
	- possible cause for Brad's issue he found in genes file...is process using a vcf rather than hail and some variants are missed because they are labelled as NA in hail?
		- or here: https://github.com/wassermanlab/Variant_catalogue_pipeline/blob/6a47f5f73f1405661e61d7c0173c079b03427e11/modules/Hail_variant_QC.py#L457 
- https://github.com/dnanexus-rnd/GLnexus/issues/210 --> pvcf from GL Nexus - description of mono-allelic - caused by overlapping variants
`chr1	45831779	45831781	#Monoallelic`

HG002
```
CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO	FORMAT	HG002
1	45831779	.	AG	A,<*>	9.7	PASS	.	GT:GQ:DP:AD:VAF:PL	0/1:10:35:15,20,0:0.571429,0:9,0,26,990,990,990
```

HG003
```
#CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO	FORMAT	HG003
1	45831779	.	AG	A,<*>	13.1	PASS	.	GT:GQ:DP:AD:VAF:PL	0/1:13:32:17,14,0:0.4375,0:12,0,24,990,990,990
```

HG004 
```
#CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO	FORMAT	HG004
1	45831779	.	AG	A,<*>	39.5	PASS	.	GT:GQ:DP:AD:VAF:PL	1/1:24:38:1,35,0:0.921053,0:39,24,0,990,990,990
```


Population (trio HG002-4)
```
CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO	FORMAT	HG002	HG003	HG004
1	45831779	1_45831779_AG_A	AG	A	39	.	AF=0.666667;AQ=39	GT:DP:AD:GQ:PL:RNC	./1:35:.,20:.:0,0,0:O.	./1:32:.,14:.:0,0,0:O.	1/1:38:1,35:23:39,24,0:..

```


### "Repeat that needs splitting and simplifying"
`chr1    60541380	60541395	#Repeatthatneedssplittingandsimplifying`  

HG002
```
#CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO	FORMAT	HG002
1	60541376	.	C	<*>	0	.	END=60541381	GT:GQ:MIN_DP:PL	0/0:50:21:0,69,689
```

HG003
```
#CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO	FORMAT	HG003
1	60541353	.	A	<*>	0	.	END=60541389	GT:GQ:MIN_DP:PL	0/0:48:21:0,78,779
```
HG004
```
#CHROM	POS	ID	REF	ALT	QUAL	FILTER	INFO	FORMAT	HG004
1	60541181	.	A	<*>	0	.	END=60541389	GT:GQ:MIN_DP:PL	0/0:50:23:0,75,749
```

Population
this is post splitting:
```
N/A --> does not seem to be called - bad quality maybe?
```
check file pre-splitting!!!

### "Decomposition Error"
`chr19   7122375	7123191	#Decompositionerror` 


### "Monoallelic - chr x"
`chrX	146543960	146543962	#MonoallelicchrX` 