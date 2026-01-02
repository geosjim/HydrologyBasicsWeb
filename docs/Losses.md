## Losses

The term losses in a hydrologic modeling simulation refers to all of the rainfall that does not runoff and make it to the river as part of the flood hydrograph. Such losses include initial
abstractions, infiltration, evaporation, and transpiration. The kinds of models used for flood runoff are considered short term simulations and therefore losses from evaporation and transpiration are
considered negligible. For long term simulations where the water balance is over a season or year (beyond the scope of this review) they would be significant and must be considered.

![Losses](static/images/losses.jpg)

## Initial Abstractions

The initial abstractions are the first losses that must be "satisfied" in a hydrologic simulation before any runoff or
infiltration occurs. They consist of surface or depression storage as well as the water that fixes itself to vegetation
such as leaves and grass. It is impossible to calculate exact volumes for initial abstractions so estimates within a
hydrologic model must be made and adjusted in order to account for them. For a rational method simulation there is no
separation of losses between initial abstractions and infiltration, whereas for the curve number method (to be discussed
in the next few pages) traditional practice has been to estimate initial abstractions as 20% of the maximum potential
losses (or watershed storage).

<video controls style="border: 2px solid black">
  <source src="../static/video/InitialAbstractions.mp4" type="video/mp4">
</video>

## Infiltration Losses

Infiltration losses consists of the rainfall that percolates into the soil matrix and down towards the water table. In
fact most infiltration is not lost overall, but becomes recharge to the groundwater for use in transpiration (uptake by
plants) or replenishing of aquifers. However, for short term simulations where the focus is on flooding they are
considered losses.

Important physical properties that determine infiltration include land use and soil. The land uses (i.e. agricultural,
forest, urban, etc.) determine how well the water is held or detained so that infiltration into the soil matrix can
occur. For example, it is more difficult for water to move quickly through thick foliage than across the pavement and
concrete of an urban environment and so we would expect more infiltration in forested areas than urban ones. Further,
the tilling of agricultural lands "loosens" the soil making infiltration higher than in areas where soils are more
compacted or consolidated. 

<video controls style="border: 2px solid black">
  <source src="../static/video/Infiltration.mp4" type="video/mp4">
</video>

## Simulation Methods

As with any other physical process we try to estimate, in a numerical simulation simplifications must be made. In the
case of infiltration, Darcy's law would ideally be used in the mathematical model, however it is difficult to know
important parameters such as the hydraulic conductivity and moisture content of soil across an entire watershed.
Therefore for simpler deterministic models like the rational method and HEC-1/HMS estimates are made by empirical
methods such as the rational runoff coefficient or the curve number.

### Runoff Coefficients

The rational method uses a runoff coefficient to separate the rainfall depth into losses and runoff. It defines a simple
percentage for the amount of rainfall that runs off. The rational equation is given as:

Q = CiA

- C = runoff coefficient (value between 0.0 and 1.0)
- i = rainfall intensity (inches/hour)
- A = area (acres)

If C represents the percentage of rainfall that becomes runoff then (1-C) would be the losses. In the case of runoff
coefficients all losses, including initial abstractions and infiltration are accounted for with this single value.

Some examples of different C values for different kinds of surface condition are given in the following table.
Surface condition Runoff Coefficient
Business districts 0.70 - 0.95
Residential 0.50 - 0.75
Industrial 0.50 - 0.90
Parks and grass 0.05 - 0.30
Streets and driveways 0.75 - 0.95
Agricultural and unimproved 0.10 - 0.30

If a watershed contains multiple surface conditions, a composite runoff coefficient should be calculated using an area
weighted average.

### Curve Number (CN)

Curve Number
A curve number is a type of runoff coefficient, but it is not a simple percentage value like the coefficient used in the
rational method. The curve number is a concept developed initially by the Soil Conservation Service (SCS) and hence it
is often referred to as the SCS Curve Number. It is typically cited as simply CN as an abbreviation of curve number. CN
values were derived from empirical data and not from direct physics. It is a function of both land use and soil and is
used to determine potential losses (or watershed storage, S) using the following equation:

S = (1000/CN) -10

Where:    S = Potential losses (inches)
CN = SCS curve number

Initial abstractions are typically estimated as 20% of the potential losses, or 0.2*S. Effective rainfall is then
computed using the following equation:

R = (P - .2S)^2 / (P + .8S)

Where:  R = Rainfall Excess (or the part of rainfall that becomes runoff)
        P = precipitation depth
        S = potential losses (storage of the watershed)

The equation is only valid when the rainfall P > .2S since lower values would actually produce negative runoff. When
using a curve number in a numerical model like TR-55 or HEC-1 the depth for initial abstractions must first be
satisfied. In their derivation of the CN concept a series of tables were created relating CN to different hydrologic
soil groups and land use covers. These tables are available in the TR-55 documentation and adaptations in almost any
text on hydrology. The hydrologic soil group is either A, B, C, or D, where A soils are loose (sands) and have high
infiltration rates, B and C are in the middle and D soils are tight (clays) and have relatively low infiltration rates.

To determine a CN you must know the hydrologic soil group and land cover of your watershed and then use a look-up table
from the SCS publications or a standard hydrology text. If multiple land uses and/or soil groups exist within the
watershed then a composite (area-weighted average) CN should be computed. GIS files for soils and land use exist for
many areas and can be used to automate composite CN computations. Move your mouse over the animation below to understand
better how these calculations are performed.

<video controls style="border: 2px solid black">
  <source src="../static/video/CNCalculations.mp4" type="video/mp4">
</video>
