# Top 5 economic journal paper affiliation extraction
This repository details how University names are extracted from messy data for my masters dissertation which is to construct a long-term ranking of research intensity of universities globally based on publications in the Top 5 economics journals (AER, JPE, ECTA, QJE, REStud) from 1940 to 2020.

## Table of contents
* [General information](#General-information)
* [Setup](#Setup)
* [File strucuture and code locations](#File-strucuture-and-code-locations)
* [Intended use](#Intended-use)
* [Contact](#Contact)

## General information
The project provides details on how the extraction and consolidation works, as well as some of the analysis of the data. This project is intended for research purposes, anyone is free to use the IP and the output data.

## Setup
The recommended software to run this program is Visual studio code. This project has been written to run on Mac and Windows and the file paths are linked to the Githib reposity, it will run once the requires libraries have been installed.

Libraries required:

use 'pip install' to install the libraries
json, pandas, numpy, rapidfuzz, matplotlib and requests

## Running the code
This repository has multiple individual pieces that contribute to a full picture in the end. This section details where all the pieces sit and what they are. The code has been designed so that anyone can run it and reproduce the results all that needs changing is writing to a local file path on the readers PC. If you do not want to do this in each step of code that creates data there is a folder in that section that contains the output data created in that section. Section 1 just contains input data and has no code that needs to be run but from section 2 onwards there are code files that will be run these are all detailed below. 

### 1. Input Data

#### 1.1. Tesseract affiliation output
Contains the input data used in the extraction, this is raw data from tesseract (Tesseract affiliation  data), affiliation data obtained from scopus (Scopus files),   (master lists)

#### 1.2. Processed
Contains files used to clean master listsa and merge input data together as well as checking how many affiliations exist within scopus.

#### 1.3. Scopus files
Contains sheets of raw scopus data for the different journals. There are some issues with this data being they do not use consitent naming for affiliations, sometimes an affiliation has multiple authors but only 1 has an affiliation written for them and the referencing of the affiliation to the author name is incosintent and sometimes inaccurate. 

### 2. Extracting affiliations from Tesseract
Split into 2 sections being consolidation  and fuzzy matching. There is a lot of variability within the data from different journals as well as within individual journals the data is variable. 

#### 2.1 Consolidation
JPE, RES and QJE follow the process of consolidation. The data from these jounals is structured and follows a generally consistent pattern with a few exceptions. Therefore code could be written to automate the splitting of affiliations for each author from the teseract output. 

#### 2.2. Fuzzy Matching
The tesseract information for AER was extracted through the use of Fuzzy matching. This is due to the nature of the data compared to the otehr journals.

### 3. Remaining affiliation data
There is some missing data from tesseract where the files varied too much and the data could not be extracted. For these missing entries some have been filled in manually, some have used Scopus data and others have been completed by Amazon Mechanical Turk. 

#### 3.1. Scopus 
QJE and RES have got data from scopus, for QJE pre 1980 there is alot of Scopus data used as well as a few post this where the data was not populated. For RES Scopus was used where there was missing data.

#### 3.2. Mturk
Extraction of affiliations to be sent to Mturk. This is post Tesseract, Scopus and manual extraction, this was used to get the remaining affiliations. 

### 4. Merge and standardize
Used to Merged all the different data sources together. 

#### 4.1 AER files merged together and standardized
AER contains 9340 articles, this was too intimidating to tackle all at once. It is split into 7 files that were checked 1 at a time. There were a couple of different methods used in AER to extract the data, these files split on number of author as well as when the splitting method changed. This file just merged these 7 back into 1 and makes sure all the columns are matched correctly.

#### 4.2. Mturk standardized and ECTA file produced
There are 3 Mturk files each with different columns and these needs to be matched back onto the mastersheets. This file ensures everything has the same naming. The next step is merging Mturk onto the ECTA mastersheet as all of the data for Mturk has been populated through the use of Mturk. 

### 4.3 Merge tesseract and Mturk data
Takes the standardized Mturk data produced in 4.2. and merges it onto the tesseract data produced in section 2. 

### 5. Final consolidation of all data
Up until this point there have been many different sources of data and manual corrections of data which could contain errors. This section is to do a final round of consolidation to ensure all spelling errors have been eliminated and that all different spellings of Universities have been consolidated into a single spelling.

#### 5.1. Uniques affiliation consolidation 
Takes the merged dataset from 4.3 and puts all the affiliations from every paper into an array and then only keeps the unique values. There are 37 906 affiliations in total and 3394 uniques. Next this list was manually screened to create a consolidation sheet that is 1844 rows long which corrects spellings and consolidates. This consolidtion is then applied to the uniques list which leaves 2033 uniques after the consolidation has been applied. 

#### 5.2. Final consolidation of full dataset
Performs the same consolidation as 5.1 except in this the consolidation is applied to the full dataset not just the uniques. 

#### 5.3. Full consolidation list of all spellings
Produces a final consolidation sheet which contains all the possible spellings from the dataset. This includes data from the first round of consolidation, the final round as well as all the correct spellings of affiliations. 

## Intended use
This project is intended for academic work and is free to use for anyone.

## Contact 
Created by @Matt970204 as part of my MPhil in FinTech at the University of Cape Town.
