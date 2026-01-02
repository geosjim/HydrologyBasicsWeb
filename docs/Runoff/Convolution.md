# Convolution

It has already been stated that a unit hydrograph corresponds to a certain duration. If a unit hydrograph is defined
based on a 30 minute duration, but we wish to model a rainfall event lasting several hours, then we must repeat the use
of the unit hydrograph over many 30 minute durations. An important property of unit hydrographs is that they are linear,
and so we can simply compute the several 30 minute unit hydrographs and add them together, after lagging each
appropriately to account for the proper starting times. The addition of multiple unit hydrographs over the defined
duration to generate the total runoff hydrograph is termed convolution.

As an example suppose we have the following 30-minute unit hydrograph from which we wish to model a storm for which we
have determined excess precipitation over three 30 minute intervals of .15, .8, and .25 inches respectively. We would
first compute each 30-minute runoff hydrograph (15%, 80%, and 25% of the unit hydrograph respectively), and then
starting the first at time 0, the second at 30 minutes, and the third at 60 minutes we would add them together to get
the final runoff hydrograph.

<video controls style="border: 2px solid black">
  <source src="/Media/Videos/Convolution.mp4" type="video/mp4">
</video>


In summary, to compute the runoff of a watershed we follow these steps:

Establish the important watershed parameters
Define the area of the watershed
Compute a runoff coefficient or area-weighted CN
Decide a unit hydrograph method and determine the time of concentration or lag time
Estimate the rainfall based on an actual event or a design storm
The rainfall consists of a depth and a temporal distribution
Then for each time step:
Determine the initial abstraction. If initial abstraction is not satisfied, go to the next time step
Determine the losses due to infiltration
Using the unit hydrograph and time of concentration (or lag time), compute the total runoff hydrograph for the time step
Using convolution add the hydrographs based on each time step
If we are only interested in the runoff of a single basin we are done. However if we wish to examine multiple sub-basins
for the purposes of defining a detention basin, some other hydraulic structure, or to take advantage of spatially
varying watershed properties or rainfall distributions, then we will need to route the computed basin runoff hydrograph
and combine them with runoff from other watersheds.

