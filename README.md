# Data sets for scheduling problems

This repository contains data sets and constraint models for the resource-constrained project scheduling problem (RCPSP) and some variants.

## Models

1. `rcpsp-cumulative.mzn`: Model in MiniZinc for the RCPSP/max using cumulative global constraints.
2. Project [kobe.rcpsp](https://github.com/ptal/kobe) can generate MiniZinc decomposition of RCPSP/max (without cumulative).

## Data sets

The data sets have different file formats and originate from different places.
We give a list of the data sets and credit the owners of these data sets.
We have clean these data sets with all the meta-information that was uneccessary to us, but feel free to consult the references given for the full data set.

We formatted known optimum results in a CSV format that is common to every data set (e.g. `data/rcpsp/j30.sm/optimum/optimum.csv`).

### RCPSP

1. Patterson (.rcp): Format originally used to evaluate RCPSP in Patterson (1984).
   It is the format used by the RanGen1 and RanGen2 generators.
   Sets of instances:
    1. Patterson: 110 instances.
    2. RG300[1]: 480 instances, 300 activities, 4 resources.
    3. RG30[2]: 900, 180, 240, 240, 240 instances, 30 activities, 4 resources.
       Resource data a bit "restricted" (in the way it was generated) on the RG30 sets.
    4. MT[3]: 900, 800, 1200, 1200 instances, 30 activities, 0 resource.
       ResSet[4]: Can be merged with MT for resources specifications.

   [1] Debels, Dieter and Vanhoucke, Mario. "A Decomposition-Based Genetic Algorithm for the Resource-Constrained Project-Scheduling Problem", 2007.

   [2] Mario Vanhoucke, José Coelho, Dieter Debels, Broos Maenhout, Luís V. Tavares, "An evaluation of the adequacy of project network generators with systematically sampled networks", European Journal of Operational Research, Volume 187, Issue 2, 2008.

   [3] Vanhoucke, M., 2010, "Measuring time: Improving project performance using earned value management" 1st ed., Springer: 164 pages.

   [4] Testing and validating algorithms for resource-constrained project scheduling (in submission).

2. SM format (.sm):

  Format of the PSPLIB, a well-known library for RCPSP with sets of instances of 30, 60, 90 and 120 activities.
  Sets of instances:
    1. j30: 480 instances, 30 activities and 4 resources.
    2. j60: 480 instances, 60 activities and 4 resources.
    3. j90: 480 instances, 90 activities and 4 resources.
    4. j120: 600 instances, 120 activities and 4 resources.

  R. Kolisch and A. Sprecher, “PSPLIB-a project scheduling problem library: OR software-ORSEP operations research software exchange program,” European journal of operational research, vol. 96, no. 1, pp. 205–216, 1997.

  http://www.om-db.wi.tum.de/psplib/getdata.cgi?mode=sm

### RCPSP/max

3. ProGenMax format (.SCH):

  Format of the sets of instances produced by the ProGenMax instance generator.
  It concerns the RCPSP/max problem.

  Sets of instances:
    1. C, D: each 540 instances, 100 activities, 5 resources.
    2. UBO_N: each 90 instances, N activities, 5 resources.
       N in 10, 20, 50, 100, 200, 500 and 1000.
    3. J_N: 270 instances, N activities, 5 resources.
       N in 10, 20, 30.

  http://www.wiwi.tu-clausthal.de/de/abteilungen/produktion/forschung/schwerpunkte/project-generator/rcpspmax/

### MMRCPSP (multi-mode RCPSP)

2. SM format (.sm): Similar to for RCPSP. With nonrenewable resources.

    Sets of instances:
      1. J_N: 3840 instances in total, N activities,
         N in 10, 12, 14, 16, 18, 20, 30

4. SM format light (.sm): Similar to SM format but without some headers.

    Sets of instances:
      1. MMLIB50: 540 instances, 50 activities, 3 modes.
      2. MMLIB100: 540 instances, 100 activities, 3 modes.
      3. MMLIB+: 3240 instances, 50 or 100 activities, 3, 6 or 9 modes.

    [1] V. Van Peteghem and M. Vanhoucke, “An experimental investigation of metaheuristics for the multi-mode resource-constrained project scheduling problem on new dataset instances,” European Journal of Operational Research, vol. 235, no. 1, pp. 62–72, May 2014.
