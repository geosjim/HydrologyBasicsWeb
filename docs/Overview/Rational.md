# Rational Method

The rational formula is one of the oldest and most commonly used methods to predict peak flows. It was originally used
to estimate peak flows only, but a triangular shaped hydrograph has also been used to define the hydrograph shape and
runoff volume. Precipitation is represented through an intensity (inches/hr) and it is assumed that the intensity is the
same throughout the entire watershed. All losses, including initial abstractions, are represented with a single runoff
loss coefficient defined between 0.0 (no runoff) and 1.0 (no losses). The only other input variable is the drainage
area, in acres.

<video controls style="border: 2px solid black">
  <source src="/Media/Videos/Rational.mp4" type="video/mp4">
</video>

The rational hydrograph is defined as a triangle, with the peak flow occurring at the time of concentration and the
total duration of the storm being two times the time of concentration.

![Rational Hydrograph](../Media/Images/Rational_hydrograph.png)

This traditional rational hydrograph assumes that duration of the storm is equal to the time of concentration.  If the duration is longer, the hydrograph shape will change from a triangle to a trapezoid with the corresponding peak flow.

![Extended Rational Hydrograph](../Media/Images/Rational_hydrograph_extended.png)

The rational method is simple and easy to use, but the difficulty in determining a runoff coefficient and the limitation of defining rainfall as a constant intensity make it applicable mostly for small, urban watersheds.
