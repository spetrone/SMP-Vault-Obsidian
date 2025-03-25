- community hazard mitigation planning - fuel reduction to reduce weight of fuel - to reduce crown fires and embers landing on buildings
- #RENR740exam - only up to and including chapter 5 (not including Tuesday's lecture next week)
	- do not need to memorize equations, but need to know how to select and plug numbers into the equations
- R Package for Canadian forest fire behaviour prediction system

# FBP System
- take inputs from FWI to estimate the values for Byram's intensity of the head fire, flanks, and back of fire
	- weather
	- FFMC, ISI, BUI, Fuel Type, Elevation, Slop, Time, type of ignition (point, line)
- -will use in case study!
- Based on species composition
- Red book - based on equations that are based on stand type
- heavily imbedded in the psyche of how people think, it is from the 90's

- system resources: manually doing equations, red book, R package, RedApp, online calculator (American)


- Output:
- Primary
	- head fire rate of spread
	- head fire intensity
	- fuel consumption
	- fire type description
		- e.g. intermittent crown fire
- Secondary:
	- flank and back fire rates of spread
	- flank and back fire intensities
	- spread distance
	- length to breadth ratio
	- elliptical fire area and perimeter
	- rate of perimeter growth


- definition of continuous "crowning"
	- 90% of crown fraction burning
- intermittent - 50% crown fraction burned - in tables

### Fuel Types
- system designed to describe **natural*** forest conditions (not disturbed)
https://cwfis.cfs.nrcan.gc.ca/background/fueltypes/c1 

Conifers
- C1 : Spruce-Lichen Woodland
- C2 : Boreal Spruce
	- most flammable fuel
- C3: Mature Jack of Lodgepole Pine
	- also very flammable after pine beetle
- C4: Immature Jack or Lodgepole Pine
- C5: Red and White pine
- C6: Conifer Plantation
- C7: Ponderosa Pine-Douglas Fir

Mixedwood and Deciduous
- *for mixedwood, can specify the relative proportion of conifer to deciduous*
- D1 - Leafless Aspen
	- now there is D2 - for greened out deciduous - not in documentation; used in computational models.
- S1 - Jack or Lodgepole Pine Slash
- S2 - White spruce-balsam slash
- S3 - Coastal Cendar-Hemlock_Douglas-Fir Slash

Open and slash
- O1 - Grass
- M1 - Boreal Mixedwood-Leafless
- M2 - Boreal Mixedwood-Green
	- % conifer/hardwood
- M3 - Dead Balsam Fir Mixedwood-Leafless
- M4 - Dead Balsam Fir Mixedwood - Green

LIMITATION:
- the natural environment rarely conforms to the fuel type described in a category in the system
- now with fuel treatments, how to measure intensity
	- now need to measure fuel loads and plug into equations; cannot use models from representative stands


- Variation in forests, largely by age, the types in the FBS do not account for structural variation and age
- Van Wagner modeled how intensity is related to stand age (e.g. time-since-fire)
![[Pasted image 20250204102340.png]]- e.g. Jen Beverley's curve on probability of escape based on time since fire



Trial 
- altering structure with burning - not a great idea in Boreal forests
	- instead of fuel treatment
	- don't want to remove all the trees, but wanted a surface fire to remove all the surface fuels
	- trees not adapted to fire in this way - meant to die, not withstand fire

What happes when structure is altered by fuel removal
- creating more variation in forest structures out there and we don't have models for them
	- hopefully can make new fuel type in the system which will be a category with a model

### Modifiers
- allow you to make some adjustments in the system
	- e.g. crown base height for C6
	- e.g. % conifer/hardwood
	- e.g. % dead fire
	- e.g. % curing (grass)


FBP - must populate equation
- instead of off of field measurements, uses assumptions based off categories; uses defaults of fuel type.
- ISI - requires a slope adjustment and BUI adjustment
	- slope creates an equivalent/effective wind speed
- ![[Pasted image 20250206103034.png]]
- BUI set by fuel type
	- determines a Build-up effect
	- ![[Pasted image 20250206101432.png]]

- CBH set by fuel type category as well (e.g. C1)
![[Pasted image 20250206101501.png]]
In FBP

RSO = CSI / (300 x SFC)

if ROS > RSI - crown involvement
if ROS <= RSO no crown involvement 


Then plug it in:
![[Pasted image 20250206102030.png]]
### Crown Fuel Consumption 
- adding it to the intensity equation
-
TFC = SFC + CFB x CFL
total fuel consumption (TFC)
surface fuel consumption (SFC)
Crown fraction burned (CFB)
 - if only 50% is burned, then would multiply it by 0.5
 - if surface, then 0; then just Byram's equation for a surface fire
Crown Fuel Load (CFL) --> set by fuel type 


Using web app:
- default usually 500m for elevation

Explore page:
- do calculations, use app for calculations
- the visual has incorrect values - do not use the visualizing tool

- definitions: CFB in FBP system:
- #renr740exam
- <0.1 Surface fire
- 0.1 - 0.89 - intermittent crown fire
- > 0.9 continuous crown fire

#renr740exam 
- stepwise calculations with calculator
- will need to plug in numbers to equations