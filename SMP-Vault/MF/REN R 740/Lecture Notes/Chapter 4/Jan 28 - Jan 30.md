**Fire Behavior :** 

Definition 1: “The manner in which fuel ignites, flame develops, and fire spreads and exhibits  
other related phenomena as determined by the interaction of fuels, weather,  
and topography.

Definition 2: " Fire behaviour refers to the way that  
a fire burns, including how quickly it  
spreads, how much heat it gives off  
and how much vegetation it  
consumes.”"

Fire management objectives have changed:
- early - put fires out - that underpinned the science behind fires - but nothing about how fire stops, all about how it ignites, spreads, moves, heat,
- evolved with blinders on - did not model how it stops, dissipates and extinguishes

**Management Changes:**
- Now from fire response in suppression to fuel treatment and containment planning

Maybe next: how about predicting how it will stop? 


**Fireline Intensity**: the radiant energy released in the flaming front

Intensity used to predict biological impacts

Byram (1959):
*I = hwr*

When calculating fire intensity - can incorporate the different strata - using the weight of the fuel - gather and aggregate that information

## Parts of a Fire:
- can calculate intensity at all of these areas
![[Pasted image 20250128100401.png]]

- front: fastest moving, usually with wind, also usually upslope
	- greatest flame length, depth and rate of spread
- unburned islands - AKA fire skips, fire refugia, green islands
## Parts of a Flame
#renr740exam know difference between length and height
![[Pasted image 20250128100636.png]]- 
- *depth** length on ground
- angle
- length - longer when angle < 90
- height

Relationship between intensity and flame length:
![[Pasted image 20250128100904.png]]

- built equation with grass fires - but there is a maximum with crown fires so it doesn't' apply as well to crown fires (would underpredict since much of fuel is considerable distance above the ground). There are other equations though, such as Butler's


### Calculating intensity
1. Constant
2. Weight of Fuel Consumed
	1. need to know what portion will be consumed
	2. small, fine fuels will 100% be consumed
		1. understory conifer, shurbs, low vegetation, woody material up to ~1cm in diameter
	3. calculated with Alberta Fuels Inventory - with specific protocols
		1. sometimes destructive sampling
		2. sample sizes and classify sizes (e.g. class 1 and 2 are fine)
		3. percent ground cover of shrubs and height
	4. depth
		1. use stakes but hard to differentiate what burned from flame front vs smoldering and the equations are based on this depth of burn that is confounded by the smoldering
	5. Crown/canopy vs surface fuels
		1. Canopy Base height (CBH)
		(some use a *fuel strata gap*)
		2. Canopy bulk density (CBD)
		3. Canopy Length

![[Pasted image 20250128104202.png]]

Crown fuel measurement:
-   Destructive sampling can be used to develop tree crown biomass equations  
- Remove all foliage and fine branch wood – dry and weigh  
- Oven-dry weights of all crown fuel components then regressed against diameter (DBH) and  
coupled with plot stem inventory to calculate canopy fuel loads  
- Example equations estimated by Alexander et al. (2004) for jack pine:

See: Predicting Fuel Characteristics of  Black Spruce Stands Using  Airborne Laser Scanning (ALS) in  the Province of Alberta, Canada  (H. Cameron MSc Thesis, 2020)

3.  Rate of Spread
	1. direct observation
	2. in-stand measurement
	3. photo/video/infrared
	4. estimate from empirical data/statistical relationships

Fuel consumption measurements (w in equation - weight):
	1. pre-fire and post-fire  sampling to calculate the load (weight) of fuels assumed to be consumed during the passage of the fire front
		1. biomass measurements and equations
			1. size class gauge
			2. shrubs - percent cover sum + transect height
		2. photo-load measurements
	2.wildfires - estimations from observations - estimate fuel loads and depth of burn using matched pairs in burned and unburned locations
	3. estimate from empirical data/statistical relationships


## Surface Fire Transition to Crowning
- crown fuel measurement
	- e.g. photoload guides
- low intensity surface file not enough energy, may kill/scorch needles but ot cause ignition
	- driven by winds that can penetrate into the canopy == crown fire initiation - but will it sustain and spread horizontally with the **wind**)
	- more intense, temp in Canopy rises


## Crown Initiation Equation
Van Wagner(1977) -  equation, to get to initiation of crown fire:
` CSI = 0.001 x CBH^1.5 x (460 +25.9 x FMC)^1.5`

CSI = **Critical surface fire intensity***
CBH = Canopy Base Height
FMC = Foliar Moisture Content

# Sustained Crown Fire Spread
![[Pasted image 20250130094924.png]]
CBD = canopy bulk density
S0 = mass flow rate of fuel expressed as mas per unit cross-sectional area per minute (typically 3.0kg/m^2)

note:
- crown bulk density and crown height = single tree
- canopy bulk density and canopy height = stand

## Calculating Crown intensity and plug into surface fuel intensity (Byram) equation
![[Pasted image 20250130095137.png]]

- once spread into crown, the w in Byram's equation must be updated to include biomass in the crown - includes both layers
	- we have a calculator to do that
- #RENR740Exam - know these two equations; fundamental and used in FWI

## Shape of fire
- important for spatial referencing for:
	- impacts
	- response - knowing what resources to send and how many you need:
		- what is the area and what is the rate in increase over a given time period and how much perimeter (front/edge is what is being suppressed) - number of firefighters depends on length of perimeter
- Ellipse
	- deviation from simple ellipse will arise when fire environment conditions vary (perfect circle when there is no variation)
	- stronger winds - longer length-to-breadth ratio
![[Pasted image 20250130100253.png|150]] ![[Pasted image 20250130100326.png|400]]
![[Pasted image 20250130100400.png]]
![[Pasted image 20250130100509.png]]

- HOWEVER, you usually do not have homogenous conditions
- More advanced with computational models - at changes, puts points along edge and then grows ellipses along each point and re-draws the perimeter - so it is many ellipses growing at each timestep - can account for conditions at different areas
## WIND DIRECTION CHANGES
- When a cold front is moving from west to  
east, the local winds ahead of the front will  
shift to be from the southeast, then from  
the south, and gradually from the southwest  
just prior to the frontal passage.  

- This change in wind direction pushes  
warmer air northward, resulting in unstable  
atmospheric conditions.  

![[Pasted image 20250130100716.png]]![[Pasted image 20250130100730.png]]