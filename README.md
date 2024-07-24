# Management Of Scientific Data - Exam Project
***
Exam-Project for the modul Management Of Scientific Data. This project is a small example research project to demonstrate data management.
This project examines the impact a countries ppp value (local gdp) on covid-19 deaths and cases. 

## Overview

- _*data*_: contains all datasets
  - _*raw_data*_: raw input datasets from eurostat and ecdc
  - _*processed_data*_: preprocessed input data generated from the raw datasets
  - _*graphs*_: plotted graphs from processed data
- _*src*_: contains all the Jupyter Notebooks used to process the data
  - `src/data_quality_assurance.ipynb` checks data quality completeness of raw data 
  - `src/data_preprocessing.ipynb` generated preprocessed csv files from raw data 
  - `src/data_analysis.ipynb` plots graphs from the preprocessed input files 
- _*doc*_: contains the project documentation and presentation slides

## Getting started

- Install python and pip
- While in the code-directory enter the following command to install all required packages:`pip install -r requirements.txt`
- To generate all project-relevant data, execute the jupyter notebooks in the following order:
  - `data_quality_assurance.ipynb` checks data quality completeness of raw data 
  - `data_preprocessing.ipynb` generated preprocessed csv files from raw data 
  - `data_analysis.ipynb` plots graphs from the preprocessed input files 

## License

All data is licensed under [CC0](https://creativecommons.org/publicdomain/zero/1.0/legalcode.txt) license and all source code is licensed under [MIT](https://opensource.org/license/mit) license 

## Questions

Please contact the repository owner via mail (fabse.hupfeld@gmail.com) for any remaining questions after reading the comprehensive documentation 