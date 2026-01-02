## Precipitation

For deterministic models the precipitation input is the primary catalyst for generating the peak flow and runoff
hydrograph. For models like HEC-HMS precipitation is defined as a rainfall depth and temporal distribution (time varying
intensity), whereas other models like the rational formula use a constant rainfall intensity.

<video controls style="border: 2px solid black">
  <source src="/static/video/Precipitation.mp4" type="video/mp4">
</video>

## Depth

It goes without saying that accurately determining rainfall depth is an essential factor in simulating runoff. Rainfall
depths are determined for a given area from either historical records of gages or through the use of radar analysis or a
combination of both.

<video controls style="border: 2px solid black">
  <source src="/static/video/Rainfall_Depth.mp4" type="video/mp4">
</video>

### Spatial Variation of Actual Storms

An important limitation to understand and quantify is the spatial variation of rainfall depth over a watershed. In fact
the rainfall depths, much like the radar predictions of rainfall you see on weather maps, not only varies across a large
watershed, but can be substantially different over just a short distance. While a continuous (different at every
location) map of rainfall depth provides the true representation, as of yet we do not have the capability to accurately
measure this on the ground.

<video controls style="border: 2px solid black">
  <source src="/static/video/Actual.mp4" type="video/mp4">
</video>

The radar rainfall estimates you see on weather maps would appear to be the perfect solution, but they are only
estimates of where the rainfall is more intense. While they provide a good picture of where it might be raining harder
relative to other locations, they actually do a poor job of predicting absolute values of rainfall depth on the ground.
This is due in part to the fact that they measure reflectance at a high altitudes. Some of what is measured never
reaches the ground, or it may be blown as it falls making the location on the ground different than what is measured.
Radar rainfall data, when adjusted by measured rain gages can be useful, but this process is still uncertain (because of
the lack of gages) and not yet available in real time. It is certain that in the future the ability to use radar data
will improve, but for now most models will continue to be developed with basin average, isohyetal, Thiessen-weighted,
etc. estimates.

### Basin Average Depth

The most common way to develop rainfall estimates for a watershed in a hydrologic simulation is to simply take an
average from nearby gages, or from a continuous map (which has been derived from gages). For example in the figure below
four different gages are within the watershed, or close enough that measured values are thought to be reflective of what
might occur in the watershed. The basin average method is simple. A rainfall depth is determined by taking the numerical
average of the gages as follows.

<video controls style="border: 2px solid black">
  <source src="/static/video/Average.mp4" type="video/mp4">
</video>

This method of computing an average works well where gage data are available. Many agencies, including NOAA, have
developed maps like the one below from gages using their best information with respect to topography and meteorological
behavior that show rainfall depths for different return periods. Some models, including the MODClark method in HMS and
other distributed models, can take advantage of spatially varying rainfall, but for many models an average value is
calculated over the watershed or its sub-basins.

![Basin Average Precipitation](static/images/continuousprecipmap.png)

### Thiessen Polygons

A slight variation on the simple average method is the Thiessen Polygon method. With this method a single average value
is still used in the simulation for each model, but it is computed by weighting the value of each gage according to the
area of influence it has on the watershed. The area of influence is determined from the Thiessen network, which defines
all of the area that is closest to a given gage.

<video controls style="border: 2px solid black">
  <source src="/static/video/Thiessen.mp4" type="video/mp4">
</video>

The equation is similar to the basin average, but includes the area closest to the gage as a weighting factor.

## Temporal Distribution of Rainfall

Depth is only one part of describing a storm for a hydrologic modeling simulation. The time duration, or temporal
distribution of the rainfall event is just as important for hydrologic models. For example 3 inches of rainfall is a
lot, but spread out over a year it is not. Of course one year is extreme, but even spreading it out over 24 hours as
opposed to 2 hours will make a big difference on the amount of runoff and flooding.

The depth of rainfall divided by the duration is the rainfall intensity. For example a depth of 2 inches in 3 hours
results in an intensity of .67 in/hr, whereas a depth of 2 inches in 24 hours results in an intensity of .083 in/hr.
Some models, like the rational method use intensities, in inches/hr, to define the rainfall input, but others like HEC-1
and HMS use a depth with a corresponding temporal distribution, or time varying intensity. This is because few storms
maintain a constant intensity for more than a short time period. By defining a separate temporal distribution the
varying intensity throughout the storm can be represented and modeled and therefore the watershed runoff can be more
accurately represented.

### Effects on Runoff and Infiltration

Different intensities, or temporal distributions can have dramatically different effects on runoff and infiltration
within the watershed. You can think of the runoff on the watershed much like pouring water on a sponge. If water is
poured quickly (high intensity) then there is not time for the sponge to absorb much and most of it will be runoff. On
the other hand if water is slowly poured or dripped onto the sponge (low intensity) then most of it will be absorbed and
little will be runoff.

The following animation illustrates the effects of infiltration, or losses (these are losses to surface runoff but are
actually sources to groundwater) and runoff for a high (short duration), medium, and low (long duration) intensity
storm. For each case the total rainfall depth is the same, and equals the sum of the losses and runoff, but the
different intensities alter the separate volumes of losses and runoff significantly.

<video controls style="border: 2px solid black">
  <source src="/static/video/Runoff_and_infiltration.mp4" type="video/mp4">
</video>

### Hyetographs

In reality the storm intensity changes constantly, but it is not feasible to simulate a rainfall event as completely
continuous. Therefore, a storm is generally entered for a deterministic model using depths that correspond to a given
time step. For example a tipping bucket rain gage measures a rainfall depth every 10 or 15 minutes and reports the storm
in this manner. A graphic representation of such an event is referred to as a rainfall hyetograph and is illustrated in
the figure below.

<video controls style="border: 2px solid black">
  <source src="/static/video/Hyetograph.mp4" type="video/mp4">
</video>

A hyetograph is defined as either cumulative or incremental values. For the simulation illustrated above the cumulative
and incremental values would be as follows:

Time Cumulative (in.)    Incremental (in.)
0:00 0 0
0:05 0.10 0.10
0:10 0.30 0.20
0:15 0.70 0.40
0:20 1.57 0.87
0:25 2.17 0.60
0:30 2.62 0.45
0:35 2.77 0.15
0:40 2.84 0.07
0:45 2.86 0.02

During a simulation the amount of rainfall that occurs each time step is processed as a single event and followed
through the entire simulation. For example if in a 5 minute time interval .4 inches of rain falls, the simulation would
determine for that same time interval how much of the rainfall infiltrates and how much runs off. The runoff depth would
then be transformed using a unit hydrograph which in turn would be routed through a reservoir or river. Methodologies
for computing losses, unit hydrograph transformations, and routing are presented in the following pages.

### Design Storms

In summary, rainfall can be defined as an intensity, generally a constant intensity as is the case for the rational
method, or as a hyetograph where the depth is associated with a temporal distribution. The Natural Resource Conservation
Service (NRCS), formerly the SCS, has defined some typical design storms for various regions of the United States. These
distributions are dimensionless in depth, but generally 24 hours in length. They indicate the differences among typical
storms where 1) rainfall begins with a shorter period of higher intensity towards the middle and tapers off, 2) a
relatively constant intensity throughout, or 3) a high intensity storm where most of the rainfall occurs over a
relatively small duration. The animations below illustrate these differences.

<video controls style="border: 2px solid black">
  <source src="/static/video/Design_storms.mp4" type="video/mp4">
</video>

The temporal distribution along with a computed depth from gages, a continuous map, or other estimate provides the basis
for defining rainfall in a HEC-1 or HMS (or similar deterministic) model. Because of interception and infiltration in
the watershed not all of the rainfall will be converted to runoff. Before the rainfall depth can be converted to a
runoff hydrograph, the effective rainfall must be determined by subtracting losses from initial abstractions and
infiltration.
