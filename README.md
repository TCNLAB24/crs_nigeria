# The impact of sub-national heterogeneities in demography and epidemiology on the introduction of rubella vaccination programs in Nigeria

This study characterizes sub-national heterogeneity in rubella transmission within Nigeria and models impact of local rubella vaccine introduction under different scenarios on the incidence of congenital rubella syndrome (CRS). 

- Details on the methodology are described in: \
  

## Version History

**Feb 9, 2024**: Uploaded first version of code. 

## Data
- Population data: Population counts stratified by gender and age in 2020 for Nigeria at a resolution of 3 arc seconds were sourced from [WorldPop](https://hub.worldpop.org/geodata/summary?id=50493)
- Birth data: The number of live births in 2015 for Nigeria at a resolution 0.0083 decimal degrees was obtained from [WorldPop](https://hub.worldpop.org/geodata/summary?id=760)
- Mortality data: Life tables used to estimate age-specific mortality rates for Nigeria were obtained from [UN Department of Economic and Social Affairs](https://population.un.org/wpp/Download/Standard/Mortality/)

## Contents

**data_management.Rmd**: This Rmarkdown document prepares the demographic and epidemiological data necessary for subsequent analyses. It uses the following datasets: 
- geographical polygons from [GADM](https://gadm.org)
- population counts by local government area from [WorldPop](https://www.worldpop.org)
- age-specific fertility rates from [WorldPop](https://www.worldpop.org)
- life table at national level from [UN Department of Economic and Social Affairs](https://population.un.org/wpp/Download/Standard/Mortality/)

