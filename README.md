# [EricssonLG Summer Internship] Log Anomaly Detection 

보안상의 이유로 코드 공개가 불가합니다.

## 1. Overview

- purpose: Designing an AI model to detect potential anomalies in design from logs.
- background: vDU has a working AI model (Cell Setup, ESS Cell Setup, Carrier Setup) <br /> 
  <img width="540" alt="image" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/5761e600-c998-46d3-ab8d-6dcc49655f54">

    

## 2. Result

<img width="558" alt="image" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/172a3928-56b3-4480-8f94-ede87c047d2f">


The following table illustrates the performance of the model. These particular results show that when I used a combination of two models, which were the Long Short Term Memory Model and the Isolation Forest Model, the accuracy of the model was 99, the precision was 78, the recall was 100, and the f1-score was 88.

## 3. Procedure

<img width="558" alt="image" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/b443f4d3-363f-41be-b650-8b751674d539">


1. Long Short Term Memory Model <br /> 
    LSTM model is suitable for ordered data, such as time series data or sentences.
    LSTM model use MSE values to express how different the next predictive message is from the actual message. 
    
2. Isolation Forest Model <br /> 
    Model training is possible with only normal data.
    Isolation Forest Model classifies as normal if prediction is 1 and abnormal if prediction is -1. 
    

## 4. Model Parameter Control

<img width="574" alt="image" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/c35457af-1d9a-4020-8a5e-ff351653826c">


- LSTM Model
    - mse_test: average of the squared values of the error between the predicted log message by and the actual log message.
- Isolation Forest Model
    - contamination: percentage of outliers expected in the overall data.
    - c_esimators: number of iTree
    

Why I choose case 2? 

- Isolation forest model leaves only a proportion of contamination in the entire dataset (high risk of anomaly being filtered).
- Considering the overall performance (ex. Precision, Recall, F1-Score) of both cases, the optimal model for implementing a log anomaly detection feature consists of utilizing the LSTM model and Isolation Forest model in the particular order.

## 5. Use Case

- Detect potential product flaws before release.
- More work needs to be done for analyzing LTTNG logs.

## Presentation in Seoul Technical Stand-up, EricssonLG

<img width="1512" alt="스크린샷 2023-09-27 오후 1 03 04" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/476eccc3-51dc-42a6-bc9e-201e72be4867">
<img width="1512" alt="스크린샷 2023-09-27 오후 1 03 41" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/ae635dde-0a8a-48c5-9a2e-41e22fe3baaf">
Playing the Demo code 

