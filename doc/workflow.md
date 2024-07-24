# Workflow
This file provides a general workflow of this project, using the Data Lifecycle as guideline

Plan -> Collect -> Assure -> Describe -> Preserve -> Discover -> Integrate -> Analyze
***
# Plan
Data Management Plan Template V1.1(04.2022) from Horizon Europe ([template](https://ec.europa.eu/info/funding-tenders/opportunities/docs/2021-2027/horizon/temp-form/report/data-management-plan_he_en.docx))  
Provides all major dmp aspects in a simple template. 
Most points clear in advanced, since it's a small project

# Collection
First dataset was given by exam. [Data on 14-day notification rate of new COVID-19 cases and deaths](https://www.ecdc.europa.eu/en/publications-data/data-national-14-day-notification-rate-covid-19)  
To answer the research question, additional data is required. Since an own Observations is not possible, processing of pre-existing data is required.  
Searching for quantitative data of all eu-countries in the given time range of the gdp in a structured format (csv preferred) from a trusted resource.

#### [Eurostat](https://ec.europa.eu/eurostat/web/main/home)
Provided statistic data about the eu. All datasets are well documented with metadata and have a [free re-use license](https://ec.europa.eu/eurostat/about-us/policies/copyright)
- Search Term gdp provided several datasets.
- One promising data set covered the gdp per capita in pps (local price adjusted gdp)
- Download metadata in xlsx format and dataset in csv format

# Assure
#### Data Quality
- Completeness:
  - The pps dataset offered 100% completeness
  - The covid dataset contained some missing data entries (89% completeness), because the corresponding health-organization of this country did not provide any information for this week 
- Uniqueness: The combination of time and country offer a unique identifier with no duplicates
  - the covid-dataset also required the indicator column to allow a unique datapoint identification.
- Timeliness: Both datasets covered the expected time range and are up-to-date (last updates: pps(19.06.24), covid(17.11.2023)).
- Validity: All data conforms with their described format in metadata
- Accuracy: They are published by an eu-organization, so I assumed that the data is accurate
- Consistency: There were two differences between the representations in the two datasets
  - The covid dataset provided time in a string format "year-week", were the pps dataset provided the time in years as an integer format
  - The covid dataset refers to the eu countries with a 3-letter Iso-code, the pps dataset provides a 2-letter Iso-code

#### Data Cleaning

While assessing the data quality, some major consistency problems were found. Therefore, some data preprocessing was required.
- Split year-week entries into separate week/year columns
- Format all country codes to a common 2-letter isocode
- Drop unwanted columns(irrelevant information) and rows(irrelevant data of accumulated eu values)

# Describe
- ReadMe
- Workflow described in this file
- Metadata generated using dublincoregenerator.com
  - Describes all generated data with metadata, including csv column descriptions

# Preserve
A public GitHub Repository will be used to preserve the project data. This approach offers backups and version control.  
In Addition to that no precautions regarding personal data is required, since there is no personal data used in this project.  
To further protect against data loss, a project copy is stored on the authors local storage. 

#### FAIR-Data
- Findable
  - Due to the project scope, no unique and persistent identifier was created (GitHub project url as semi valid identifier)
  - If this project scope expands, all data will be published on zenodo with a valid identifier and keywords
  - All generated datasets have corresponding metadata with metadata linked to the research project
- Accessible
  - The project and the corresponding metadata is publicly available with standard protocols or web browsers via the project link.
- Interoperable
  - To ensure interoperability extensive metadata provides data description and references in an human/machine readable open format.
- Reusable
  - ReadMe.md provides startup instruction to improve reusability.
  - Used Jupyter-notebooks provide comments and a requirements.txt allows an easy installation process of all required packages.
- License
  - All code is licensed under a MIT-license
  - All generated data is licensed under a CC0-license

# Discover
[EuroStat](https://ec.europa.eu/eurostat/web/main/home) provides qualitative FAIR-Data with rich metadata for different statistical datasets of the eu.  
[Zenodo](https://zenodo.org/) offers a large amount of datasets from different research project, but often too specific for our usecase.

# Integrate

Similar dataset formats were provided, but minor differences required preprocessing (See [Data Cleaning](#data-cleaning))
For an easier analysis the preprocessing datasets are then combined into two datasets (death/pps and cases/pps).

# Analyze

Due to the scope of this project, a simple visual analysis should be sufficient.  
To generate graphics, a jupyter notebook with matplotlib and pandas use scatter plots to show the possible correlations.
- Load all integrated and preprocessed datasets.
- Plot data as scatterplots with x-axis as time, y-axis as case/death-amount and color as size
- Confirm or reject research question based on visual analysis
