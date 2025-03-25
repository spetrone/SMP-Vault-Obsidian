pairs(data, main = "Pairs Plot of Predictors and Response Variable", pch = 21, bg = "lightblue", panel = panel.smooth)
- I assume I will be re-writing all these sections for a full paper
-
- relaxed species code - not separating y forest type - too much noise

- should knowledge gaps be in objective? where to put it?

- abundance vs. relative abundance?

- simply stating effect size and significance - not going into explanation of results - that is discussion only?

- p <=0.05 or put actual p-value? always include p-value? or if it is affected is it assumed, and if not significant, just say that. 

- Repeast statistics section? or re-do that when I re-write methods?

visually - there is a trend

Title - **Effects of Structural Diversity on Lichen Biodiversity in the Boreal Forest of Alberta, Canada**
- components of biodiversity -- too long if I include those? 

**Structural Diversity affects Lichen  Abundance , Species Richness, Diversity,  and Composition in the Boreal Forest**

- index of structural diversity 
- include species four times here?

p = if found
otherwise < 0.0001


- if I have non-significant results, should I include the graph as well? e.g. when I have a 2x2 grid and 1/4 is not significant?

- do i need to provide all the eigenvalues  for every ordination?

- can i have some figures/tables as supplementary?



Make models with 
- make multiple linear mixed model
- dredge function of MuMIn
- then AICc() function to calculate AIC - nparam/
	- compares likelihood of each model given the data and looks for a high likelihood
	- penalizes goodness of fit for model parameters
	- look for lowest AICc
		- will show the best model
	- assess model fit and assumptions


abundance and occupancy 
- linear model  but filter data 


- once for occupacy - reduce dataset to rare species (look at species abundance distribution)
	- then re-do all four 


