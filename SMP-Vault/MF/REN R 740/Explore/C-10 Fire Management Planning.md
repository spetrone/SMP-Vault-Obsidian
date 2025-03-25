- fuel management at stand at landscape scale
	- landscape scale - ecosystem scale mosaic - needed to emulate natural disturbance
	- for surface fire regimes - stand level makes more sense
		- may reduce crown fire initiation in boreal ecosystems, but it is not the natural fire regime;

- where to prioritize the effort - a map showing "hot spots" at the landscape level - heat map of where to prioritize 



- information for fire response differs based on mitigation
	- changed after Okanagan mountain fire in 2003 
	- whole history of science evolved for fire response, now for mitigation
		- what researchers and agencies did was try to use existing knowledge to switch to mitigation through fuel management
	- decided to grow a lot of fires as a management response
	- computer simulation arrived at the same time, so had computing power to go grow a lot of fires 
		- so **simulation-burn-probabilities** became the thing to do
			- re-iterate stochastically how each pixel burns in one year, and then compute the probability for each pixel across all simulations
	- Result of simulations after 11 years (maps made in 2005, fires compared in 2016) was that the probability heat map was entirely wrong; it does not work at all. 



- Fire behaviour models (fire growth and fire spread) models - are **brief processes**
	- brief process
	- occuring at a site 1 - 1000m2
- Fire Weather Index System - assessing day to day 
	- current conditions
	- an area of 1 - 100km2
- Fire risk or fire susecptibility assessments
	- conditions for a fire season
	- across a zone (10,000 km2 or more)


- terminology changes over time
	- "risk" has changed - the sign on the highway is the FWI fire risk only
		- when moving from fire response to mitigation, from reaction to proactive actions, risk definition changed to engineering framework using likelihoods - but can you estimate likelihoods? (See below)

**Risk = Likelihood x Potential Impacts**
- *changed from potential for fire ignition on a given day to the engineering framework for risk assessment*
- *burn probability modeling provided the likelihoods - need some degree of confidence on the likelihoods, but it was proven that simulation-based likelihoods were not reliable*

**Hazard = a potential source of harm**
- for fire itself or precipitating factors (fuel can be the potential source of harm)
- so fuel is a hazard - fuel hosts the fire; weather doesn't host the fire, it modifies the fire
- whether harm plays our depends on 
	- source characteristics 
	- environmental factors/modifiers
	- receptor characteristics
- for fuel as a hazard
	- source characteristics:
		- fuel flammability, load, structure, composition, arrangement, continuity
	- environmental factors/modifiers:
		- dry spells, drought, ignitions, wind speed, wind direction
		- **this is why the probability modeling maps do not work - stochastic modeling just does not cover enough variables***
		- SO: calculate probabilities without needing this part
	- receptor characteristics:
		- building materials
		- infrastructure
		- habitat suitability
		- fire regime
		- timber resources
		- etc. etc. that you care about


**Exposure** - looks at the possibility of fire to transmit from the fuel to the receptor (from hazard to receptor)
	- in between  are the environmental modifiers
	- is it proximate enough for fire to transmit from fire to receptor
	- these probabilities are needed for the engineering framework of risk
		- but the environmental modifiers are very tricky to get to; 
		- the purpose of this method is to exclude the environmental modifiers when calculating likelihoods
- **Exposure**: started 15 years ago; replicated by independent group in Alaska
	- Exposure is based on fore transmission distances
	- we know where the fuel is
definition: a numeric rating of the potential for fire transmission to a location given surrounding fuel conditions
****


- conifers in general burn much more
- in terms of age class -fire burns ***proportionately to what is available***
	- not necessarily related to where fire suppression has occurred, no significant pattern

source characteristics
- how precise?
- spatial context - the surroundings are important - e.g. water surrounding an area



### burn probabilities
- the FBP system does not have away to spot over non-fuel barriers like rivers
- when Fort McMurray was modelled with prometheus, when a vertice hits water it just stops
	- therefore those using models did not realize the implications of the fire moving over the river 
	- hard-coded in that the fire stops when it gets to water


### Burn probabilities vs Exposure
- Fire Spread Simulation (burn probability)
	- 25,000 iterations
	- includes environmental modifiers (ignitions, weather, wind,)
	- estimate burn probability
	- data intensive
	- computationally complex
	- poor alignment with fires
	- slow, inefficient
### Neighborhood Analysis (Exposure)
- simple neighborhood analysis based on hazard and receptor, ignoring the environmental modifiers
	- is there hazardous fuel around
	- % of neighborhood with hazardous fuel
	- single input (fuel)
	- fast
	- inexpensive
	- aligns with real fires
		- can still add in modifiers;
			- e.g. combine with FFMC
			- then it will be exposed + dry today
			- blend strategic exposure map with more real-time, precise condition map (with a time horizon that makes sense)
- intersect segments with exposure map
	- those with at least 80% with exposure under it, they get shown in colour
	- very simple in GIS
	- radius centered at area/location of interest, and go out from centre, looking at overlaps with the exposure map
		- e.g. anything with conifer
		- exposure map uses fuel grids
		- **any conifer or mixedwood gets a 1 , everything else is a 0; this is at the landscape scale**
			- doesn't even need the FBP system to do this well
			- ![[Pasted image 20250320102407.png]]
	- ![[Pasted image 20250320102442.png]]
	- can be used for proactive containment lines or fuel management to protect specific areas


## Types of Risk
###### Aleatory:  
▪ Uncertainty due to variability or  randomness.  
▪ “The more we understand the  probabilities, the better we can assess  the risk we are facing” – is this valid?  
- unlikely to be possible to understand  or measur/map probabilities

###### Epistemic:  
▪ Uncertainty due to gaps in knowledge.  
▪ “We can endeavor to fill our gap in  knowledge that is causing the uncertainty which creates the risk” – is this possible?  

