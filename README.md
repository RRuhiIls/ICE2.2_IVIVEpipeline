# ICE_IVIVEpipeline
The workflow allows the flexibility to select from three different rat and human PK models: a 1 compartment model that incorporates Monte Carlo simulation to simulate the population variance (1C), a 3 compartment model leveraging the  [EPA's httk package](https://github.com/USEPA/CompTox-ExpoCast-httk) (Solve_3comp), and a pbpk model that is tailored for compounds with additional glucuronidation(3CGlu). The workflow is to predict the daily equivalent administered dose (EAD, mg/kg/day) that would lead to steady state blood concentration equivalent to the bioactive concentration from in vitro assays and compared to the predicted lowest effective levels (LELs) of in vivo assays, which is user provided

# Required Libraries
library(plyr) # splitting, combining and applying data
library(deSolve) # Solves for initial value problems of differential equations
library(tidyr) # helps tidy data easily
library(ggplot2) # for creating elegant complex plots
library(scales) # scaling functions for visualizing

# Input files
ChemicalData_rnotebook.txt # chemicals dats from ICE, include CASRN field as identifier
"invitroData_xc.txt" # invitro data from ICE, includes CASRN field as identifier then acc/ac50 values

# Code files
steadyState.R # required for 1C model
glu_MaxConc.R # required for "3CGlu"
CalcEAD.R # required for 1C and 3CGlu
EADboxplot.R # required for plotting
