# Hyetographs

In reality the storm intensity changes constantly, but it is not feasible to simulate a rainfall event as completely
continuous. Therefore, a storm is generally entered for a deterministic model using depths that correspond to a given
time step. For example a tipping bucket rain gage measures a rainfall depth every 10 or 15 minutes and reports the storm
in this manner. A graphic representation of such an event is referred to as a rainfall hyetograph and is illustrated in
the figure below.
![Rainfall Hyetograph](../images/Rainfall_Hyetograph.png)

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