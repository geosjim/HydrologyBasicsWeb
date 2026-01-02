# HEC-HMS

The US Army Corps of Engineer's Hydrologic Engineering Center (HEC) has been involved in the development of computer
simulation models for several decades. One of their most popular models has been HEC-HMS, which is a deterministic model
used to model runoff from rainfall. The HEC-HMS (formerly HEC-1) model includes several different methods for defining
rainfall, losses, runoff transformation and routing. HEC-1 is divided into separate hydrograph computational units as
illustrated in the diagram below.

<video controls style="border: 2px solid black">
  <source src="/Media/Videos/HEC-1.mp4" type="video/mp4">
</video>

The most simple hydrograph analysis problems are solved with a single basin. For a basin, runoff is computed from a
defined rainfall depth and temporal distribution, a loss coefficient, and a runoff transformation method. The way these
three processes are simulated in a deterministic model will be discussed in the following pages. For more advanced
analyses a computed basin hydrograph can be routed through reaches, reservoirs, and diversions to produce the resulting
downstream hydrograph based on the channel, reservoir, or diversion properties.