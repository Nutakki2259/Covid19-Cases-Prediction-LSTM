# Covid19-Future-Confirmed-Cases-Predicction-Through-LSTM
## In this project the estimation of increase in confirm cases cases in future days using LSTM can be predicted.
The dataset of Covid19 confirmed cases from January to July 2020 are taken into consideration from the site https://data.humdata.org/dataset/novel-coronavirus-2019-ncov-cases available on daily update basis. An approximate measurement of increase in future confirmed covid cases globally are predicted using LSTM.

### 1. Load the Dataset
In the link provided above contains a csv file of 'time_series_covid19_confirmed_global.csv' of all countries in particular to daily update from 22 Jan 2020 to till now. Load this dataset after downloading to upto date from the website.

### 2. Preprocessing Dataset
As it can be seen that the data visulaised will have first four columns in data.head() are not needed as represents state, country, Latitude and Longitude which are unnecessary for our data analysis and are removed from dataset for our flexibility.

In this project as estimating the increment = present data-previous data. So, the sum up of all cases as it is considers globally and increment in data can be vsualised as 'increment cases' = daily_data[1]-daily_data[0]

### 3. Split the data into sequences
In the forward of the project, it is need to split the data as input sequence and output sequence depending on sequence length of the data to be visualised in incremeent in coid cases day by day status.

### 4. Build LSTM Network for Future Prediction
Now its time to build an LSTM network that is required to predict the future estimated increased covid19 cases. Initialise the data layers for the LSTM, sequence length, hidden and feature size. As it is require to reset the state after every epoch of turn to analyse again the data as clear. Get the data of last time step that is required and sent to linear layer to forecast the future.

### 5. Train the Network
Here, comes with training of the data with build 'FutureDataPrediction' LSTM network. 'model.reset_hidden_state()' is used to reset the state to its original position after an epoch has initialised. Then collected the loss from the netwrok predict trained with whole data available of 175 entries.

### 6. Loss Plot
It is the plot between the data trained and loss between actual and predicted output. The spikes in the loss may be due to the irregular of data wih daily increase or decrease of incoming confirmed cases but anyways loss is decreasing.


![Loss vs Epoch](https://github.com/Nutakki2259/Covid19-Future-Estimation-Prediction-of-Confirmed-Cases-Through-LSTM/blob/master/Plots/loss.PNG)

### 7. Predict confirm cases 
In this case the previous cases increase from 22 Jan 2020 to 14 July 2020 can be observed along with the future cases as estimated for a month i.e 15 July 2020 to 13 Aug 2020. Note that, as the data of entries is too small to train the predicted will be purely an approximate number.

### 8. Combination of increment in previous and future confirmed cases.
The estimated increase in future cases can be observed in the plot while data trained with previous cases

![Estimation](https://github.com/Nutakki2259/Covid19-Future-Estimation-Prediction-of-Confirmed-Cases-Through-LSTM/blob/master/Plots/increment.PNG)

### References
[1] https://data.humdata.org/dataset/novel-coronavirus-2019-ncov-cases

[2] https://www.curiousily.com/posts/time-series-forecasting-with-lstm-for-daily-coronavirus-cases/
