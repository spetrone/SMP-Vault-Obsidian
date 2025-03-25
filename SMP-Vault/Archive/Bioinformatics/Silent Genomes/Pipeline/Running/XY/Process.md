1. Extract reads from BAM to Fastq
	1. Samtools fastq 
	2. or GATK PrintReads??
	
2. scramble the reads (mapping tools expect random order?)
3. Create a masked reference genome, with all except the X-region PAR masked
4. Map to the masked reference genome
5. cut and paste PAR regions of BAM files (X and Y only)
	1. remove Y non-par from XX samples
	2. remove all Y PAR reads from old BAMS
6. use Deepvariant haploid-aware 1.6.1 and re-call chromosomes X and Y
7. 