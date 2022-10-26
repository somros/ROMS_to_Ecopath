# Mapping GOA ROMS output to Ecopath

This code performs two tasks:

1. Overlay the grid of a ROMS model for the GOA to the spatial domain of a Ecopath model.
2. Extracts physical and biological variables from the ROMS-NPZ model and summarizes them to obtain input values for Ecopath. 

All variables that identify a concentration per $m^3$ in the ROMS output were converted to average values per $m^2$ by integrating (sum) over the water column, after conducting a cubic spline interpolation of the ROMS data at 1 m depth intervals. Variables that are not concentration (e.g. salinity, temperature, etc.) were averaged over the water column (same vertical interpolation). See notes in the code for details.

The file `ROMS_to_Ecopath_depth_interp.Rmd` is where you would look for an overview of the workflow. The file `ROMS_to_Ecopath_ts.R` is what you would use to run this again for another model/data. Get in touch (arovel@uw.edu) if you have issues with any of those.

__NOTE__: this could be generalized to work for any model, all you need is ROMS data and a shapefile of the model domain.