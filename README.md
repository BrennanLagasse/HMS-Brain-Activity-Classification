# HMS-Brain-Activity-Classification

# Getting Started
To replicate our results, follow the following steps:

1. Download the data from the Harvard Medical School Brain Activity Classification challenge on Kaggle: https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/data (scroll down and hit download all at the bottom right). The data is associated with a competition, so you will likely need a Kaggle account and need to agree to the terms of competition. The dataset is also large, so downloading it may take close to an hour. If there are any difficulties accessing the data, contact brennan.lagasse@yale.edu. Additionally, some small samples from the dataset have been provided in the event of difficulties.

2. Extract the folder downloaded from Kaggle if applicable and enter the directory.

3. Run `git --clone https://github.com/BrennanLagasse/HMS-Brain-Activity-Classification.git` to copy the full code directory (For academic integrity reasons this will remain private until the deadline, please contact brennan.lagasse@yale.edu if there are any issues with access). This will also be submitted on Gradescope.

4. Our best results were on model **TBD** and the instructions for how to create this model and replicate our results can be fount in **TBD**

5. The rest of the results are summarized below, and there are details for how to run these files in the associated markdown files. Some of these models require preprocessing with signal processing algorithms. Details will be provided in the associated files, and `generate_transformed_dataset.ipynb` can be used to produce these datasets. Keep in mind this may be a time consuming process for large datasets.

# Motivation
The EEG is a diagnostic tool commonly used by medical professionals to reliably identify and diagnose neurological conditions and harmful neurological activity, such as seizures. EEGs monitor electrical activity of the brain as a function of time through electrodes positioned on the scalp. Currently, the prevailing method for interpretation of EEG data is manual reading by professionals, a process which is time consuming and error-prone, delaying diagnoses and potentially endangering patient health outcomes. In this project, we aim to create a model which can consistently and accurately interpret and classify EEG data related to six common neurological conditions.

# Approach
The procedure used by experts to identify EEG data involves reviewing the electrical activity level in the brain across twenty sensors in different locations to identify the location and pattern of the activity. Location specifies where in the brain the activity occurs, and it is of particular interest if activity in different hemispheres of the brain or within one hemisphere differs significantly. Pattern of the activity describes the relative shape of the waves and whether there are gaps in between them. It is vital that our model is capable of identifying these features. One consequence of this is that our model needs to be able to identify amplitude and relative phases of the waves of different sensors but should not be impacted by a global phase shift (i.e. if recording had started slightly earlier or later). As a result, a linear model trained on the raw EEG data would be incapable of identifying any meaningful patterns within the data since it is limited in its ability to capture phenomena such as frequencies of signals. One way around this problem is to preprocess the data in a way that captures desirable features such as the relative phase and amplitude of the component waves. This can be achieved with multiple signal processing algorithms including the Fourier transform. For this project we will experiment with different signal processing techniques to generate the training data along with models of varying complexity including logistic regression, k-neighbors, and neural networks to find a model that has high accuracy and generalizability. We expect that simpler models with basic signal processing techniques may not be able to capture the full complexity of the model but more complex models that try to learn a more complex relationship between the data and classes may be prone to overfitting. We will experiment with regularization techniques and data processing methods to find an ideal model with high accuracy and generalizability.

# Data
The data for this project is sourced from the Harmful Brain Activity Classification competition on Kaggle. The data was provided by Harvard Medical School and labeled by the Critical Care EEG Monitoring Research Consortium. The data consists of fifty second long EEG samples and ten minute long spectrograms from which ten second subintervals are labeled by experts based on what neural activity is exhibited during that time period. There are 106,800 such labeled intervals. This dataset has the advantage of high label credibility since labels are given by medical experts and a large number of samples which is important for regularization for developing an accurate and generalizable model. One issue with the dataset, however, is that the ground truth labels are determined by a simple majority of expert votes, and many samples exhibit low expert consensus. For our project, we plan to first stratify the dataset such that we will train, validate, and test our model using data with high expert agreement. By stratifying the data in this way, we hope to reduce the noise of the ground truth that may impede the ability of our model to correctly classify various types of brain activity, and therefore increase its accuracy.

# Results

Analysis of HMS data: https://www.kaggle.com/competitions/hms-harmful-brain-activity-classification/overview

The dataset is not included in this repo and can be downloaded separately. If this repository is added within the folder containing the data file paths will work as intended. Otherwise, make sure to change the paths for the data for the code to work correctly.

Reformatted data for small sample sizes is included in the github, but the full converted data is well over the file size requirement for GitHub. One workaround is just generating random samples from this larger dataset, which will be uploaded later.

*Note that this document is an extension of the initial proposal for this project and includes some of the same information for context* 