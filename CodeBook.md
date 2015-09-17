# Subject and Activity Statistical Measure Data Set Derived from the Human Activity Recognition Using Smartphones Data Set Codebook

The tidy dataset in [tidydata.txt](./tidydata.txt) can be retrieved within R 
with the following command:

    tidydata <- read.table(tidydata.txt, header = TRUE)

## Overview

The specification of formatting and content of the data contained in the 
simplified dataset and final tidy dataset is documented herein.

The Human Activity Recognition Using Smartphones Data Set used to produce the 
tidy dataset has been provided by the University of California at Irvine,  
Center for Machine Learning and Intelligent Systems. The source data is 
available from the [Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones). 
For convenience a copy of this publicly-accessible data (uci\_data.zip) is 
contained within the GitHub repository along with the R script 
(./run_analysis.R) used to generate the tidy dataset (tidydata.txt) as well as 
documentation supporting the production of the tidy data 
(./README.md and ./CodeBook.md).

[README.md](./README.md) provides a step-by-step walk-through of the data 
cleansing and transformation procedure undertaken to create 
[tidydata.txt](./tidydata.txt). [CodeBook.md](./CodeBook.md) describes the 
variables, the data, and any transformations performed in furthernace of data 
tidying in anticipation of subsequent data analysis.

The raw data archive which forms the basis for the derived datasets was 
downloaded on September 9, 2015 from the University of California at Irvine,  
Center for Machine Learning and Intelligent Systems repository [archive](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip). 

Briefly the original training and testing datasets contain experimental 
observations comprised of data collected using the following parameters:

* a group of 30 participants between 19-48 years of age. 
* each participant performed 6 activities (laying, sitting, standing, walking,
walking downstairs, and walking upstairs) while wearing a Samsung Galaxy S II 
smartphone.
* the smartphone's embedded accelerometer and gyroscope permitted capture of 
tri-axial linear acceleration and tri-axial angular velocity at a constant rate
of 50Hz. 
* the experimential data was randomly partitioned by the data provider into two 
sets (approximately 70% training, 30% testing). 

## Data Dictionary

The variables in the [tidy dataset](./tidydata.txt) are a subset of those 
described in features_info.txt. The tidy dataset is a combination of the 
original testing and training data containing only statistical measures of mean 
or standard deviation for each of six activities and thirty participants. The 
final dataset has been formatted in accordance with tidy data best practises as 
published by Hadley Wickham, including a header row identifying the contents of 
each column.

The first-cut dataset consists of an observation for each subject and activity 
performed with associated statistical measures of mean and standard deviation 
for those activities as collected by the Samsung Galaxy S II.  There are 66 
unique variables (mean and standard deviation) as described in the section 
*Tidy Dataset Variables*.

The final [tidy dataset](./tidydata.txt) contains rows of space-separated values
for each subject-activity pair (subject S performing activity A) with the 
computed mean of each of the collected measurement means and standard 
deviations.
 
### Variable Name Format

Variables follow this standardised naming convention with their associated 
definition.

    Participant:
        subject  - experiment participant identifier;
                   character: 1 - 30
        activity - activity being performed;
                   character: laying, sitting, standing, walking, 
                   walking downstairs, walking upstairs 

    Measurement Variable Names:
        <Domain><AccelerationType><MeasureName>[<Axis>]<StatisticType>
    
    Domain:
        t - time variable
        f - Fast Fourier Transform variable
    
    Acceleration Type:
        body    - measurement acceleration separated from gravity
        gravity - separation of the gravity acceleration signal
    
    Measure Name:
        Unique measures for each of the 66 measures normalized between [-1, 1], 
        therefore these measures have no units, and without modification of the 
        original data.
    
    Axis (optional):
        xaxis - X-axis measurement
        yaxis - Y-axis measurement
        zaxis - Z-axis measurement
    
    Statistic Type:
        std  - standard deviation variable
        mean - mean value variable


### Tidy Dataset Variables 

```
Column | Variable Name                     | Definition
-------|-----------------------------------|-------------------------------------------------------
 [1]    subject                             identifies the volunteer participant
                                            (non-personally identifiable 
                                            designator for anonymity)                        
 
 [2]    activity                            identifies the activity performed by
                                            the subject (walking, walking 
                                            upstairs, walking downstairs,
                                            sitting, standing, or lying)
 
 [3]    tbodyaccelerometerxaxismean         mean of the body acceleration on the
                                            x-axis         
 
 [4]    tbodyaccelerometeryaxismean         mean of the body acceleration on the
                                            y-axis        
 
 [5]    tbodyaccelerometerzaxismean         mean of the body acceleration on the
                                            z-axis        
 
 [6]    tbodyaccelerometerxaxisstd          standard deviation of the body 
                                            acceleration on the x-axis          
 
 [7]    tbodyaccelerometeryaxisstd          standard deviation of the body 
                                            acceleration on the y-axis          
 
 [8]    tbodyaccelerometerzaxisstd          standard deviation of the body 
                                            acceleration on the z-axis
 
 [9]    tgravityaccelerometerxaxismean      mean of the gravity acceleration on 
                                            the x-axis     

[10]    tgravityaccelerometeryaxismean      mean of the gravity acceleration on 
                                            the y-axis

[11]    tgravityaccelerometerzaxismean      mean of the gravity acceleration on 
                                            the z-axis

[12]    tgravityaccelerometerxaxisstd       standard deviation of the gravity 
                                            acceleration on the x-axis

[13]    tgravityaccelerometeryaxisstd       standard deviation of the gravity 
                                            acceleration on the y-axis       

[14]    tgravityaccelerometerzaxisstd       standard deviation of the gravity 
                                            acceleration on the z-axis      

[15]    tbodyaccelerometerjerkxaxismean     mean of the body acceleration on the
                                            x-axis, derived in time to obtain 
                                            Jerk signals

[16]    tbodyaccelerometerjerkyaxismean     mean of the body acceleration on the
                                            y-axis, derived in time to obtain 
                                            Jerk signals

[17]    tbodyaccelerometerjerkzaxismean     mean of the body acceleration on the
                                            z-axis, derived in time to obtain 
                                            Jerk signals

[18]    tbodyaccelerometerjerkxaxisstd      standard deviation of the body 
                                            acceleration on the x-axis, derived 
                                            in time to obtain Jerk signals      

[19]    tbodyaccelerometerjerkyaxisstd      standard deviation of the body 
                                            acceleration on the y-axis, derived 
                                            in time to obtain Jerk signals     

[20]    tbodyaccelerometerjerkzaxisstd      standard deviation of the body 
                                            acceleration on the z-axis, derived 
                                            in time to obtain Jerk signals      

[21]    tbodygyroscopexaxismean             mean of the body angular velocity on
                                            the x-axis             

[22]    tbodygyroscopeyaxismean             mean of the body angular velocity on
                                            the y-axis

[23]    tbodygyroscopezaxismean             mean of the body angular velocity on
                                            the z-axis         

[24]    tbodygyroscopexaxisstd              standard deviation of the body 
                                            angular velocity on the x-axis

[25]    tbodygyroscopeyaxisstd              standard deviation of the body 
                                            angular velocity on the y-axis

[26]    tbodygyroscopezaxisstd              standard deviation of the body 
                                            angular velocity on the z-axis

[27]    tbodygyroscopejerkxaxismean         mean of the body angular velocity on
                                            the x-axis, derived in time to 
                                            obtain Jerk signals

[28]    tbodygyroscopejerkyaxismean         mean of the body angular velocity on
                                            the y-axis, derived in time to 
                                            obtain Jerk signals

[29]    tbodygyroscopejerkzaxismean         mean of the body angular velocity on
                                            the z-axis, derived in time to 
                                            obtain Jerk signals

[30]    tbodygyroscopejerkzaxisstd          standard deviation of the body 
                                            angular velocity on the z-axis, 
                                            derived in time to obtain Jerk 
                                            signals          

[31]    tbodygyroscopejerkxaxisstd          standard deviation of the body 
                                            angular velocity on the x-axis, 
                                            derived in time to obtain Jerk 
                                            signals          

[32]    tbodygyroscopejerkyaxisstd          standard deviation of the body 
                                            angular velocity on the y-axis, 
                                            derived in time to obtain Jerk 
                                            signals          

[33]    tbodyaccelerometermagnitudemean     mean of the body acceleration 
                                            magnitude, calculated using the 
                                            Euclidean norm    

[34]    tbodyaccelerometermagnitudestd      standard deviation of the angular 
                                            velocity magnitude      

[35]    tgravityaccelerometermagnitudemean  mean of the gravity acceleration 
                                            magnitude  

[36]    tgravityaccelerometermagnitudestd   standard deviation of the gravity 
                                            acceleration magnitude
                                            
[37]    tbodyaccelerometerjerkmagnitudemean mean of the body acceleration 
                                            magnitude derived in time to obtain 
                                            Jerk signals

[38]    tbodyaccelerometerjerkmagnitudestd  standard deviation of the body 
                                            acceleration magnitude derived in 
                                            time to obtain Jerk signals  

[39]    tbodygyroscopemagnitudemean         mean of the angular velocity 
                                            magnitude         

[40]    tbodygyroscopemagnitudestd          standard deviation of the angular 
                                            velocity magnitude          

[41]    tbodygyroscopejerkmagnitudemean     mean of the angular velocity 
                                            magnitude derived in time to obtain 
                                            Jerk signals    

[42]    tbodygyroscopejerkmagnitudestd      standard deviation of the angular 
                                            velocity magnitude derived in time 
                                            to obtain Jerk signals      

[43]    fbodyaccelerometerxaxismean         mean of the body acceleration on the
                                            x-axis, with a Fast Fourier 
                                            Transform (FFT) applied         

[44]    fbodyaccelerometeryaxismean         mean of the body acceleration on the
                                            y-axis, with a Fast Fourier 
                                            Transform (FFT) applied

[45]    fbodyaccelerometerzaxismean         mean of the body acceleration on the
                                            z-axis, with a Fast Fourier 
                                            Transform (FFT) applied

[46]    fbodyaccelerometerzaxisstd          standard deviation of the body 
                                            acceleration on the z-axis, with a 
                                            Fast Fourier Transform (FFT) applied         

[47]    fbodyaccelerometerxaxisstd          standard deviation of the body 
                                            acceleration on the x-axis, with a 
                                            Fast Fourier Transform (FFT) applied          

[48]    fbodyaccelerometeryaxisstd          standard deviation of the body 
                                            acceleration on the y-axis, with a 
                                            Fast Fourier Transform (FFT) applied          

[49]    fbodyaccelerometerjerkxaxismean     mean of the body acceleration on the
                                            x-axis, derived in time to obtain 
                                            Jerk signals, with a Fast Fourier 
                                            Transform (FFT) applied     
[50]    fbodyaccelerometerjerkyaxismean     mean of the body acceleration on the
                                            y-axis, derived in time to obtain 
                                            Jerk signals, with a Fast Fourier 
                                            Transform (FFT) applied

[51]    fbodyaccelerometerjerkzaxismean     mean of the body acceleration on the
                                            z-axis, derived in time to obtain 
                                            Jerk signals, with a Fast Fourier 
                                            Transform (FFT) applied

[52]    fbodyaccelerometerjerkxaxisstd      standard deviation of the body 
                                            acceleration on the x-axis, with a 
                                            Fast Fourier Transform (FFT) applied      

[53]    fbodyaccelerometerjerkyaxisstd      standard deviation of the body 
                                            acceleration on the y-axis, with a 
                                            Fast Fourier Transform (FFT) applied      

[54]    fbodyaccelerometerjerkzaxisstd      standard deviation of the body 
                                            acceleration on  the z-axis, with a 
                                            Fast Fourier Transform (FFT) applied

[55]    fbodygyroscopexaxismean             mean of the body angular velocity on
                                            the x-axis, with a Fast Fourier 
                                            Transform (FFT) applied

[56]    fbodygyroscopeyaxismean             mean of the body angular velocity on
                                            the y-axis, with a Fast Fourier 
                                            Transform (FFT) applied

[57]    fbodygyroscopezaxismean             mean of the body angular velocity on
                                            the z-axis, with a Fast Fourier 
                                            Transform (FFT) applied

[58]    fbodygyroscopexaxisstd              standard deviation of the body 
                                            angular velocity on the x-axis, with
                                            a Fast Fourier Transform (FFT) applied      

[59]    fbodygyroscopeyaxisstd              standard deviation of the body 
                                            angular velocity on the y-axis, with
                                            a Fast Fourier Transform (FFT) applied

[60]    fbodygyroscopezaxisstd              standard deviation of the body 
                                            angular velocity on the z-axis, with
                                            a Fast Fourier Transform (FFT) applied

[61]    fbodyaccelerometermagnitudemean     mean of the body acceleration 
                                            magnitude, with a Fast Fourier 
                                            Transform (FFT) applied     

[62]    fbodyaccelerometermagnitudestd      standard deviation of the body 
                                            acceleration magnitude, with a Fast 
                                            Fourier Transform (FFT) applied      

[63]    fbodyaccelerometerjerkmagnitudemean mean of the body acceleration 
                                            magnitude derived in time to obtain 
                                            Jerk signals, with a Fast Fourier 
                                            Transform (FFT) applied 

[64]    fbodyaccelerometerjerkmagnitudestd  standard deviation of the body 
                                            acceleration magnitude derived in 
                                            time to obtain Jerk signals, with a 
                                            Fast Fourier Transform (FFT) applied 

[65]    fbodygyroscopemagnitudemean         mean of the angular velocity 
                                            magnitude, with a Fast Fourier 
                                            Transform (FFT) applied         

[66]    fbodygyroscopemagnitudestd          standard deviation of the angular 
                                            velocity magnitude, with a Fast 
                                            Fourier Transform (FFT) applied          

[67]    fbodygyroscopejerkmagnitudemean     mean of the angular velocity 
                                            magnitude, with a Fast Fourier 
                                            Transform (FFT) applied         

[68]    fbodygyroscopejerkmagnitudestd      standard deviation of the angular 
                                            velocity magnitude, with a Fast 
                                            Fourier Transform (FFT) applied
```

## Bibliography

Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. 
Reyes-Ortiz. A Public Domain Dataset for Human Activity Recognition Using 
Smartphones. 21th European Symposium on Artificial Neural Networks, 
Computational Intelligence and Machine Learning, ESANN 2013. Bruges, Belgium
24-26 April 2013.

Human Activity Recognition Using Smartphones Data Set. University of California 
at Irvine,  Center for Machine Learning and Intelligent Systems, 
[Machine Learning Repository](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones). 
Retrieved 09 September 2015.
