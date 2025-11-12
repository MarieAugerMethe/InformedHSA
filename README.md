# InformedHSA

This repository contains the code and data associated with the article: 

Auger-Méthé, M, F Dupont, A Eby, KH Elliott, N Hussey, DA Lyons, M Marcoux, A Patterson,
S Shadloo, and CR Shuert (2025) Including fitness and health proxies can alter our
understanding of habitat selection. Preprint available on bioRxiv.

# Data

All the data is available in the folder `Data`

## Literature review

The literature review is available in the file `Literature_review.xlsx` 
found in the subfolder `0_Review`. 

The excel file has 3 tabs:

1. Documents: contains the information extracted from the articles. 
Specifically it contains the columns:
    - Authors: full author list
    - Article Title: title
    - Abstract: arcticle abstract
    - TitleExclude: whether or not the article was excluded while reviewing the titles
    - AbstractExlude: whether or not the article was excluded while reviewing the abstracts
    - FullTextExclude: whether or not the article was excluded while reviewing the articles
    - AccountForIndividuals: whether or not the habitat selection analysis account for individual (e.g., via random effect or separate analyses)
    - IncludeCharacteristicsOfFitnessHealth: whether or not  the habitat selection analysis include characteristics of an individual fitness or health
    - FitnessHealthCharacteristic: the fitness or health characteristics included in the habitat selection analysis
    - IncludeCharacteristicsOfFitnessHealthSpecific: More specific info on whether or not the habitat selection analysis included characteristics of an individual fitness or health
    - IncludeOtherCharacteristic: whether or not the habitat analysis include other characteristics of the individuals
    - OtherCharacteristic: the other individual characteristics was included in the habitat selection analysis
    - MethodCharacteristic: information on the method used to include individual characteristics (see keywords)
    - CommentMethodCharacteristic: additional comment on method to include individual characteristics
    - PrimaryFocus: What is the primary focus of the paper? Is it a review, methodological, theory, or empirical  paper?
    - ManagementConservationInference: whether or not conservation or management inference was made based on the results
    - Additional info on inference made: additional information on the statements
    - Species common: common species name
    - Species scientific: Latin species name
    
2. Full questions: contains the relationship between the column short form name and the full question associated with that column.

3. Keywords to use: contains a list of keywords to use from some of the columns (to help consistency).

## Simulations

The simulations do not require data. 
However, as some code sections take hours to run, 
we have saved the results in .csv files. The files are:
 - `sim.rsf.sc1_20251112.csv`
 - `sim.rsf.sc2_20251112.csv`
 - `sim.rsf.sc3_20251112.csv`
 - `sim.ssf.sc1_20251112.csv`
 - `sim.ssf.sc2_20251112.csv`

These files are not stand alone files. 
They are meant to be loaded in the simulation code and all of the columns are detailed in the code itself.

# Code

## Literature review

The code to reproduce the figures of the literature review is available in `0_review.Rmd`. 
A compiled version is also available in `0_review.html`.

## Simulations

The code to reproduce simulations and the associated figures is available in two sets of files. 
The first set of files are for 
