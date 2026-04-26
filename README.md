# Microtiter_plate_Antibiotic_Resistance_Analysis

Files used to obtain growth curve plots and growth parameter data in broth dilution assays done on 96-well plate, subjecting various strains to serial dillutions of various different antibiotics

## Getting started

Download plate_analysis.py (main file) and fill in your experiment data with the template provided in Example_plate_setup.txt (explained more carefully below), update the file paths and other parameters in the main file and run. The output will be a folder containing the growth curve plots for control and testing wells, growth parameter plots descriminated by strain and test and an excel workbook containing all the values obtained for the parameters.


## Functions

### plate_analysis.recursive_dict()

Defines a recursive default dict object for other functions to use

### plate_analysis.get_plate_setup(path_to_plate_setup)

Generates a nested dictionary (plate) which stores the information from the experiment in a structured way as displayed below:

<img width="1920" height="1080" alt="Dictionary (1)" src="https://github.com/user-attachments/assets/a796445f-c6eb-4c6d-8c1c-39cb791b7fa0" />

Where the tests, other controls, strains and replicates dictionaries can contain multiple dictionaries with the structure of test 1, control 1, strain 1 and replicate 1 respectively depending on the path_to_plate_setup provided. Additionally 
