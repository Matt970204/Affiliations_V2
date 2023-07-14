# Top 5 economic journal paper affiliation extraction

## Table of contents
* [General information](#General-information)
* [Setup](#Setup)
* [File strucuture and code locations](#File-strucuture-and-code-locations)
* [Intended use](#Intended-use)
* [Contact](#Contact)

## General information
This repository detials how University names are extracted from messy data for my masters dissertation which is to construct a long-term ranking of research intensity of universities globally based on publications in the Top 5 economics journals (AER, JPE, ECTA, QJE, REStud) from 1940 to 2020.
The repository takes in outputted raw NLP data from papers published and cleans this data, as well as visualising the data. 

## Setup 
All source files have been included under 'Tesseract output json files'.
The project is witten using MACOS and files refecinging will need to be adapted for Windows use. 

## File strucuture and code locations
This repository has multiple individual pieces that contribute to a full picture in the end. This section details where all the pieces sit and what they are.

### 1 Input files and processing input files

#### 1_1 Input files
Contains the input data used in the extraction, this is raw data from tesseract (Tesseract affiliation  data), affiliation data obtained from scopus (Scopus files),   (master lists)

#### 1_2 Processing input files
Contains files used to clean master listsa and merge input data together as well as checking how many affiliations exist within scopus.

## 2 Extracting affilitions
Split into 2 sections of manual extraction and fuzzy matching. These are the 2 thoughts on how to extract affilitons from the different journals. 

### 2_1 Manual splitting
The first failed iteration of the project. This was an attempt at maually coding in rules to split the data. In the end this couldn't work due to the variability in the data. Especially when switching between journals.

### 2_2 Fuzzy matching
Within fuzzy matching there are the 5 journals each contains its own notebook for splitting as well as another folder which contains the combined splitting from multiple journals and output. UNiversity list contains the unique Universities that have been used in the fuzzy matcher which produce an output.

## Simplified start to finish of project

### General data placement on page

In the 5 journals there are 3 general placements of the University name and author name. AER and QJE have this at the bottom of their last page. JPE and RES are on the first page. ECTA is either before references, appendix or in the footnotes. This is a general placement and it does change in each journal throughout the years, which adds to the complexity of the manual cleaning. There are also changes in line spacing and punctuation picked up by the PDF reader, with these combined it is near impossible to manually do this accurately.

The 3 images show this what this looks like in a PDF.

![Bottom](./Miscellaneous/Bottom%20of%20last%20page.png)

![Top](./Miscellaneous/Top%20of%20first%20page%20under%20heading.png)

![Appendix](./Miscellaneous/Footnotes%20refernces%20appendix.png)

### Raw tesseract data
The data outputted is in this format with the affiliations line contaning the round about placement of the affiliation. It is generally within this text, although the output does contain additional text either above or below the string with the contained affilliation.

![AER tesseract](./Miscellaneous/AER%201.png)

### Cummulative plot of papers published over time for top 10 publishers in all journals

### Ranking of Universities based on number of publications per decade

## Intended use
This project is intended for academic work and is free to use for anyone.
6543
## Contact 
Created by @Matt970204 as part of my MPhil in FinTech at the University of Cape Town.

## Addito
