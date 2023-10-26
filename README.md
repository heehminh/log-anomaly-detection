# [EricssonLG Summer Internship] Log Anomaly Detection 

보안상의 이유로 코드 공개가 불가합니다.

## 1. Overview

- purpose: Designing an AI model to detect potential anomalies in design from logs.
- background: vDU has a working AI model (Cell Setup, ESS Cell Setup, Carrier Setup) <br /> 

  <img width="437" alt="Untitled (3)" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/51816f4f-29e7-4ffc-b32c-6c7d1d6ef672">
  <img width="438" alt="Untitled (4)" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/35a04107-2e2a-4099-8df0-8c550a54c875">

    

## 2. Result

<img width="567" alt="Untitled (5)" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/1991ad8d-4d9d-493e-b0d6-745e4c905500">


The following table illustrates the performance of the model. These particular results show that when I used a combination of two models, which were the Long Short Term Memory Model and the Isolation Forest Model, the accuracy of the model was 99, the precision was 78, the recall was 100, and the f1-score was 88.

## 3. Procedure

<img width="720" alt="Untitled (6)" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/468a0442-1a0d-43e9-bd15-c03dca6704b5">


1. Long Short Term Memory Model <br /> 
    LSTM model is suitable for ordered data, such as time series data or sentences.
    LSTM model use MSE values to express how different the next predictive message is from the actual message. 
    
2. Isolation Forest Model <br /> 
    Model training is possible with only normal data.
    Isolation Forest Model classifies as normal if prediction is 1 and abnormal if prediction is -1. 
    

## 4. Model Parameter Control

<img width="531" alt="스크린샷 2023-10-26 오후 12 49 10" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/d938d4f1-cc1d-4a93-ab0d-7a1760552d6f">

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
<img width="1512" alt="스크린샷 2023-10-26 오후 12 45 25" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/247ea248-aaa3-4f01-b516-5186589fc7ad">
Playing the Demo code 

<img width="1512" alt="스크린샷 2023-10-26 오후 12 47 56" src="https://github.com/heehminh/log-anomaly-detection/assets/76530562/faff1f3a-0f22-4f3d-b82b-ad69667fbc51">



