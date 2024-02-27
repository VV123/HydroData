# HydroData

## Data Description as A Graph

`Node`: index (e.g., v_i=1), hydrological data are represented as node features. 

`Edge`: connectivity of nodes (e.g., <v_i, v_j>), material, slope, and other static edge features. 


## Files and Field Descriptions

- junction.csv - Node file
  - `id`
  - `coordinate`
  - `Invert` is the inner bottom of the pipe (or manhole)
  - `Flow depth` is measured from the elevation of the invert.

- conduit.csv - Edge file
  - `id`
  - `start`
  - `end`
  - `Manning's n` describes the surface roughness of the pipe wall. A greater value of n indicates greater loss of head (energy) due to friction. 
