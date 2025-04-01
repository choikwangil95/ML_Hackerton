# 부동산 허위매물 분류 해커톤: 가짜를 색출하라!
---

<img src="https://velog.velcdn.com/images/choikwangil/post/4bd718b8-db84-4f98-9a68-932984c7d444/image.png" width="600px"/>

부동산 매물관련 정보가 포함된 데이터를 활용하여 허위매물을 분류하는 AI 알고리즘을 개발

- [데이콘](https://dacon.io/competitions/official/236439/overview/description)
- [리더보드 (109등](https://dacon.io/competitions/official/236439/leaderboard)

## 제공 데이터 

|ID| 매물확인방식 | 보증금        | 월세   | 전용면적 | 해당층 | ... | 중개사무소  | 게재일     | 허위매물여부 |
|--|:------------|-------------:|------:|--------:|------:|:---------:|:---------|:--------:|:---------:|
|1| 현장확인    | 402500000.0  | 470000 |   NaN   |   NaN |...| t93Nt6I2I0 | 2024-10-09 | 0 |
|2| 현장확인    | 170500000.0  | 200000 |   NaN   |   3   |...| q39iV5J4E6 | 2024-12-26 | 0 |
|3| 전화확인    | 114000000.0  | 380000 |   NaN   |   2   |...| b03oE4G3F6 | 2024-11-28 | 0 |
|4| 현장확인    | 163500000.0  |  30000 |  36.3   |   3   |...| G52Iz8V2B9 | 2024-11-26 | 0 |
|5| 현장확인    | 346000000.0  | 530000 |   NaN   |   3   |...| N45gM0M7R0 | 2024-06-25 | 1 |
|...|...|...|...|...|...|...|...|...|...|

![image](https://github.com/user-attachments/assets/95dbfecf-e870-4c39-8cb1-4c06563adb83)


## 결과
### ROC-AUC
![image](https://github.com/user-attachments/assets/5a71a2ae-a0d5-46e8-aaff-b7bd06da97c2)

- Threshold 0~1에 따른 결과값
- 허위매물분류는 FPR이 중요하므로 Threshold를 높이는 선택

### Confusion Matrix
![image](https://github.com/user-attachments/assets/917b785a-dbe0-415f-90af-3cfe0a574a12)

- Threshold = 0.5일때의 결과값


| Class        | Precision | Recall | F1-score | Support |
|--------------|-----------|--------|----------|---------|
| 0 (정상 매물) | 0.98      | 0.98   | 0.98     | 2154    |
| 1 (허위 매물) | 0.84      | 0.82   | 0.83     | 298     |
|              |           |        |          |         |
| Accuracy     |           |        | 0.96     | 2452    |
| Macro Avg    | 0.91      | 0.90   | 0.90     | 2452    |
| Weighted Avg | 0.96      | 0.96   | 0.96     | 2452    |
