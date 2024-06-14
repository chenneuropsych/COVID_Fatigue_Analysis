# COVID_Fatigue_Analysis

Analysis for study "Phyisological Biomarkers of post-COVID fatigue". This study uses Empatica wearable sensors to gather PPG, EDA and accelerometer data from participants with post-COVID fatigue.

## Data Cleaning
Includes two files for cleaning the two kinds of data.
1. **Lab data** includes timestamp, BVP, EDA, TEMP, accelerometer X, Y and Z components, Block number and Fatigue Rating. Block number refers to the section of the computer task that the participant is in. Block 0 refers to the baseline period, and Blocks 1-6 refer to the six blocks of the task. Fatigue ratings are self-reported measures of the participant's mental fatigue while completing the six blocks of the 2-back test.
2. **Remote data** includes timestamp, BVP, EDA, TEMP, and accelerometer X, Y and Z components. TBA will add mindLAMP fatigue ratings.
Other files:
1. **test_avro_conversion** is the file used to convert the EmbracePlus raw data (in AVRO format) to csv files that match up with the E4 dataframes we made previously.
2. **Compare_E4_Emp_raw** is the file using the dataframes generated from test_avro_conversion and computing euclidean distance, dynamic time warping, etc.
   
## Data Preprocessing
Includes files for preprocessing.
1. bvp_acc_filtering. This file uses chebyshev II and butterworth filters as well as upsamples the accelerometer data. Run this file before using the padasip code.
2. Padasip_Filtering. This file runs the padasip adaptive filter to account for motion artifacts.
3. factor_analysis. This file is some preliminary factor analysis to determine which PHI (participant health information) is most relevant for predicting fatigue.

## Feature Extraction
1. nk2_feature_extraction. This is an exploratory file to visualize peak detection algorithms and participant data in general.
2. feature_extraction_windows. This is the file that is extracting HRV features from BVP data using neurokit2. It also breaks the data into windows of various sizes and excludes invalid windows(see campanella paper).
3. TsFresh. file to extract the 800 or so TsFresh statistical features, run on Amarel cluster.
4. accuracy_rt. a file to calculate the accuracy and reaction time values by block, 30 second window, and 60 second window.
5. HRV_visualization , file to visualise and find correlation amoing HRV features and fatigue levels.
6. factor analysis, file on code for PHI data analysis, factor analysis and correlation plots .

## Models
Preliminary code for training and testing different models to predict fatigue scores.
1. DecisionTree_30seconds. development of decision tree for 30 second windowed data, as generated from the feature_extraction_windows file.
2. DecisionTree_60seconds. development of decision tree for 60 second windowed data, as generated from the feature_extraction_windows file.
3. Train_Test_Windows_Block. training on window data and testing on block data, also including randm forest model and feature importance calculations. This is the final experiment with these models.

Pipeline: 
![pipeline](https://github.com/chenneuropsych/COVID_Fatigue_Analysis/assets/30849030/bdb23881-219f-4a44-b674-f09505c169c6)

1. bvp_acc_filtering.
2. Padasip_Filtering.
3. feature_extraction_windows.
4. Train_Test_Windows_Block.
