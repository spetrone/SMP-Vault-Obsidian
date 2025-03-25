Transcription factor:
Promoter: Promoters are specific DNA sequences located near the beginning of a gene. They act as a binding site for RNA polymerase, the enzyme responsible for transcription.

enhancer : They amplify gene expression by binding to specific proteins called transcription factors

TF: A protein that binds to specific DNA sequences.  Can bind to the promoter region itself or to enhancer/silencer regions that can influence the promoter

TOP - To make a conservative assessment of direct binding, we considered a ChIP-seq peak to be bound directly by a TF if the peak overlapped with a GHT-SELEX peak for the same TF, and also contained at least one motif match. In addition, the significance thresholds for all three (ChIP-seq and GHT-SELEX peaks, and PWM hits treated as peaks) were adjusted to maximize the Jaccard value (intersection/union) between all three peak sets; we refer to these as “triple overlap” or TOP sites

![[Pasted image 20241120111452.png]]


TREND:
- Older TFs tend to bdin with older DNA
- - HOWEVER - 

- Evolution of TF binding sites - (1) from new TEs (transposable elements), (2)and from mutations - ancestral DNA
	- dominant for enhancer-binding TFs
	- wanted to see if Codebook TFs evolved from ancestral DNA (rather than transposable elements?)
- method: estimated age of each TOP site for each TF == oldest ancestral genome that contains the entire site (gapless alignment - even if base identities are different)
- Looked and compared ages of different TOP sites for different types of TFs

- RESULTS:

6A - 
Heatmap showing the fraction of TOP sites for each TF dating to different mammalian clades in the human lineage, along with information about the TF category, median age of TOP sites and TFs (million years ago, MYA), and log 10 of total TOP sites.
- SEEMS TO BE SORTED BY TOP SITE AGE

6 B and C - comparison of promoter and dark TF ages - of the TFs and of the TOP sites
6B:
	- TOP sites for Dark TFs (often in TEs == younger) trend younger on average than Promoter (46 vs 72 MYA)
	- still a large overlap & both have binding sites at both extremes (young and old)
6C: age of Dark vs promoter TFs
- estimated the ages of the TFs, using catalogued ortholog and paralog relationships[57](https://www.biorxiv.org/content/10.1101/2024.11.11.622123v1.full#ref-57) and species divergence times

B & C
- age of TFs, both classes, tend to be older than the sites they bind 
	- DARK TF med age: 97 MYA (older than med. age of even the promoter binding sites)
		- 46 MYA median age of TOP sites
	- Promoter TF med age: 429 MYA
		- 72 MYA median age of TOP sites

	- TF binding sites evolve more rapidly - assumes that TFs take on additional regulatory roles -i.e. weaker than expected correlation with binding sites means they likely don't evolve with total specificity to the binding sites




