## H5N1  Simulation Data 

This repository contains the accompanying simultion data from the [H5N1 model](https://github.com/affans/h5n1model). The data is organized as follows

- The folders `AsymptomaticFraction-20-Percent` and  `AsymptomaticFraction-50-Percent` contain data corresponding to probability of an asymptomatic infection being 20% and 50%, respectively.

- Each subfolder includes scenarios of `Preemptive` or `Reactive` vaccintion as well as `Self-Isolation` days of either 1 day or 2 days. 

- Files within each subfolder have the format `r[*]_A[*]_i[*]_vt[*]_isoday[*]_[type].csv`. 
    - The `r*` refers to the calibrated reproduction number (i.e., `r2 = 0.2` and `r8 = 0.8`).
    - The `A*` refers to vaccination effectiveness scenarios,  
        - `A1` = 50% protection against infection, no protection against symptomatic disease  
        - `A2` = 50% protection against infection, and addition 50% protection against symptomatic disease
        - `A3` = no protection against infection, 50% protection against symptomatic disease
    - The `vt*` refers to vaccination time (i.e., preemptive or reactive). `vt = 1` means vaccination was administered on day 1 of the simulations while `vt = 42` (corresponding to reactive vaccine) means vaccination was administered on day 42 of the simulation. 
    - The `isoday*` refers to when a symptomatic person was isolated. That is, `isoday2` corresponds to self-isolation after 2 days of symptomatic infection. 
- The file type `_incidence` corresponds to daily incidence (365 days) over `n` simulations. Headers include `baseline` in which there is no isolation, `isolation50-80` referring to incidence when 50-80% of symptomatic individuals isolated, followed by 4 columns of incidence under vaccination, followed by 4 columns of incidence of isolation+vaccination. 

- The file type `_maxbeta` denotes the maximum beta value (representing infection pressure) from each simulation. The initial value is calibrated to `R = 0.2` or `R = 0.8`, which is then subject to mutations during the simulation. This file records the maximum beta across all transmission chains. 

- The file type `_maxgen` corresponds to the maximum transmission generation. For example, `initial infections -> secondary infections -> tertiary infections` represents three generations.