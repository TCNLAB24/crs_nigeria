# The impact of sub-national heterogeneities in demography and epidemiology on the introduction of rubella vaccination programs in Nigeria

This study characterizes sub-national heterogeneity in rubella transmission within Nigeria and models impact of local rubella vaccine introduction under different scenarios on the incidence of congenital rubella syndrome (CRS). 

- Details on the methodology are described in: \
  [TO BE UPDATED POST DAPR].

## Version History

**Feb 9, 2024**: Uploaded first version of code. 

## Data
- **Population data**: Population counts stratified by gender and age in 2020 for Nigeria at a resolution of 3 arc seconds were sourced from [WorldPop](https://hub.worldpop.org/geodata/summary?id=50493)
- **Birth data**: The number of births by age group used in the calculation of age-specific fertility rates were made available by the Demographic and Health Surveys (DHS) Program in Nigeria (see `ng2_fertility_data.csv` in `local_data`)
- **Mortality data**: Life tables used to estimate age-specific mortality rates for Nigeria were obtained from [UN Department of Economic and Social Affairs](https://population.un.org/wpp/Download/Standard/Mortality/)
- **Serological survey data**: Raw seroprevalence data are unavailable due to privacy consideration as datasets include global positioning system coordinates which might enable identification of location of study subjects. For access to an anonymized state-level serological survery data (`ng1_rubella_seroprevalence_data.csv`), please reach out to the corresponding author. 

## Contents

`data_management.Rmd`: This Rmarkdown document prepares the demographic and epidemiological data necessary for subsequent analyses. It uses the following datasets: 
- geographical polygons from [GADM](https://gadm.org)
- population counts by local government area from [WorldPop](https://www.worldpop.org)
- age-specific fertility rates are available in the `local_data` folder. 
- abridged life tables for both sexes at national level from [UN Department of Economic and Social Affairs](https://population.un.org/wpp/Download/Standard/Mortality/)

`r0_estimation.Rmd`: This Rmarkdown document estimates the $R_0$ for rubella in each state of Nigeria using age-stratified serological survey data. 

`parameterization.Rmd`: This Rmarkdown document generates the parameteres for the MSEIRV age-structured model used for the simulation of rubella dynamics in each of the 37 states of Nigeria. 

`initial_conditions.Rmd`: This Rmarkdown document generates the initial conditions for the simulation of rubella dynamics in each of the 37 states of Nigeria. 

`model_simulators.Rmd`: This Rmarkdown document runs the simulations of the MSEIRV age-structured model. The model itself is implemented in C++ (`mspeirv_ode_model.cpp`). 

`local_data`: This folder contains relevant local data including state-level first-dose measles-containing-vaccine coverage (`ng1_mcv1_data.xlsx`), state-level zone designations (`ng1_zone_designations.csv`) and structure of hypothetical rubella vaccination campaigns (`summarised_general_sia_scenario1.xlsx`, `summarised_general_sia_scenario2.xlsx`). 

`helper_scripts`: This folder contains short helper scripts used by some of the Rmarkdown documents. Further details are provided in the respective script headers. 

## Project workflow
To successfully estimation $R_0$ and perform simulations, please follow the steps below:
- download required data to local repository (see above)
- run `data_management.Rmd`
- run `r0_estimation.Rmd`
- run `paramaterization.Rmd`
- run `initial_conditions.Rmd`
- run `model_simulators.Rmd`

Details of specific R packages required for each step are described in the respective Rmarkdown documents. 

## Support 

Please direct questions or bug reports to [TO BE UPDATED POST DAPR].
