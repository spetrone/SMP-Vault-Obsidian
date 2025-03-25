In our data
- stretches of variants that seem misaligned
- our reference, no alt contigs
	- have some decoy sequences & unmapped contigs
- they pre-process with fastp
	- filters reads
	- default
	- low quality trimming
- Kraken-filtere - some human sequences are filtered out
- haplo-type aware (only X and Y)

Sommalier
- check into our age lmit
- the Sommalier snps make Mauri look more closely related by increasing IBS2 but not decreasing IBS0, likely due to population bottlenecks
- RTG-vcfeval - doesn't like indels
		- reference overlap
		- represents variants in both missing and present, and so in both false negative and false positive