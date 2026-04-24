# Microtiter_plate_Antibiotic_Resistance_Analysis

Files used to obtain growth curve plots and growth parameter data in broth dilution assays done on 96-well plate, subjecting various strains to serial dillutions of various different antibiotics

## Getting started

Download plate_analysis_pipeline.py (main file) and fill in your experiment data with the template provided in Example_plate_setup.txt (explained more carefully below), update the file paths and other parameters in the main file and run. The output will be a folder containing the growth curve plots for control and testing wells, growth parameter plots descriminated by strain and test and an excel workbook containing all the values obtained for the parameters.


## plate_analysis_pipeline Functions

### get_plate_data
