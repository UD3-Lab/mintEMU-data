# mintEMU project data

## Table of Contents

-   [1. GENERAL INFORMATION](#1-general-information)
-   [2. METHODOLOGICAL INFORMATION](#2-methodological-information)
    -   [2.1 Research questions, methods and envisioned uses](#21-research-questions-methods-and-envisioned-uses)
    -   [2.2 Methods for processing the data](#22-methods-for-processing-the-data)
    -   [2.3 Instrument- or software-specific information](#23-instrument--or-software-specific-information)
-   [3. FILE OVERVIEW](#3-file-overview)
    -   [3.1 File List](#31-file-list)
    -   [3.2 Relationship between files](#32-relationship-between-files)
    -   [3.3 File formats and naming conventions](#33-file-formats-and-naming-conventions)
-   [4. DATA-SPECIFIC INFORMATION](#4-data-specific-information)
    -   [4.1 Thesis Data](#41-thesis-data)
-   [5. SHARING/ACCESS INFORMATION](#5-sharingaccess-information)
    -   [5.1 Licenses/restrictions placed on the data](#51-licensesrestrictions-placed-on-the-data)
    -   [5.2 Links to other resources](#52-links-to-other-resources)
    -   [5.3 Recommended citation for this dataset](#57-recommended-citation-for-this-dataset)

# 1. GENERAL INFORMATION

## 1.1 Title of Dataset

mintEMU project data

## 1.2 Dataset description

This dataset contains data collected in the mintEMU research project on theses from the European post-Master of Urbanism (EMU) run by the Department of Urbanism at the Faculty of Architecture and the Built Environment. Prompted by the closure of EMU, the mintEMU project aims to describe the legacy of the program, including the distinctive features of its didactics, and the emergence and evolution of major urbanism topics. To that end, we analysed its output — 83 theses with an average of 25000 words — produced over the years for the entire duration of the program with a text analysis approach. The result of the mintEMU project is a reproducible research compendium that consists of a FAIR dataset, a journal article, and a companion dashboard that makes the findings available to the public in an interactive form. The FAIR dataset is included in this publication. Additional details about the project can be accessed at https://github.com/UD3-Lab/mintEMU.

## 1.3 Author Information

A. Principal Investigator

-   Name: Claudiu Forgaci (mintEMU project, package development & dataset)
-   Institution: Delft University of Technology, Faculty of Architecture and the Built Environment
-   Address: Julianalaan 134, 2628AL Delft, South Holland, The Netherlands
-   Email: [C.Forgaci\@tudelft.nl](mailto:C.Forgaci@tudelft.nl){.email}

B. Associate or Co-investigator

-   Name: Aleksandra Wilczynska (mintEMU package development & dataset)
-   Institution: Delft University of Technology, TU Delft Library
-   Address: Prometheusplein 1, 2628 ZC Delft, South Holland, The Netherlands
-   Email: [A.Wilczynska\@tudelft.nl](mailto:A.Wilczynska@tudelft.nl){.email}

## 1.4 Dates of data collection

-   2022-2023

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

mintEMU is a text analysis project meant to reveal topics, and evolutions thereof, from theses published throughout the program between 2007 and 2021. The theses are available in PDF format with complex layouts typical to an urbanism project in which text and various types of graphics are combined. As a text mining project, mintEMU required a machine-readable version of the thesis texts. The dataset published here, extracted from the original PDF files, meets that requirement. Moreover, the thesis text data is accompanied by metadata in a linked data frame.

### 2.1.1 Research questions

The following research questions used in the mintEMU project guided the preparation of this dataset:

1.  What were the main topics addressed in the EMU program?
    -   Data requirement: The text of all theses is cleaned and stored in a text column that can be read by a text analysis workflow.
2.  How did those topics evolve throughout the program between 2007-2021?
    -   Data requirement: Information about the time of graduation (year and semester) is provided.

### 2.1.2 Envisioned uses of the dataset

The mintEMU project data can be used:  
-   for unsupervised machine learning applications, such as the LDA topic model used in the mintEMU project;
-   as training data in supervised machine learning models, such as classification models to predict the topic in a larger corpus of urbanism theses;
-   in combination with computer vision applications in which text analysis provides information for labelling images found in the theses.

Analyses in the mintEMU project were carried out on words and ngrams which discard the relationship between such tokens. However, cases, punctuation and line breaks marking the end of paragraphs were preserved in this dataset to allow for sentence- and paragraph-level analysis as well.

## 2.2 Methods for processing the data

### 2.2.1 Data collection

-   Metadata was obtained from the TU Delft education repository in CSV format. Metadata for theses that were not submitted to the repository were added from EMU coordination records.
-   Full texts of the theses were obtained upon request from the TU Delft education repository via email. For theses that were not available on the repository, a request via email was sent to the authors.
-   Thesis authors were asked to provide their permission in writing for their thesis to be used in this project. Only theses for which permission was granted were included in the dataset.

### 2.2.2 Data processing

-   Full-text data was extracted from the PDF version of the theses using the PyMuPDF Python package. The full extracted text was anonymised and cleaned and it was stored in a `text_raw` column.
-   To anonymise the dataset, we removed personal information, such as names and email addresses, from the metadata and we replaced the author name in the full text with the marker `AUTHOR_REMOVED`.
-   Cleaning consisted of the removal of hyphens, line breaks, page numbers, and occurrences of the title, mostly found in page headers or footers.
-   The front matter and back matter were removed, as they did not contain content relevant to text analysis.

## 2.3 Instrument- or software-specific information

-   Python 3.9:latest and PyMuPDF 1.21.0 were used for text extraction
-   R version 4.3.0 "Already Tomorrow" with RStudio version 2023.06.2+561 was used for data processing

# 3. FILE OVERVIEW

Are there multiple versions of the dataset? No

## 3.1 File List

-   "emu-metadata.csv": thesis metadata
-   "emu-raw.csv": raw theses text data
-   "theses-per-year.csv": summary table of theses available in the dataset

## 3.2 Relationship between files:

-   The files can be linked with the `ID` column containing unique thesis IDs

## 3.3 File formats and naming conventions

### 3.3.1 File formats

-   CSV - tabular data

### 3.3.2 Naming conventions

-   files named lowercase, spaces replaced with dashes (dash-case)
-   in tabular data, variable names use snake case; except for the ID, all variables are lowercase

# 4. DATA-SPECIFIC INFORMATION

-   Missing data code: NA
-   Not Applicable: N/A
-   Specialised formats or other abbreviations used: N/A

## 4.1 Thesis data  

### 4.1.1 emu-metadata.csv

1.  Number of variables: 10

2.  Number of cases/rows: 68

3.  Variable List:

"ID"  
- Full name: Thesis identifier  
- Description: Unique thesis identifier  
- Type of variable: Numerical  
- Unit of measurement: N/A  
- Number of missing values: 0  

"grad_year"  
- Full name: Graduation year  
- Description: The year when the thesis was published  
- Type of variable: Numerical  
- Unit of measurement: N/A  
- Number of missing values: 0

"grad_sem"  
- Full name: Graduation semester  
- Description: The semester when the student graduated  
- Type of variable: Categorical, Nominal 
- Categories: "Spring", "Fall"  
- Unit of measurement: N/A  
- Number of missing values: 0  

"full_title"  
- Full name: Full title of the thesis  
- Description: Full title of the thesis, including main title and subtitle, separated by a colon
- Type of variable: String  
- Unit of measurement: N/A  
- Number of missing values: 0  

"title"  
- Full name: Title of the thesis  
- Description: Title of the thesis  
- Type of variable: String  
- Unit of measurement: N/A  
- Number of missing values: 0  

"subtitle"  
- Full name: Subtitle of the thesis  
- Description: Subtitle of the thesis, when available
- Type of variable: String  
- Unit of measurement: N/A  
- Number of missing values: 6  

"loc"  
- Full name: Thesis location  
- Description: Location of the case used in the thesis  
- Type of variable: String  
- Unit of measurement: N/A  
- Number of missing values: 0

"long"  
- Full name: Longitude of thesis location  
- Description: Longitude obtained from location geocoded via the OSM Nominatim API  
- Type of variable: Numerical  
- Unit of measurement: Degrees ranging from 0° at the Prime Meridian to +180° eastward and −180° westward  
- Number of missing values: 0

"lat"  
- Full name: Latitude of thesis location  
- Description: Latitude obtained from location geocoded via the OSM Nominatim API  
- Type of variable: Numerical  
- Unit of measurement: Degrees North or South of the Equator to 90° at the North or South poles  
- Number of missing values: 0

"abstract"  
- Full name: Thesis abstract  
- Description: Thesis abstract submitted to the TU Delft education repository  
- Type of variable: String  
- Unit of measurement: N/A  
- Number of missing values: 26

4.  File size: 94 KB

### 4.1.2 emu-raw.csv

1.  Number of variables: 2

2.  Number of cases/rows: 68

3.  Variable List:

"ID"  
- Full name: Thesis identifier  
- Description: Unique thesis identifier  
- Type of variable: Numerical  
- Unit of measurement: N/A  
- Number of missing values: 0  

"text_raw"  
- Full name: Raw thesis text  
- Description: Anonymised and cleaned thesis text extracted from the PDF versions of the theses obtained either from the TU Delft education repository or via email from the authors  
- Type of variable: String  
- Unit of measurement: N/A  
- Number of missing values: 0

4.  File size: 11161 KB

### 4.1.3 theses-per-year.csv

1.  Number of variables: 4

2.  Number of cases/rows: 15

3.  Variable List:

"grad_year"  
- Full name: Graduation year  
- Description: The year when the thesis was published  
- Type of variable: Numerical  
- Unit of measurement: N/A  
- Number of missing values: 0

"n_total"  
- Full name: Total number of theses  
- Description: Total number of theses published per year  
- Type of variable: Numerical  
- Unit of measurement: N/A  
- Number of missing values: 0

"n_pdfs"
- Full name: Number of PDFs
- Description: Number of theses for which PDF was available 
- Type of variable: Numerical  
- Unit of measurement: N/A  
- Number of missing values: 0

"n_permissions"
- Full name: Number of PDFs
- Description: Number of theses for which permission was obtained from the authors
- Type of variable: Numerical  
- Unit of measurement: N/A  
- Number of missing values: 0

4.  File size: 0.2 KB

### 4.1.4 Total file size: 11255 KB

# 5. SHARING/ACCESS INFORMATION

## 5.1 Licenses/restrictions placed on the data:

This dataset is freely available for reuse. If you make use of data from this data set, please credit the authors.

## 5.2 Links to other resources:

### 5.2.1 Links to publications that cite or use the data:

N/A

### 5.2.2 Links to other publicly accessible locations of the data:

N/A

### 5.2.3 Links/relationships to ancillary data sets:

N/A

### 5.2.4 Links to publicly accessible scripts for analysis of the dataset:

[mintEMU repository](https://github.com/UD3-Lab/mintEMU)

### 5.2.5 Was data derived from another source?

Yes. The data was derived from metadata from the TU Delft education repository and from the PDF full texts of the theses.

## 5.3 Recommended citation for this dataset:

Forgaci, C., Wilczynska, A. (2023). Mining Theses: The EMU Program (mintEMU) project data [dataset]. Retrieved from <http://doi.org/10.4121/7175050b-aebf-41f7-835b-4f23233c3ded>

---

This README.md uses a template that was generated on 2022-04-19 by Claudiu Forgaci and Adele Therias according to the 4TU.ResearchData [Guidelines for creating a README file](https://data.4tu.nl/info/en/use/publish-cite/upload-your-data-in-our-data-repository) and the Cornell University template [Guide to writing "readme" style metadata](https://cornell.app.box.com/v/ReadmeTemplate).
