novelty
- lichen-specific index
- correlate indices
	- relax covariates to compare with other indices
	- structural diversity as a proxy - but then need to look at disturbance
- more species - bryophytes
- red-listed species
	- to conserve for the most
- functional groups of lichen
- forest structure vs forest type
- basic ecology
	- precision between relationship
		- structural attributes
		- parameterizing the relationship
			- shape of relationship
		- are there thresholds

- exclude genus from richness
	- but include ONLY in abundance
- exclude from composition 


- mix-model with random factor for quadrants
	- for linear regression 
- for multi-variate
- PERMANOVA 
- test for spatial auto-correlation

lme4

model1 <- glmer(lichen_richness$response~structural_div ) + (1|site)


okay to just do visualization and get pattern; can only do p-value if I have time

lichen species:
![[Pasted image 20250227005716.png]]



TO DO
- remove genus listings from data (except abundance)
- - higher levels of structural diversity are where increases in lichen diversity are most significant

-re-state objective
- make sure they are clear and well-ordered
- make sure to follow the same order throughout




**Objectives:**
1. Determine the effect of forest structural cdiversity on lichen species richness,  species diversity (Hill numbers for Shannon and Simpson Diversity indices), species abundance, and species composition. 
2. Assess the effectiveness of a general forest inventory index for showing the relationship between structural complexity and lichen diversity
3. Determine the most important structural attributes associated with lichen diversity
	1. inform the creation of a lichen-specific structural diversity index and test that index
4. Determine the relative effects of structural diversity between aspen, mixedwood, and coniferous stands
5. Determine a threshold for structural diversity
	1. based on index
	2. determine link to specific attributes
