This README.md file template was generated on 2022-04-19 by Claudiu Forgaci and Adele Therias according to the 4TU.ResearchData [Guidelines for creating a README file](https://data.4tu.nl/info/en/use/publish-cite/upload-your-data-in-our-data-repository) and the Cornell University template [Guide to writing "readme" style metadata](https://cornell.app.box.com/v/ReadmeTemplate).

# Mining theses: The EMU program (mintEMU) project data 

## Table of Contents

- [1. GENERAL INFORMATION](#1-general-information)
- [2. METHODOLOGICAL INFORMATION](#2-methodological-information)
  - [2.1 Research questions, methods and envisioned uses](#21-research-questions-methods-and-envisioned-uses)
  - [2.2 Methods for processing the data](#22-methods-for-processing-the-data)
  - [2.3 Instrument- or software-specific information](#23-instrument--or-software-specific-information)
- [3. FILE OVERVIEW](#3-file-overview)
  - [3.1 File List](#31-file-list)
  - [3.2 Relationship between files](#32-relationship-between-files)
  - [3.3 File formats and naming conventions](#33-file-formats-and-naming-conventions)
- [4. DATA-SPECIFIC INFORMATION](#4-data-specific-information)
  - [4.1 Data Category A](#41-data-category-a)
  - [4.2 Data Category B](#42-data-category-b)
  - [4.3 Data Category C](#43-data-category-c)
  - [4.4 Data Category D](#44-data-category-d)
- [5. SHARING/ACCESS INFORMATION](#5-sharingaccess-information)
  - [5.1 Licenses/restrictions placed on the data](#51-licensesrestrictions-placed-on-the-data)
  - [5.2 Links to other resources](#52-links-to-other-resources)
  - [5.3 Recommended citation for this dataset](#57-recommended-citation-for-this-dataset)


# 1. GENERAL INFORMATION

## 1.1 Title of Dataset
mintEMU project data 

## 1.2 Dataset description
This dataset contains data collected in the mintEMU research project on theses from the European post-Master of Urbanism (EMU) of the Department of Urbanism at the Faculty of Architecture and the Built Environment. Prompted by the closure of EMU, the mintEMU project aims to describe the legacy of the program, including the distinctive features of the didactics employed in it, and the emergence and evolution of major urbanism topics. To that end, we analysed its output — 83 theses of ???100+ pages each — produced over the years for the entire duration of the program with a text analysis approach. The result of the project of the mintEMU project is a reprodcuible research compendium that consists of a FAIR dataset, a journal article, and a companion dashboard that makes the findings available to the wider public in an interactive form. The FAIR dataset is included in this publication. Additional details about the project can be accessed [here](https://...).

## 1.3 Author Information

A. Principal Investigator  
- Name: Claudiu Forgaci (mintEMU project & dataset)
- Institution: Delft University of Technology, Faculty of Architecture and the Built Environment
- Address: Julianalaan 134, 2628AL Delft, South Holland, The Netherlands
- Email: C.Forgaci@tudelft.nl

B. Associate or Co-investigator. 
- Name: Aleksandra Wilczynska (mintEMU package development & dataset)
- Institution: Delft University of Technology, TU Delft Library
- Address: Prometheusplein 1, 2628 ZC Delft, South Holland, The Netherlands
- Email: A.Wilczynska@tudelft.nl

## 1.4 Dates of data collection

- 2022-2023

## 1.5 Geographic location of data collection

Delft, NL

## 1.6 Keywords

Text mining, text analysis, urbanism, EMU

## 1.7 Language

English

## 1.8 Information about funding sources that supported the collection of the data

The mintEMU research project received in-kind support for reproducible package development and data refinement from the TU Delft Digital Competence Center.

# 2. METHODOLOGICAL INFORMATION
## 2.1 Research questions, methods and envisioned uses

mintEMU is a text analysis project meant to reveal topics and evolutions thereof throughout the entire duration of the program between 2007-2021. The theses are available in PDF format with complex layouts typical to an urbanism project in which text and various types of graphics are combined. As a text mining project, mintEMU required a machine readable version of the thesis texts. The dataset published here, extracted from the original PDF files, meets that requirement. Moreover, the thesis text data is combined with metadata in a single tidy data frame that can be easily used as input in downstream analyses.

### 2.1.1 Research questions

The following research questions used in the mintEMU project guided the preparation of this dataset:

1. What were the main topics addressed in the EMU program?
    - Data requirement: The text of all theses is cleaned and stored in a text column that can be read in by a text analysis workflow.
    
2. How did those topics evolve throughout the duration of the program between 2007-2021?
    - Data requirement: Information about the time of graduation (year and semester) is provided.

3. To what extent were the topics and evolution thereof influenced by the assignments given to the students throughout their studies leading up to their thesis?
    - Data requirement: Information about the assignments given in each semester is included in the dataset.

4. To what extent were the topics and evolution thereof influenced by the exchange semester followed by the students?
    - Data requirement: For each thesis, the location of the exchange semester in one of the other three universities of the EMU program is given.

### 2.1.2 Envisioned uses of the dataset  

The mintEMU project data can be used:
- for unsupervised machine learning applications, such as the LDA topic model used in the mintEMU project;
- for supervised machine learning applications, such as classification models to predict the topic in a larger corpus of urbanism theses;
- in combination with computer vision applications in which text analysis provides information for labelling images found in the theses.

## 2.2 Methods for processing the data

### 2.2.1 Data collection
- Metadata was obtained from the TU Delft education repository in CSV format. Metadata for theses that were not submitted to the repository were added from EMU coordination records.
- Full texts of the theses were obtained upon request from the TU Delft education repository via email. For theses that were not available on the repository, a request via email was sent to the authors.
- Theses authors were asked to provide their permission in writing for their thesis to be used in this project. Only theses for which permission was granted were included in the analysis.

### 2.2.2 Data processing
- Full text data was extracted from PDF version of the theses using the PyMuPDF Python package. The full extracted text was anonymised and stored in the `text_raw` column of the data.
- To anonymise the dataset, we removed personal information, such as names and email addresses, from the metadata and we replaced the author name in the full text with the marker `AUTHOR_REMOVED`.
- We created the `text_clean` variable with a cleaned version of `text_raw`.

## 2.3 Instrument- or software-specific information

- Python 3.9.7 and PyMuPDF 1.21.0 were used for text extraction
- R version 4.3.0 "Already Tomorrow" with RStudio version 2023.03.1+446 were used for data processing

# 3. FILE OVERVIEW
Are there multiple versions of the dataset? No

## 3.1 File List
- "emu-theses.csv": EMU theses data and metadata

## 3.2 Relationship between files:
- Not applicable

## 3.3 File formats and naming conventions
### 3.3.1 File formats
- csv - tabular data

### 3.3.2 Naming conventions
- files named lower case, spaces replaced with dashes (dash-case)
- in tabular data, variable names use snake case

# 4. DATA-SPECIFIC INFORMATION
- Missing data code: NA
- Not Applicable: N/A

## 4.1 Thesis data

### 4.1.1 emu-theses.csv
1. Number of variables: 10

2. Number of cases/rows: 83

3. Variable List:

"id"
- Full name: Thesis identifier
- Description: Unique thesis identifier
- Type of variable: Numerical
- Unit of measurement: N/A
- Number of missing values: 0

"graduation_year"
- Full name: Graduation year
- Description: The year when the student graduated
- Type of variable: Numerical
- Unit of measurement: N/A
- Number of missing values: 0

"graduation_semester"
- Full name: Graduation semester
- Description: The semester when the student graduated
- Type of variable: Categorical, Nominal
- Categories:
    - spring
    - autumn
- Unit of measurement: N/A
- Number of missing values: 0

"title"
- Full name: Title of the thesis
- Description: Full title of the thesis
- Type of variable: Categorical, Nominal
- Unit of measurement: N/A
- Number of missing values: 0

"location"
- Full name: Thesis location
- Description: Location of the case used in the thesis
- Type of variable: Categorical, Nominal
- Unit of measurement: N/A
- Number of missing values: 0

"longitude"
- Full name: Longitude of thesis location
- Description: Longitude obtained from location geocoded via the OSM Nominatim API
- Type of variable: Numerical
- Unit of measurement: Degrees ranging from 0° at the Prime Meridian to +180° eastward and −180° westward
- Number of missing values: 

"latitude"
- Full name: Latitude of thesis location
- Description: Latitude obtained from location geocoded via the OSM Nominatim API
- Type of variable: Numerical
- Unit of measurement: Degrees North or South of the Equator to 90° at the North or South poles
- Number of missing values: 0

"abstract"
- Full name: Thesis abstract
- Description: Thesis abstract submitted in the TU Delft reducation repository
- Type of variable: String
- Unit of measurement: N/A
- Number of missing values: ???

"text_raw"
- Full name: Raw thesis text
- Description: Anonymised thesis text extracted from the PDF versions of the theses obtained either from the TU Delft education repository or via email from the authors
- Type of variable: String
- Unit of measurement: N/A
- Number of missing values: 0

"text_clean"
- Full name: Cleaned thesis text
- Description: Thesis text after the removal of ??? from the raw text
- Type of variable: String
- Unit of measurement: N/A
- Number of missing values: 0 

4. Specialised formats or other abbreviations used: N/A

5. Total file size: ??? KB

# 5. SHARING/ACCESS INFORMATION
## 5.1 Licenses/restrictions placed on the data:
This dataset is freely available for reuse. If you make extensive use of data from this data set, please credit the authors.

## 5.2 Links to other resources:

### 5.2.1 Links to publications that cite or use the data:
N/A

### 5.2.2 Links to other publicly accessible locations of the data: 
N/A

### 5.2.3 Links/relationships to ancillary data sets: 
N/A

### 5.2.4 Links to publicly accessible scripts for analysis of the dataset:
- [mintEMU repository](https://github.com/UD3-Lab/mintEMU) ??? Let's use a Zenodo snapshot, just in case the repository migrates to another organisation

### 5.2.5 Was data derived from another source?
Yes. The data was derived from metadata from the TU Delft education repository and from the PDF full texts of the theses.

## 5.3 Recommended citation for this dataset:
Forgaci, C., Wilczynska, A. (2023). Mining Theses: The EMU Program (mintEMU) project data [dataset]. Retrieved from ??? add doi after reserving one in 4TU.ResearchData ???
