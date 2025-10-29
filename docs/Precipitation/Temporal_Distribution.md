# Temporal Distribution of Rainfall

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
