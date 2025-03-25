- Not implemented but probably should be
	- variant quality score recalibration or random forest - using ML to find artifactual variants rather than just thresholds
		- VQSR requires a truth training dataset --> don't have that for Indigenous genomes
	- hardy-Weinberg filtering
	- relatedness filtering 
	- inbreeding coefficient filtering
- Contamination:
	- CHARR https://www.biorxiv.org/content/10.1101/2023.06.28.545801v1 



- other methods?
	- trios and Mendelian error rate 
		- try out an example with open data?
	- micro-array data

- Create a truth set and truth data for future version for Indigenous genomes?
	- microarray ?
	- long read sequencing ?
	- trios ?

- needs orthogonal methods, cannot do so via bootstrapping


#### Callset Evaluation
- Two metrics for evaluating the genotyping quality of variants are Hardy-Weinberg equilibrium (HWE) and excess heterozygosity (ExcHet) scores. 
	- (https://www.biorxiv.org/content/10.1101/2022.02.21.481353v1.full) 
- 
### Summary of Current Implementation 
tbd