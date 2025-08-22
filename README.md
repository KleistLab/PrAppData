# PrAppData
This repository contains code to conduct the statistical analysis of factors associated with PrEP use and non-use in Germany and to identify reasons for not using PrEP among those with a PrEP indication.

- [System requirements](#system-requirements)
  - [Operating systems](#operating-systems)
  - [Dependencies](#dependencies)
- [Execution ](#execution)
  - [Input files](#input_files)
- [Output](#output)
- [Demo](#demo)
- [Figures](#figures)

## System requirements 

### Operating systems
This workflow was tested on macOS Sequoia Version 15.5 and Windows 10 Version 22H2

### Dependencies

| software/package      | version           |
| -------------   |:-------------:| 
| python          | 3.13.1 | 
| pandas          | 2.3.1     |  
| numpy | 2.3.1   |   
| matplotlib | 3.10.3  |   
| seaborn | 0.13.2  |   
| tableone | 0.9.5  |   
| statsmodels | 0.14.5  |   
| joblib | 1.5.1 |   
| kneefinder |0.0.2 |   
| scikit-learn |1.7.2 |   



## Execution 
The statistical analysis can be found in the [jupyter notebook](PrApp_analysis.ipynb). 

### Input files
As input the statistical analysis requires the files with the preprocessed PrEP and non-PrEP users 
- no_PrEP_filtered.csv 
- PrEP_filtered.csv 

## Output 
The following files are created in the folder results, with the following structure:

```bash
    └── results                                       # results folder
        ├── parameter_tuning_models                   # logistic regression models for the parameter tuning
        |   ├── logreg_0.joblib                       # for l1-ratio 0.0 - 1.0
        |   ├── logreg_0_1.joblib                     # for l1-ratio 0.1 - 1.0 (with regularization strength 
        |   ├── logreg_0_1_elbow.joblib               # based on the elbow point)
        |   ├── logreg_0_2.joblib 
        |   ├── logreg_0_2_elbow.joblib
        |   ├── logreg_0_3.joblib 
        |   ├── logreg_0_3_elbow.joblib
        |   ├── logreg_0_4.joblib 
        |   ├── logreg_0_4_elbow.joblib
        |   ├── logreg_0_5.joblib 
        |   ├── logreg_0_5_elbow.joblib
        |   ├── logreg_0_6.joblib 
        |   ├── logreg_0_6_elbow.joblib
        |   ├── logreg_0_7.joblib 
        |   ├── logreg_0_7_elbow.joblib
        |   ├── logreg_0_8.joblib 
        |   ├── logreg_0_8_elbow.joblib
        |   ├── logreg_0_9.joblib 
        |   ├── logreg_0_9_elbow.joblib
        |   ├── logreg_1_0.joblib 
        |   └── logreg_1_10_elbow.joblib
        ├── multivariable_analysis_result.csv         # table with regression coefficients, CI and P-values
        └── multivariable_analysis_result_sensitivity.csv  # sensitivity analysis: table with regression coefficients, CI and P-values                      

```

## Demo
As example datasets 
- no_PrEP_filtered.csv 
- PrEP_filtered.csv 
will be provided upon publication.

The HIV-specialists density categories "0" and "1-2" were summarized in these data sets for further anonymization.

## Figures 
The code and data to reproduce the manuscript figures is given in [figs](figs). 
