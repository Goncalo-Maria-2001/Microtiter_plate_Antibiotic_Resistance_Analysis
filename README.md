# Microtiter_plate_Antibiotic_Resistance_Analysis

Files used to obtain growth curve plots and growth parameter data in antibiotic resistance broth dilution assays done on 96-well plate, subjecting various strains to serial dillutions of various different antibiotics

## Getting started

Download plate_analysis.py (main file) and fill in your experiment data with the template provided in Example_plate_setup.txt (explained more carefully below), update the file paths and other parameters in the main file and run. The output will be a folder containing the growth curve plots for control and testing wells, growth parameter plots descriminated by strain and test and an excel workbook containing all the values obtained for the parameters.


## Functions

### plate_analysis.recursive_dict()

Defines a recursive default dict object for other functions to use.

### plate_analysis.get_plate_setup(path_to_plate_setup)

Input: path to a plate_setup.txt file with information detailing how the assay was done.

Output: generates a nested dictionary (plate without data) which stores the information from the experiment in a structured way as displayed below:

<img width="1920" height="1080" alt="Dictionary (1)" src="https://github.com/user-attachments/assets/a796445f-c6eb-4c6d-8c1c-39cb791b7fa0" />

Where the tests, other controls, strains and replicates dictionaries can contain multiple dictionaries with the structure of test 1, control 1, strain 1 and replicate 1 respectively depending on the path_to_plate_setup provided.

### plate_analysis.add_plate_data(plate_setup,path)

Input: A plate_analysis output dictionary and the path to the output of Tecan i-control converted to .csv

Output: A nested dictionary (plate with data) with the following structure

<img width="1920" height="1080" alt="Dictionary" src="https://github.com/user-attachments/assets/0e15d5a7-5113-4f6e-b550-2ad0be9729a7" />

Where the tests, other controls, strains and replicates dictionaries can contain multiple dictionaries with the structure of test 1, control 1, strain 1 and replicate 1 respectively depending on the path_to_plate_setup provided.

### plate_analysis.create_save_dirs(plate,save_path):

Input: A plate without data or plate with data dictionary, path to place results folder

Output: Creates the directories where the output plots and workbooks will be stored and stores their paths in a dictionary with the following structure.

<img width="1920" height="1080" alt="Dictionary (1)" src="https://github.com/user-attachments/assets/73935444-da8d-43b7-85d7-10395cd6ed2b" />

### plate_analysis.has_fittable_growth(df,min_OD_change):

Input: A pandas DataFrame with two columns: 'Time' and 'OD' representing the evolution of OD over time for a given well and a float corresponding to the minimun OD overall change in the well for which bacterial growth is considered to have occured

Output: True or False

Does a series of tests on the well data to determine if growth is considered to have occured

### plate_analysis.lag_phase_finder(df, slope_threshold):

Input: A pandas DataFrame with two columns: 'Time' and 'OD' representing the evolution of OD over time for a given well and
 a float represnting the population growth from one cycle to the next at which the log phase begins

Output: A float representing the cycle at which the lagphase ended
