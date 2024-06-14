## CS613 
## Jack Anderson
## Music Genre Classification Analysis using Mel-Frequency Cepstral Coefficients as Features

## Prerequisites
In order to run the project you will need:
 - Python 3.11.5 is what I used however I am not doing anything super specific to that version
 - Jupyter Notebook
 - The following Python packages: numpy, pandas, matplotlib, sklearn, librosa, seaborn, and tensorflow
    - `pip install numpy pandas matplotlib scikit-learn librosa seaborn tensorflow`

## Data Collection
In order to collect the data used for training the model, you will need the GTZAN dataset in the base directory, with the following structure.
Data/
    genres_original/
        blues/
        classical/
        country/
        disco/
        hiphop/
        jazz/
        metal/
        pop/
        reggae/
        rock/

Currently I have the code that extracts the 128 MFCCs and writes them to a csv file at Data/csvs/mfccs.csv commented since it takes quite some time to run and is not necessary to run more than the one time, unless this process is changed to extract more features or more MFCCs by updating the # of mels.

## Training the Models
Training each of the models is relatively the same process due to how the code is structured.
1. You execute the code that iterates over the 128 MFCCs
    - for KNN this process takes a bit longer since it iterates over the odd values from 1 to 128 as well to find the best K (this takes 10-20 minutes)
    - Training the 128 Neural Nets takes anywhere from 10 to 30 minutes depending on computer resources
2. After finding the best # of MFCCs you can run just that version of the model to get the accuracy, confusion matrix, class report, and a list of which songs were misclassified and what they were misclassified as.  This section for each model will also graph the accuracy plot.  For KNN it will display the plot of the best accuracy for each K as well.

# Final Analysis
This section combines the accuracy plots into one final graph.
There is also a section of the code that looks at each misclassified song and tallies the number of times it was misclassified, which would allow for easier analysis of possible misclassified samples or distortions for future work.