# Microtiter_plate_Antibiotic_Resistance_Analysis

Files used to obtain growth curve plots and growth parameter data in broth dilution assays done on 96-well plate, subjecting various strains to serial dillutions of various different antibiotics

## Getting started

Download plate_analysis.py (main file) and fill in your experiment data with the template provided in Example_plate_setup.txt (explained more carefully below), update the file paths and other parameters in the main file and run. The output will be a folder containing the growth curve plots for control and testing wells, growth parameter plots descriminated by strain and test and an excel workbook containing all the values obtained for the parameters.


## Functions

### plate_analysis.recursive_dict()

Defines a recursive default dict object for other functions to use

### plate_analysis.get_plate_setup(path)

Generates a dictionary with the following structure so that the information from the experiment is organized in the following way:

<img width="1920" height="1080" alt="Strain 1 (6) (1)" src="https://github.com/user-attachments/assets/88a1dc3f-395c-4f09-8228-4a992ae55993" />

