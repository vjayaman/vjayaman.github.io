
## Honours Research Project Proposal

Student: Vasena Jayamanna

Supervisors: Dr. Michael Domaratzki, Dr. Eduardo Taboada


### Introduction

We will be developing a tool for active reporting on SARS-CoV-2 phylogenetic analysis and associated metadata, using the existing EpiQuant analysis framework [[3]](#3). Within this reporting tool we plan to compare clusters of cases across points in time while considering a variety of different factors. My project involves development of a module in which we detect and report on any clusters with a significant increase in size from one time point to the next. While detection of expanding clusters is the focus, I will also use this information as "label data" to attempt prediction of clusters that can be expected to increase in size. In other words, prediction of population prevalence at a secondary time point, using genome data and associated metadata at a primary time point. 

### Background preparation

Data available from open source data repositories such as Nextstrain [[2]](#2) and GISAID [[1]](#1) will be used for analysis. Relevant genomic/phylogenetic data and associated metadata will be collected and processed. We will use the phylogenetic data to extract clusters at significant similarity thresholds. The metadata will be cleaned for use as input into the expanding cluster detection module as well as for the machine learning model in prevalence prediction. Research into appropriate learning algorithms will be done as a starting point of analysis.

### Related work

The EpiQuant model is based on the use of epidemiologic cluster cohesion (ECC), which is a “measure of … homogeneity of isolates within a subtyping cluster” [[4]](#4). Isolates within clusters with high ECC values have epidemiologic profiles with high similarity [[3]](#3). We plan to compute the ECC of clusters generated at various thresholds and under different parameter settings and this analysis will form the core of the reporting tool. I will be responsible for developing a module for monitoring cluster prevalence and cluster expansion which will also include a machine learning component for predicting clusters likely to expand. 

### Problem statement

Rapid reporting on genomic information on COVID-19 suitable for public health officials and front-line epidemiologists is needed. A COVID-19 reporting tool is being developed that will require a module for monitoring cluster prevalence over time and detecting cluster expansion. An additional feature of great interest would be the ability to prospectively predict clusters likely to undergo future expansion. In addition to developing the tools for basic cluster prevalence monitoring, I will develop a machine learning model that can predict SARS-CoV-2 cluster prevalence at a secondary time point, given cluster prevalence, metadata and phylogenetic information at the primary time points.

### Methodology

  - Develop method for comparing the cluster size and cluster composition between time points.
    - Data at three separate time points have been sampled from the available GISAID and NextStrain repositories. This resulted in information for 3692 strains on April 15th, 4690 strains on May 17th, and 4382 strains on June 4th of this year. Using clusters extracted by our team from the given phylogenetic Newick trees, I compared the data across the three time points, identifying recurring strains (that were found at more than one time point) and new strains (only found at one of the three time points). I compared clusters composition and sizing across the three stages to get a better understanding of the data.
  - Develop reporting module that outputs cluster sizes, cluster membership, difference in cluster size between time-points
  - Analyze example data to generate labelled clusters at Time 1 that underwent significant cluster expansion by Time 2. 
  - Identify fields with enough information to be potential input in a machine learning model, pinpoint preferred format of output (type of classification). 
  - Select type(s) of model(s) that are appropriate for the problem and set initial parameter values.
  - Split the data into training and test data sets. Train the data.
  - Evaluate the results and adjust parameters (or model choice) as required. We will repeat the training and evaluation until results are as satisfactory as possible.
  - Test the model on the test data and analyze the results, comparing test and training error as a check.

### Infrastructure required

The sequence data and metadata are readily available from public repositories, and we have sufficient independent computing resources via personal workstations at the National Microbiology Lab and access to laboratory data servers.

### Outcomes

  1. A module in the reporting tool for cluster prevalence and cluster expansion detection given independent time points and corresponding data, or
  2. A learning algorithm that can predict population prevalence for significant clusters at the given time points, or 
  3. A conclusion on features for which we need more data before the model can perform effectively;  identification of potential influencing factors in cluster expansion over time.

### References

<a id="1">[1]</a> S. Elbe and G Buckland-Merrett.  ”Data, disease and diplomacy:  GISAID’s innovative contribution toglobal health.”.Global Challenges, 1:33–46, 2017.

<a id="2">[2]</a> Hadfield et al. ”Nextstrain: real-time tracking of pathogen evolution.”.Bioinformatics, 34(23):4121–4123,01 December 2018.

<a id="3">[3]</a> Benjamin M et al Hetman.  ”The EpiQuant Framework for Computing Epidemiological Concordance ofMicrobial Subtyping Data.”.Journal of Clinical Microbiology, 55(5):1334–1349, 2017.

<a id="4">[4]</a> Eduardo Taboada.  ”The Campy-COVID project:  applying the EpiQuant framework to facilitate large-scale reporting on SARS-CoV-2 WGS data.”.  PowerPoint presentation, April 2020.
