# heatwave

**Impact of heatwave amplitude, duration, and timing on parasite fitness at different baseline temperatures.**

Niamh McCartan 1 (communicating author), Floriane O’Keeffe 1, Guoyuan Zhang 1, and Pepijn Luijckx 1.

1 Discipline of Zoology, School of Natural Sciences, Trinity College Dublin, Dublin 2, Ireland.

This dataset contains infection prevalence and burden observations collected from _Daphnia magna_ infected with its microsporidian parasite _Ordospora colligata_ at the School of Natural Sciences in Trinity College Dublin during spring 2022. This study looked at the effect of heatwaves on parasite fitness. Here, a heatwave meant a increase in baseline temperature (constant mean temperature) at a specific amplitude and duration, occurring at four different time points. Infection prevalence data included all exposed individuals, while burden data included confirmed infections only. Baseline temperature was a continuous centered variable to reduce issues with collinearity and remove the need for a ‘water bath’ variable, thus avoiding any associated random effects. A polynomial (cubic for burden) was added to account for non-linearity in the response to temperature. Amplitude and duration were ordered factors with two levels each (“+3ºC” and “+6 ºC” for amplitude, “3 days” and “6 days” for duration), both also included the constant treatments with the reference level “0”, this allowed for statistical testing on the two variables both independently and combined. Heatwaves occured 10 days prior to infection, on the day of infection (day 0), 10-days and 20-days post infection. An indivodual _Daphnia_ reveived one heatwave treatment at one of these timings. The package ‘glmnet’ was used to model parasite fitness, and the package ‘emmeans’ was used to compare specific treatments. Data were analyzed using R Studio version 4.0.3. Custom contrast p-values were adjusted for multiple comparisons using the ‘Benjamini-Hochberg’ method.


