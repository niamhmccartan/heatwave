# heatwave

**Impact of heatwave amplitude, duration, and timing on parasite fitness at different baseline temperatures.**

Niamh McCartan 1 (communicating author), Floriane O’Keeffe 1, Guoyuan Zhang 1, and Pepijn Luijckx 1.

1 Discipline of Zoology, School of Natural Sciences, Trinity College Dublin, Dublin 2, Ireland.

This dataset contains infection prevalence and burden observations collected from _Daphnia magna_ infected with its microsporidian parasite _Ordospora colligata_ at the School of Natural Sciences in Trinity College Dublin during spring 2022 (experiment 1) and spring 2023 (experiment 2). This study looked at the effect of heatwaves on parasite fitness. Here, a heatwave meant a increase in baseline temperature (constant mean temperature) at a specific amplitude and duration, occurring at different time points. 

In experiment 1, infection prevalence data included all exposed individuals, while burden data included confirmed infections only. Baseline temperature was a continuous centered variable to reduce issues with collinearity and remove the need for a ‘water bath’ variable, thus avoiding any associated random effects. A polynomial (cubic for burden) was added to account for non-linearity in the response to temperature. Amplitude and duration were ordered factors with two levels each (“+3ºC” and “+6ºC” for amplitude, “3 days” and “6 days” for duration), both also included the constant treatments with the reference level “0”, this allowed for statistical testing on the two variables both independently and combined. Heatwaves occured 10 days prior to infection, on the day of infection (day 0), 10-days and 20-days post infection. An indivdual _Daphnia_ reveived one heatwave treatment at one of these timings. The package ‘glmnet’ was used to model parasite fitness, and the package ‘emmeans’ was used to compare specific treatments. Data were analyzed using R Studio version 4.0.3. Custom contrast p-values were adjusted for multiple comparisons using the ‘Benjamini-Hochberg’ method.

In experiment 2, burden data included confirmed infections only. Here, there was one baseline temperature (17ºC), and one amplitude (+6ºC). Only duration and timing in relation to infection were altered. Duration was the same as experiment 1 with an ordered factor containing two levels “3 days” and “6 days” for duration and the constant treatment with the reference level “0”. Heatwaves occured 10 days prior to infection, on the day of infection (day 0), and 10-days post infection, to have even dispersions around the infection day. The package MASS was used to run a glm with a negative binomial distrubiton. Then a chi squared analysis of deviance was run. Finally, the package ‘emmeans’ was used to compare specific treatments. Data were analyzed using R Studio version 4.0.3. Custom contrast p-values were adjusted for multiple comparisons using the ‘Benjamini-Hochberg’ method

______________________________________________________________________________

**R scripts for analysis**

_HW_Analysis.Rmd_: analysis and graphing for both infection prevalence and burden for experiment 1.

_HW_17.Rmd_: analysis and graphing for comparison of burden between experiment 1 and 2.

_____________________________________________________________________________

**List of datasets used for analysis**

_HW_data.csv_: observations on infection prevalence and burden in experiment 1

```
ID: unique sample number from 1 to 1176
Timing: heatwave timing, either happening 10-days pre-infection “-10”, the day of infection "0", 10 days post-infection "10", 20 days post-infection "20", or constant “C”
A_Temp: target baseline temperature
Real_Avg: the true temperature per bath read from the HOBO loggers at the end of the experiment 
Amplitude: How many degrees the cold snap decreased (“0” constant, “+3” +3 ºC, “+6” +6 ºC)
Duration: Duration of the cold snap (“0” constant, “3” 3 days, “6” 6 days)
Replicate: Replicate number of the treatment
Bath: Location of the individual microcosm (either bath A, B, or C)
Date: Date of death (last day 08/05/2022)
Day: Day of death (starting from day -10 and ending on day 34)
Sex: Sex of the individual 
Infection: Presence (1) or absence (0) of infection 
Spores: Number of spores present if infected, if exposed but uninfected NA entered
Exposed: Number of spores present if infected, if exposed but uninfected 0 entered
Include: Yes if included in analysis, no if excluded from analysis (e.g. before first confirmed infection, any males, or any inconclusive infections) 
Notes: Any important notes given when dissections occurred
Change: Explanation if any changes in the raw data were made
```

_HW_17.csv_: observations on burden in experiment 1 and 2

```
ID: unique sample number 
Experiment: whether the sample was in experiment 1 "A" or experiment 2 "B"
Timing: heatwave timing, either happening 10-days pre-infection “-10”, the day of infection "0", 10 days post-infection "10", or constant “C”
A_Temp: target baseline temperature
Real_Avg: the true temperature per bath read from the HOBO loggers at the end of the experiment 
Amplitude: How many degrees the cold snap decreased (“0” constant, “+6” +6 ºC)
Duration: Duration of the cold snap (“0” constant, “3” 3 days, “6” 6 days)
Replicate: Replicate number of the treatment
Bath: Location of the individual microcosm (either bath A, B, or C)
Date: Date of death (last day 26/07/2023)
Day: Day of death (starting from day -10 and ending on day 30)
Sex: Sex of the individual 
Infection: Presence (1) or absence (0) of infection 
Spores: Number of spores present if infected, if exposed but uninfected NA entered
Include: Yes if included in analysis, no if excluded from analysis (e.g. before first confirmed infection, any males, or any inconclusive infections) 
Notes: Any important notes given when dissections occurred
Change: Explanation if any changes in the raw data were made
```

_HW_Temp_Logs.xlsx_: raw temperature data per bath per hour, also with overall mean temperature 

```
#: Time point recording ID
Date Time, GMT+00:00: Date and time of time point recording 	
Temp, °C: Temperature recorded					
Average Temp: Average temperature only including temperature points ±2 degrees
Logger ID: Logger ID used for the specific bath	
```
