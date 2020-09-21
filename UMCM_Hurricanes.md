# University of Miami Coupled Model (UMCM) for Hurricane Ike and Sandy

## Model

The University of Miami Coupled Model (UMCM) is a coupled model that integrates
atmospheric, wave, and ocean components to produce wind, wave, and current
data, Atmospheric data is produced using the [Weather Research and Forecasting](https://www.mmm.ucar.edu/weather-research-and-forecasting-model)
model (WRF), Wave data is produced using the [University of Miami Wave Model](https://umwm.org/)
(UMWM), While ocean current data is produce using the
[HYbrid Coordinate Ocean Model](https://www.hycom.org/) (HYCOM),

The model was used to study offshore wind conditions during Hurricane Ike
and Hurricane Sandy, The time resolution for each model run is as follows:

- Hurricane Ike
  - 1 sample/hour from 9/8/2008 12:00:00 UTC to 9/12/2008 6:00:00 UTC
  - 1 sample/10 minutes from 9/12/2008 6:00:00 UTC to 9/13/2008 9:00:00 UTC
- Hurricane Sandy
  - 1 sample/10 minutes from 10/28/2012 00:10:00 UTC to 10/31/2012 00:00:00 UTC

The following variables were extracted from the HYCOM model:
- bathymetry
- ocean_mixed_layer_thickness-ilt
- ocean_mixed_layer_thickness-mlt
- sea_water_potential_density at all depths
- sea_water_salinity at all depths
- sea_surface_elevation
- eastward_sea_water_velocity
- northward_sea_water_velocity
- upward_sea_water_velocity
- sea_water_temperature
- depth (m): [0, 5, 10, 15, 20, 25, 30, 35, 40, 45, 50, 55, 60, 65, 70, 75, 80, 85, 90, 95, 100, 105, 120, 135, 150, 175, 200, 225, 250, 275, 300, 350, 400, 450, 500, 600, 700, 800, 900, 1000]

The following variables were extracted from the
- cd
- cgmxx
- cgmxy
- cgmyy
- dcg
- dcg0
- dcp
- dcp0
- depth (m): [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 12, 14, 16, 18, 20, 25, 30, 35, 40, 50, 60, 70, 80, 90, 100]
- dwd
- dwl
- dwp
- momx
- momy
- mss
- mwd
- mwl
- mwp
- rhoa
- rhow
- seamask
- swh
- tailatmx
- tailatmy
- tailocnx
- tailocny
- taux_bot
- taux_form
- taux_form_1
- taux_form_2
- taux_form_3
- taux_ocn
- taux_skin
- taux_snl
- tauy_bot
- tauy_form
- tauy_form_1
- tauy_form_2
- tauy_form_3
- tauy_ocn
- tauy_skin
- tauy_snl
- u_stokes at all depths
- uc
- ust
- v_stokes at all depths
- vc
- wdir
- wspd

## Directory structure

The UMCM data as two .h5:
- s3://oedi-data-lake/umcm/
  - ike.h5
  - sandy.h5

The UMCM data is also available via HSDS at /nrel/umcm/,

For examples on setting up and using HSDS please see our [examples repository](https://github.com/nrel/hsds-examples)

## Data Format

The data is provided in high density data file (,h5) separated by year, The
variables mentioned above are provided in 2 dimensional time-series arrays with
dimensions (time x location), The temporal axis is defined by the `time_index`
dataset, while the positional axis is defined by the `meta` dataset. The units
for the variable data is also provided as an attribute (`units`).


## References

Users of the UMCM model should use the following citations:
- [E. Kim, L. Manuel, M. Curcic, S. S. Chen, C. Phillips, P. Veers, 2016, On the Use of Coupled Wind, Wave, and Current Fields in the Simulation of Loads on BottomSupported Offshore Wind Turbines during Hurricanes (Technical Report, NREL/TP-5000-65283), Golden, CO: National Renewable Energy Laboratory.](https://www.nrel.gov/docs/fy16osti/65283.pdf)