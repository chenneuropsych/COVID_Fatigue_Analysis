# COVID_Fatigue_Analysis

Analysis for study "Phyisological Biomarkers of post-COVID fatigue". This study uses Empatica wearable sensors to gather PPG, EDA and accelerometer data from participants with post-COVID fatigue.

## Data Cleaning
Includes two files for cleaning the two kinds of data.
1. **Lab data** includes timestamp, BVP, EDA, TEMP, accelerometer X, Y and Z components, Block number and Fatigue Rating. Block number refers to the section of the computer task that the participant is in. Block 0 refers to the baseline period, and Blocks 1-6 refer to the six blocks of the task. Fatigue ratings are self-reported measures of the participant's mental fatigue while completing the six blocks of the 2-back test.
2. **Remote data** includes timestamp, BVP, EDA, TEMP, and accelerometer X, Y and Z components. TBA will add mindLAMP fatigue ratings.

## Data Preprocessing
Includes files for preprocessing various variables: 
1. Filtering and upsampling
2. Motion artifact reduction of PPG data.
3. Feature extraction
