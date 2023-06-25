# Affiliations

## Table of contents

## General information
This repository is how I went about my masters dissertation which is to construct a long-term ranking of research intensity of universities globally based on publications in the Top 5 economics journals (AER, JPE, ECTA, QJE, REStud) from 1940 to 2020.
The repository takes in outputted raw NLP data from papers published and cleans this data, as well as visualising the data. 

##

## Setup 
All source files have been included under 'Tesseract output json files'.
The project is witten using MACOS and files refecinging will need to be adapted for Windows use. 

## File structure
The project contains the source data as well as the different iterations in getting to the final result. 

### Masterlists 
Contains the truth files for the papers downloaded from the journals. 

### 1 Fuzzy matching 
Final methodology in trying to clean the data. This is the code that was selected in the end and worked. 

### 2 Manual cleaning
The first failed iteration of the project. This was an attempt at maually coding in rules to split the data. In the end this couldn't work due to the variability in the data. Especially when switching between journals.
