# **IL5pred**
A computational method to predict and scan IL-5 inducing peptides.
## Introduction
IL5pred is developed to predict, scan, and design IL-5 inducing peptides. More information on IL5pred web server is available at https://webs.iiitd.edu.in/raghava/il5pred. Please read/cite the content about the IL5pred for complete information including the algorithm behind the approach. 

## Reference
Devi NL, Sharma N and Raghava GPS (2023) A web server for predicting and scanning of IL-5 inducing peptides using alignment-free and alignment-based method. <a href="https://doi.org/10.1016/j.compbiomed.2023.106864">Computers in Biology and Medicine, DOI:10.1016/j.compbiomed.2023.106864</a>.
## Model
The best Random Forest-based hybrid model (RF(DPC)+BLAST) is implemented in the webserver. 

## Standalone
Standalone version of IL5pred is written in python3 and the following libraries are necessary for a successful run:
- scikit-learn
- Pandas
- Numpy
- blastp

## Important Note
- Due to large size of the model file, we have not included it in the zipped folder or GitHub repository, thus to run standalone successfully you need to download model file and then unzip them.
- Make sure you extract the download zip files in the directory where main execution file i.e. il5pred.py is available.
- To download the model folder click [here].(https://webs.iiitd.edu.in/raghava/il5pred/model.zip)

## Minimum usage
To know about the available option for the standalone, type the following command:
```
python3 il5pred.py -h
```
To run the example, type the following command:
```
python3 il5pred.py -i example_input.fa
```
This will predict if the submitted sequences are IL-5 inducers or Non-inducers. It will use other parameters by default. It will save the output in "outfile.csv" in CSV (comma-separated variables).

## Full Usage: 
```
Following is complete list of all options, you may get these options
usage: il5pred.py [-h] 
                       [-i INPUT]
                       [-o OUTPUT]
		       [-j {1,2,3}]
		       [-t THRESHOLD]
                       [-w {9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25}]
		       [-d {1,2}]
```
```
Please provide the following arguments

optional arguments:
  -h, --help            show this help message and exit
  -i INPUT, --input INPUT
                        Input: protein or peptide sequence(s) in FASTA format
                        or single sequence per line in a single letter code
  -o OUTPUT, --output OUTPUT
                        Output: File for saving results by default outfile.csv
  -j {1,2,3}, --job {1,2,3}
                        Job Type: 1:Predict, 2: Design, 3:Scan, by default 1
  -t THRESHOLD, --threshold THRESHOLD
                        Threshold: Value between 0 to 1 by default 0.21
  -w {9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25}, --winleng {9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25}
                        Window Length: 9 to 20 (scan mode only), by default 9
  -d {1,2}, --display {1,2}
                        Display: 1:IL-5 inducing peptides only, 2: All peptides, by default 1
```

**Input File:** Allows user to provide input in FASTA format.

**Output File:** Program will save the results in CSV format, in case the user does not provide the output file name, it will be stored in "outfile.csv".

**Threshold:** User should provide a threshold between 0 and 1, by default it's 0.21.
