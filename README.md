# HMS-Brain-Activity-Classification

# Getting Started
To replicate our results, first download the data from the Harvard Medical School Brain Activity Classification challenge on Kaggle: https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/data (scroll down and hit download all at the bottom right). After downloading the dataset, extract the files and enter this directory. 

Now run `git --clone https://github.com/BrennanLagasse/HMS-Brain-Activity-Classification.git` to copy the full code directory (For academic integrity reasons this will remain private until the deadline, please contact me at brennan.lagasse@yale.edu if there are any issues with access). This will also be submitted on Gradescope.

In this project, we analyze a variety of techniques of varying degrees of complexity to discover what model can best differentiate between neural disorders. The results of this experimentation are described below with the files that can be run to achieve our results.

As discussed below, some less complex models are incapable of capturing some of the important features of the eeg data and there are some natural approaches for converting this data into a format that has a better change of linear separability in signal processing with algorithms like a Fourier transform. To recreate the transformed data sets we reference in our analysis, use the `generate_transformed_dataset.ipynb` file and input the desired parameters for the outputted dataset in the first code block.


# Motivation
The EEG is a diagnostic tool commonly used by medical professionals to reliably identify and diagnose neurological conditions and harmful neurological activity, such as seizures. EEGs monitor electrical activity of the brain as a function of time through electrodes positioned on the scalp. Currently, the prevailing method for interpretation of EEG data is manual reading by professionals, a process which is time consuming and error-prone, delaying diagnoses and potentially endangering patient health outcomes. In this project, we aim to create a model which can consistently and accurately interpret and classify EEG data related to six common neurological conditions.

# Approach

# Data

# Results

Analysis of HMS data: https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/overview

The dataset is not included in this repo and can be downloaded separately. If this repository is added within the folder containing the data file paths will work as intended. Otherwise, make sure to change the paths for the data for the code to work correctly.

Reformatted data for small sample sizes is included in the github, but the full converted data is well over the file size requirement for GitHub. One workaround is just generating random samples from this larger dataset, which will be uploaded later.