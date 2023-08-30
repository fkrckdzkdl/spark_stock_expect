# spark_stock_expect - ELK Stack
현재 날짜를 기준으로 1년 간의 주가를 예측 해보는 프로그램

1. yfinance 라이브러리를 통해 원하는 주식의 최근 1년치 데이터를 csv 형식으로 받아온다.
   ![image](https://github.com/fkrckdzkdl/spark_stock_expect/assets/91944913/726e9d25-9acb-4da0-ba58-9e1b29aa6cf6)

2. 현재 날짜를 기준으로 다음 1년치 기간의 데이터 프레임을 생성한다.
   ![image](https://github.com/fkrckdzkdl/spark_stock_expect/assets/91944913/59a92d7a-9a71-4f04-8d32-d73cc38d1494)
3. 기간 만큼의 주가 예측 값을 예측
  - 주가예측값 : 파동의 법칙에 따른 지난 1년치값의 대칭값을 평균값과 비교하는 방식으로 예측
   ![image](https://github.com/fkrckdzkdl/spark_stock_expect/assets/91944913/09204bd9-0945-4de3-8ead-5aa8f0d67fbf)
   ![image](https://github.com/fkrckdzkdl/spark_stock_expect/assets/91944913/75843c2d-3258-410c-8659-5556b9ad297c)

4. logstash를 사용하여 생성한 데이터를 elasticsearch로 input
   
![image](https://github.com/fkrckdzkdl/spark_stock_expect/assets/91944913/a842233a-9164-4761-9006-16dcd1629dc4)

5. kibana를 통해 데이터를 시각화
- 지난 1년 종가 
![image](https://github.com/fkrckdzkdl/spark_stock_expect/assets/91944913/5e26625e-8b0e-4de9-85d1-600043211977)

- 예측값
 ![image](https://github.com/fkrckdzkdl/spark_stock_expect/assets/91944913/eb28661f-120a-436a-b8c2-2018b75c2f82)
