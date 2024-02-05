# Static_Traffic_Assignment 🚗🛣️

## Overview

This project focuses on the Static Traffic Assignment (STA) conducted from January to April 2023, employing Dijkstra's algorithm (Label Setting Method) and the Label Correcting Method on the US cities network dataset. The results were used for implementing traffic assignment algorithms like Frank Wolfe and Method of Successive Averages.

## Introduction

This report compares the time taken for computing the System Optimal (SO) and User Equilibrium (UE) solutions using different approaches. Two methods, label correcting and label setting, were combined with Frank-Wolf and MSA algorithms to find UE and SO solutions. Results were measured in Jupyter notebook on our own system.

## Hardware Details

- Architecture: x86_64
- CPU: AMD Ryzen 5 5600H with Radeon Graphics (12 CPUs)
- CPU Speed: 3294 MHz
- Kernel: 5.10.102.1-microsoft-standard-WSL2
- Memory: 7646.2 MiB

## Observed Time for SO and UE Solutions

| City       | UE TSTT      | SO TSTT       | % Diff | Time (MSA+LS) | Time (MSA+LC) | Time (FW+LS) | Time (FW+LC) |
|------------|--------------|---------------|--------|---------------|---------------|--------------|--------------|
| SiouxFalls | 7477635.21   | 21731841.32   | 190.62 | 1.43 s        | 3.07 s        | 0.26 s       | 0.51 s       |
| EMA        | 28207.75     | 31265.04      | 10.86  | 1.57 s        | 3.12 s        | 2.18 s       | 4.13 s       |
| Chicago    | 18374511.86  | 23105285.6    | 25.74  | 137.59 s      | 1795.58 s     | 44.87 s      | 582.61 s     |
| Anaheim    | 1323294.53   | 1753730.04    | 32.6   | 1.43 s        | 11.95 s       | 1.07 s       | 10.08 s      |

## Conclusion

From the results, FW+LSM works faster in most cases than MSA+LSM. MSA+LCM was slowest in 3 out of 4 cases. These algorithms with LCM don’t work well because the argmin function in LCM is quite unoptimized. Surprisingly, in each case, the System Optimal Travel Time (SOTT) was greater than the User Equilibrium Travel Time (UETT).

## Usage

1. Install the required dependencies by running `$ sudo lscpu` and `$ sudo inxi`.
2. Adjust parameters and configurations in the Jupyter notebook (`STA_Jan_Apr_2023.ipynb`).
3. Run the notebook to execute the STA algorithms and analyze results.

Feel free to explore the project! ✨🚀
