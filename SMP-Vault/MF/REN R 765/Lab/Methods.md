Forestry toolbox in excel 
there is a user guide
https://fgrow.ca/publications/forestry-toolbox-excel-add


1. Sampling
- maximize uniformity of distance between plots
- select from the same total area
- determine restrictions
	- e.g. dominant species
	- disturbance 
	- etc.
- have a look at ABMI methods
- automated exploration and minimization of covariates? 


Plots:

Site Suitability;l
Site suitability was used to broadly describe the current habitat conditions in a 150 m radius around each bird point count station [2003-2015] or in a 50 m radius around locations where ARUs and/or remote camera traps were deployed as well as any bird point count stations [2015 onwards]. We recorded characteristics of veteran trees, dominant and co-dominant (canopy trees), and intermediate/suppressed (sub-canopy) trees, dominant shrub species and total shrub cover. We estimated total percent cover of shrubs in four categories (<25%, 25-50%, 51-75%, >75%). We estimated tree species composition (in 10% increments), average distance between trees (in 1 m increments), and average height of trees (to the nearest 5 m category) for all trees (excluding dead trees) within the following stratification categories:




# 2. Create a measure / index for structural diversity as predictor variable
-  within-stand structural diversity
- how to set to ultimately look for thresholds?
- multi-variate? or univariate? --> for predictor variable
	- ordination?
- Look at ***what might affect lichen*** and think about the best way to describe structural diversity to capture this relationship


# 3. Determine measures for response variables:
- Hill numbers (species richness, species diversity)
- species composition
- species abundance
- Richness Estimator
	- see lab 3 - Chao2 instead of Chao1? Because it is plants and therefor incidence rather than abundance?

# 4. Determine statistical methods to analyze effects
- ANOVA - species richness, 
- MANOVA - species composition
- Chao1 


- Linear Mixed Models
- Structural Equation Models