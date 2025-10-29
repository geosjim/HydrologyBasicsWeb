# Thiessen Polygons

A slight variation on the simple average method is the Thiessen Polygon method. With this method a single average value
is still used in the simulation for each model, but it is computed by weighting the value of each gage according to the
area of influence it has on the watershed. The area of influence is determined from the Thiessen network, which defines
all of the area that is closest to a given gage.

![Thiessen Polygon Rainfall](../images/Thiessen_Polygon_Rainfall.png)

The equation is similar to the basin average, but includes the area closest to the gage as a weighting factor.