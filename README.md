# CBIOS_Practicum
Repo for CBIOS Project on Modeling AMR Data

This repo is for a project completed in the Fall of 2020 for CBIOS Practicum at Penn State.

The overall outline of the project is as follows:

  Data - Antimicrobial resistance wherein each column is a gene ortholog matched to the KEGG ontology database and each individual is a microbe isolate from the S. pneumoniae organism. A single catagorical feature representing the antibiotic the isolate was exposed to was encoded as 6 additional features to create underlying correlation between antibiotic treatments. Finally a single column labeled AMR is a binary variable describing wheather or not the isolate was resistant to the treatment or not.
         
  Data Wrangling - We begin with the CBIOS_Project.ipynb code which performs the data wrangling for our project; first we read in our larger data file and consolidate all of the S. pneumoniae isolates into a single dictionary. We then take all of the keys corresponding to different antibiotic treatments and concatinate all of the treatments on the union of all treaments. Then we encode our treatment using one-hot-encoding to prevent ordination and create an underlying correlation between treatments. Finally we save this as our dataset available for download from this repo
                   
  Analysis - For the analysis we switch over to the CBIOS_Project.Rmd code which uses the glmnet function for performing feature screening and cross validation. We begin with splitting the data into testing and training sets at 25% and 75% respectively. We then perform our lasso path and cross validation, plotting each and obtaining our lambdas corresponding to minimum mean cross-validated error & error within one standard error of the minimum. The results from this screen are seen in the Lasso_Path.pdf & Cross_Validation.pdf files. Our original idea was to take only the top ~ P/log(P) number of features contributing to overall.
            
