
Updates

(1) Pipeline is running!
- on 3 nodes only; issues with dev_q configuration that prevents Singularity from working
	- have asked not to alter queue while running --> happened during a test run and destroyed the cache
- changed an option with bwa mem after benchmarking to -k 23 --> slight improvement re: recall, precision, and speed

(2) Benchmarking Analysis done
 - done with Hap.py using the vcfeval engine, it was quite good
 - followed their best practices for benchmarking 
 - done on HG002-4 and compared against the truth set

(3) Looking into variants
- looking at Aoteoroa's data 
- looking into our data
- doing a deep dive into hail to look into ways to address issues with variants and how they are split
- also doing deep dive into our tools, specifically GLNexus, the population vcf and its format, and how we are splitting variants. This is on-going
	- need to normalise
	- probably should split differently
- X-chromosome issue
	- Variome using black box to tackle black box
	- might try addressing this with hail, less opaque of a process
- Our QC --> hard filtering only; NEEDS relevant truthset and/or trios to do more in-depth QC processes; would like to improve it. 




---------------------------------------------
- will meet with Australian and Variome group
- SGRDDC meeting mid-Sept

--------------------------------------------------------------------- 

Priorities
(1) SVs
- have a solid, well-documented pipeline
- QC
(2) Long read - presenting it to governance committees 
(3) Publication
	(a) Silent Genomes Publication - small technical piece
	(b) 