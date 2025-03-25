- think of it as moisture codes
- tracking moisture coming in and out of the fuels, changing day to day and hour to hour as these change
	- RH
	- temperature
	- precipitation
	- wind
- only based on weather(the above four variables)
- built over decades and decades of measurements


- ***tracks the moisture content in 3 different layers  on surface***
	- fine fuel moisture code - thin - for ignition (especially human ignitioin)
	- duff moisture code - loosely compacted organic layer - 5-7 cm depth - more possible for lightning ignition because it is so intense and can explode trees
	- drought code - heavily compacted and decomposed - not part of head fire but part of drought conditions that can cause deep smoldering

- codes are arbitrary relative numbers - no units
	- based solely on weather, per weather station throughout fire season

- based on a closed pine stand (conifer only) - but not that relevant since it is on fuel size


- empirical-based approach in Canada rather than physical-based modeling approach like in the USA
	- Canada observations rather than theoretical and conceptual models

- predicts conditions for peak burning period : 16:00 LST (local standard time) - 17:00 (LST)
	- daylight savings not accounted for


3 layers -> moisture codes :
know layer (what is in it)
thickness
weather conditions affecting that layer

- processing is a bookkeeping system of sponges

### 3 **moisture codes**:
- FFMC : fine fuel moisture code
	- surface  litter 
- DMC : Duff Moisture Code
	- 5-10 cm F horizon
- DC : Drought code
	- 10cm - mineral soil - H horizon


used to create indices (relative numbers, not ) - analogues to the pieces of Byram's equation, but relative ratings - no units.

ISI : FFMC + wind (initial spread index)
BUI : DMC  + DC () Buildup index
 FWI (fire weather index) : BUI + ISI -> overall measurement rating of intensity

* *note that the FWI above is a unique index - the system also has the umbrella name with the 6 parts* 


## Intensity (Bryam 1959)
intensity: the rate of energy release
fireline intensity: the rate of heat transfer per unit length of fire (kW/m)
I = hwr
w: weight of fuel consumed (kg/m2)
r: rate of spread (m/s or m/min)
h : constant head of combustion (~18,000 kJ.kg, or with m/min 300)


mirrors with indices:
you do NOT substitute them into this equation, they are just a rating indicator of those things, have no units. #renr740exam

I : FWI
w: BUI - weight - build-up index
r : ISI - rate of speed - initial spread index

Prediction/output is for peak burning at 1600-1700
input is at **noon** - to predict ahead of time, set alert times, etc.


- fuel moisture & equilibrium 
	- determines fuel availability for ignition and combustion
	- affected by all three components of the fire triangle
	- about drying and wetting - this is what is in bookkeeping
		- Fuels are constantly exchanging moisture with the surrounding air
	- Equilibrium moisture content, is reached when there is no net gain or loss of moisture between fuels and the surrounding air

Time lag:
Time lag is the amount of time necessary for a dead fuel particle to lose or gain 63 percent of the difference between its initial moisture content and its equilibrium moisture content at a constant temperature and relative humidity
- “amount of time it takes for the fuel to lose 2/3 of its available moisture
- depends on:
	- temperature, RH, wind speed
	- fuel - how fine determines how responsive
- 
Equation for equilibium moisture content exchange:
- **negative exponential relationship***

![[Pasted image 20250123101245.png]]


### FFMC Calculations
- in SPRING most important - dry but lower layers are moist but FF are dry
	- therefore --> more **human caused fires***
- For dry fuels, you can approximate FFMC as 101-mc
- For dry fuels, you can approximate moisture content as 101-FFMC
- since exponential, never average the FFMC, and also because of hard cutoffs:
	- An FFMC of at least 75 (i.e., ~25 -30% moisture content) is typically required for ignition and fire spread in fine fuels in many forest fuel complexes
- will need to calculate #renr740exam


## DMC Calculations
- more likely for **lightning-caused** 
	- after weeks of drying out - then people or lightning-caused
- takes longer to dry
	- much longer time lag - weeks instead of hours or days like fine fuels
- Equilibrium moisture content me is assumed to be a constant value of 20% 
- Time lag τ varies with temperature and relative humidity
## Deriving Key Values Empirically
- DMC vs fires per lightning strike
![[Pasted image 20250123102846.png]]
### Drought Code
- deeper layers, lower duff
- much slower time lag
- 300 good cutoff
- Equilibrium moisture content, me is assumed to be a constant value of 0% 
- Time lag τ varies only with temperature


## Key values for moisture codes:
- get to know the key values for each indicator - red flags for people on the ground

Key values for Indices:

- *ISI over **10***
- *BUI over **80***
- *FWI* - Every province has a table of what values they consider to be low, moderate, high extreme - **24** is common
### Questions
- is m0 in the field empirically measured rather than estimated (step 1?)
- what kinds of equations do we need to know?

- decision support system
