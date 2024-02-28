# COVID_Fatigue_Analysis

Analysis for study "Phyisological Biomarkers of post-COVID fatigue". This study uses Empatica wearable sensors to gather PPG, EDA and accelerometer data from participants with post-COVID fatigue.

## Data Cleaning
Includes two files for cleaning the two kinds of data.
1. **Lab data** includes timestamp, BVP, EDA, TEMP, accelerometer X, Y and Z components, Block number and Fatigue Rating. Block number refers to the section of the computer task that the participant is in. Block 0 refers to the baseline period, and Blocks 1-6 refer to the six blocks of the task. Fatigue ratings are self-reported measures of the participant's mental fatigue while completing the six blocks of the 2-back test.
2. **Remote data** includes timestamp, BVP, EDA, TEMP, and accelerometer X, Y and Z components. TBA will add mindLAMP fatigue ratings.

## Data Preprocessing
Includes files for preprocessing.
1. bvp_acc_filtering. This file uses chebyshev II and butterworth filters as well as upsamples the accelerometer data. Run this file before using the padasip code.
2. Padasip_Filtering. This file runs the padasip adaptive filter to account for motion artifacts. 

## Feature Extraction
Currently still WIP.
1. nk2_feature_extraction. This is an exploratory file to visualize peak detection algorithms and participant data in general.
2. feature_extraction_windows. This is the file that is extracting HRV features from BVP data using neurokit2. It also breaks the data into windows of various sizes and excludes invalid windows.
3. 3. TsFresh. file to extract the 800 or so TsFresh statistical features, run on Amarel cluster.
