# Top 5 economic journal paper affiliation extraction

## General information
This repository detials how University names are extracted from messy data for my masters dissertation which is to construct a long-term ranking of research intensity of universities globally based on publications in the Top 5 economics journals (AER, JPE, ECTA, QJE, REStud) from 1940 to 2020.
The repository takes in outputted raw NLP data from papers published and cleans this data, as well as visualising the data. 

## Setup 
All source files have been included under 'Tesseract output json files'.
The project is witten using MACOS and files refecinging will need to be adapted for Windows use. 

### 1_Input files and processing input files

#### 1_1_Input files
Contains the input data used in the extraction, this is raw data from tesseract (Tesseract affiliation  data), affiliation data obtained from scopus (Scopus files),   (master lists)

#### 1_2_Processing input files
Contains files used to clean master listsa and merge input data together as well as checking how many affiliations exist within scopus.

## 2_Extracting affilitions
Split into 2 sections of manual extraction and fuzzy matching. These are the 2 thoughts on how to extract affilitons from the different journals. 

### 1_Manual splitting
The first failed iteration of the project. This was an attempt at maually coding in rules to split the data. In the end this couldn't work due to the variability in the data. Especially when switching between journals.

### 2_Fuzzy matching
Within fuzzy matching there are the 5 journals each contains its own notebook for splitting as well as another folder which contains the combined splitting from multiple journals and output. UNiversity list contains the unique Universities that have been used in the fuzzy matcher which produce an output.
