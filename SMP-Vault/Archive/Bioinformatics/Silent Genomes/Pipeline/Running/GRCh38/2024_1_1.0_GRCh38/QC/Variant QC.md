- POSSIBLE source of AF increase from 0.95 to 1.0 --> the sites adjacent (causing) the mono-allelic sites, end up with an increased allele frequency when the mono-allelic samples (those carrying the mono-allelic) end up with no call at the adjacent site.

(a) variant QC report from bcftools stat:
	location
(b) variant QC with hail
	- AC0 variants - method
	- report how many filtered
	- filter out AC and AN of 0 - from when samples are removed
(c) mono-allelic
	- report number and variants
	- fix AF and AN
(d) can I add a filter field without messing up downstream scripts?
	- yes add to filter field
(e) XX - non-par set to no call
	- report min, max, mean for all XX samples
(f) HWE - with plink cutoff - 10^-47
(g) genotype-level filtering?
	- GQ, DP, AB


Gnomad:
In addition to VQSR, we also applied the following hard filters: 

- AC0: No sample had a high quality genotype at this variant site (GQ>=20, DP>=10 and allele balance > 0.2 for heterozygotes)
- InbreedingCoeff: there was an excess of heterozygotes at the site compared to Hardy-Weinberg expectations using a threshold of -0.3 on the InbreedingCoefficient metric.

----
MANUAL METRICS
(* includes calls for reference - not just variants)
Genotype quality:
Number of called genotypes: 12231149738

GQ < 20
Count of genotypes with GQ < 20 : 897585773
Percentage of genotypes with GQ < 20:  7.34%

GQ < 15
Count of genotypes with GQ < 15 : 737712610
Percentage of genotypes with GQ < 15: 6.03%

GQ < 10
Count of genotypes with GQ < 10 : 580828247
Percentage of genotypes with GQ < 10: 4.74%

----
SITES
---- 
Total sites: 28331605

AC0 : here No sample had a high quality genotype at this variant site  (GQ>=20, DP>=10 and allele balance > 0.2 for heterozygotes)
count AC0 sites whole genome: 506175
percentage: 1.787%



--------------------------------------------------
### X and Y chromosomes, XX vs XY Samples

X chromosome:
XX-non-par genotypes called: 276,768,558
XY-non-par genotypes called: 130,312,021


Y chromosome:
XX-non par genotypes called: 23,643,886
	-mostly AD of 0 - think it is a result of improper handling of Deepvariant and GLNexus -- will be setting to 0
XY-non-par genotypes called: 11,572,116


HAPLOTYPE BOXES