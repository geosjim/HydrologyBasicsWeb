# Synthetic Unit Hydrographs

The problem with using a derived unit hydrograph is that if we already have enough measured information (runoff and
rainfall) to derive the unit hydrograph then statistical methods of estimating a peak runoff are likely to be better
anyway. Most often we wish to perform a hydrologic analysis in ungaged locations where it is not possible to derive the
true unit hydrograph. For this reason synthetic unit hydrographs, such as the SCS, Clark, or Snyder, are used in
deterministic models.

A synthetic unit hydrograph is developed based on two important elements; the shape and the time to peak. The most basic
shape is the triangular, rational, unit hydrograph.

![Triangular Unit Hydrograph](../images/triangular_unit_hydrograph.png)

In order to make the shape more natural the SCS modified it to look like a typical measured hydrograph by elongating the
falling limb and fitting a higher order shape through the basic triangle.

![SCS Unit Hydrograph](../images/scs_unit_hydrograph.png)

The Clark method is another commonly used synthetic unit hydrograph. This method uses a time area mass curve to develop
the shape of the watershed. A time area curve defines the percentage of the watershed contributing flow at the outlet
from the beginning of the storm runoff to the time of concentration, or time when the entire watershed is in equilibrium
and contributing to flow at the outlet.

![Time Area Curve](../images/time_area_curve.png)

Further it uses a storage coefficient to account for the fact that there is a delayed response to runoff as the
watershed "absorbs" and then "releases" water for runoff much like a sponge. With a storage coefficient the peak can be
reduced by "spreading" or "squeezing" the hydrograph and decreasing or increasing the peak according to the storage
properties of the watershed being modeled. This second degree of freedom in the hydrograph makes it easier to match both
peak and volume of a measured event during calibration.

![Clark Unit Hydrograph](../images/clark_unit_hydrograph.png)
