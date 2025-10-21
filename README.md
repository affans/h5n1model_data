## H5N1  Simulation Data 

This repository contains the accompanying simultion data from the [H5N1 model](https://github.com/affans/h5n1model). The data is organized as follows

- The folders `AsymptomaticFraction-20-Percent` and  `AsymptomaticFraction-50-Percent` contain data corresponding to probability of an asymptomatic infection being 20% and 50%, respectively.

- Each subfolder includes scenarios of `Preemptive` or `Reactive` vaccintion. The filename also indicates `Self-Isolation`, which refers to self-isolation of symptomatic individuals 1 day or 2 days after symptom onset.

- Files within each subfolder have the format `r2_A[*]_i[*]_vt[*]_isoday[*]_[type].csv`. 
    - The `r2` refers to the calibrated reproduction number of 0.2.
    - The `A*` refers to vaccination effectiveness scenarios,  
        - `A1` = 50% protection against infection, no protection against symptomatic disease
        - `A2` = no protection against infection, 85% protection against symptomatic disease
        - `A3` = 50% protection against infection, 85% protection against symptomatic disease
    - The `vt*` refers to the number of days for vaccination to become effective (also referred to as preemptive or reactive). `vt = 1` means vaccination was effective on day 1 of the simulations while `vt = 42` means vaccination was effective by day 42 of the simulation. 
    - The `isoday*` refers to when a symptomatic person was isolated. That is, `isoday2` corresponds to self-isolation 2 days after symptom onset. 
- The file type `_incidence` corresponds to daily incidence (365 days) over `n` simulations. Headers include `baseline` in which there is no isolation. The next four columns refer to incidence when 50%, 60%, 70%, and 80% of symptomatic individuals self-isolate. The next four columns refer to same compliance of self-isolation but include vaccination of farmers only. The next four columns are similar, but now include vaccination farmers + household members of those farmers.   

- The file type `_maxbeta` denotes the maximum beta value (representing infection pressure) from each simulation. The initial value is calibrated to `R = 0.2`, which is then subject to mutations during the simulation. This file records the maximum beta across all transmission chains. 

- The file type `_maxgen` corresponds to the maximum transmission generation. For example, `initial infections -> secondary infections -> tertiary infections` represents three generations.
