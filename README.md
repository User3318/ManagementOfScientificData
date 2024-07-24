# Management Of Scientific Data - Exam Project

Exam-Project for the modul Management Of Scientific Data. This project is a small example research project to demonstrate data management.
This project examines the impact that economy of an eu-country has on their COVID-19 deaths and cases during the COVID-19 pandemic.  

For further information read the [workflow documentation](doc/workflow.md)

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

- Install python 3.11.9 and pip
- While in the code-directory enter the following command to install all required packages:`python3 -m pip install -r requirements.txt`
- To generate all project-relevant data, execute the jupyter notebooks in the following order:
  - `data_quality_assurance.ipynb` checks data quality completeness of raw data 
  - `data_preprocessing.ipynb` generated preprocessed csv files from raw data 
  - `data_analysis.ipynb` plots graphs from the preprocessed input files 

## License

All data is licensed under [CC0](https://creativecommons.org/publicdomain/zero/1.0/legalcode.txt) license and all source code is licensed under [MIT](https://opensource.org/license/mit) license 

## Questions

For further questions or suggestions please contact the repository owner via github([User3318](https://github.com/User3318)) or mail ([fabian.hupfeld@uni-jena.de](mailto:fabian.hupfeld@uni-jena.de))