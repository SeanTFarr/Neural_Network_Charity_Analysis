<img src=Resources\Images\header.jpg>

## Overview of the analysis: 
This analysis uses machine learning and neural networks on the features presented in a dataset, charity_data.csv to create a binary classifier that is capable of predicting whether applicants will be successful if funded. The target predictive accuracy is 75%

## Results: 

### Data Preprocessing

The was read in to find the target, the features, and anything that may need to be removed.

<img src=Resources\Images\pd.read.jpg>

The Target was the "Yes" or "1" in the "IS_SUCCESSFUL" column

<img src=Resources\Images\target.jpg>

The Features were the data in the "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", and "ASK_AMT" columns.

The "EIN" and "NAME" columns were not beneficial to the analysis, so they were removed.

<img src=Resources\Images\drop.jpg>

### Compiling, Training, and Evaluating the Model

Once the data was cleaned, encoded, and scaled, the first neural network was created. I used two hidden "relu" layers with 80 and 30 neurons respectively and an output layer with the "sigmoid" activation. The "relu" activations were chosen based on prior experience where these worked best with this range of data, nonlinear relationships and with the data being complex, I wanted to start with a larger number of neurons to get better accuracy. The "sigmoid" activation works best on the output because we are trying to produce a probability output.

<img src=Resources\Images\nn.jpg>

This yeilded the following results

<img src=Resources\Images\Charity.jpg>

at 65.5%, I needed to optimize the model 

By adjusting the number of bins in the "APPLICATION_TYPE" and "CLASSIFICATION" columns I was trying to reduce some "noise"

<img src=Resources\Images\app.jpg><img src=Resources\Images\class.jpg>

I also added additional neurons to the model

<img src=Resources\Images\nn1.jpg>

The results were better at 70.4%

<img src=Resources\Images\best_run.jpg>

I thought I would try to use another activation function, so I plugged in the "tanh" function

<img src=Resources\Images\nn2.jpg>

But this did not help...

<img src=Resources\Images\2nd.jpg>

For a 3rd attempt, I went back to the "relu" functions and added an additional layer to try to gain a little more accuracy

<img src=Resources\Images\nn3.jpg>

however it seemed to be getting overfit and the accuracy dropped

<img src=Resources\Images\3rd.jpg>

I did not reach the desired 75% target model performance.

## Summary: 
The overall results of the deep learning model fell short of our target. I am confident though that with further cleaning of the data, I could hit it without using too many layers(more is not always better). 
