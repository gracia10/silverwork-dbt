# silverwork-dbt
DBT를 이용한 ELT 파이프라인 모듈  [[프로젝트 전체보기]](https://github.com/SilverWork)
<br/>

## 1.DBT 프로세스
![그림2](https://github.com/DW-BI-Project/silverwork-airflow/assets/68600766/bb788021-73f2-45f5-a934-76aa30151046)
    - DBT를 이용해 DW의 raw 데이터를 검증하고 분석에 적합한 데이터로 가공  
    - DBT 이미지를 생성하여 Airflow를 통해 스케줄링  
<br/>


## 2. DBT 배포 프로세스 구현
![그림3](https://github.com/DW-BI-Project/silverwork-airflow/assets/68600766/03af6947-a701-4ebb-bb8f-5d77a349a1c7)
    - Airflow 와 코드베이스를 분리하기 위해 DBT 프로젝트를 별로도 생성  
    - develop, main 브랜치의 PR 이벤트를 기준으로 dev, stage 환경에서 모델 검증을 수행할 수 있도록 CI 구조 구성  
    - main 브랜치에 push 이벤트가 발생하면 도커이미지를 생성하고 Airflow DAG를 트리거  
