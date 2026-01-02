# Curve Number (CN)

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
  <source src="/Media/Videos/CNCalculations.mp4" type="video/mp4">
</video>