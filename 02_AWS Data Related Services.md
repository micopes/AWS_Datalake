# AWS Data Related Service
- 데이터 레이크 관련 서비스
  - Amazon S3
  - Amazon Glue
- 데이터 이동 관련 서비스
  - Amazon Kinesis
  - Amazon API Gateway
- 데이터 처리 관련 서비스
  - Amazon EMR
  - Amazon Lambda
- 데이터 분석 관련 서비스
  - Amazon Athena
  - Amazon Redshift
  - Amazon ElasticSearch
  - Amazon Kibana (시각화 도구)

## 도움되는 관점
- AWS 의 여러 모듈로 Data Lake를 구성.
- Data Lake를 **여러 부분**으로 나눠서 생각할 필요가 있다.
  - `Store and Catagoring`
  - `Data movement`
  - `Analytic and Processing`

### DB
- 불가능(확장성 문제)

## Amazon S3 
- **`Storage Layer`**
- 형식에 구애받지 않는다.
- 유형에 따라 별도로 저장되어서는 안된다. 모든 형식이 같은 공간에 존재해야 한다.(중앙 집중식)
  - S3에는 모든 유형의 콘텐츠를 저장할 수 있는 **버킷** 개념이 있다.
- 스케일링을 설정할 필요가 없다.(확장에 관한 얘기)
- 내구성이 뛰어나다.
- 액세스 빈도에 따라 Tier를 설정할 수 있다.(비용 문제 고려 가능)

## Amazon Glue

#### 기존 방식

- large amount of raw assets
  - 무엇인지 확신 X
  - 어떤 데이터가 존재?
  - 데이터가 시간이 지남에 따라 변환된다.
> 적절하게 관리될 필요가 있는데 이때 `AWS Glue`가 유용하다.

#### AWS Glue
- Serverless
- Schema를 수동으로 생성하고 정의할 필요가 없다. (시간의 경과에 따라 변경, 삭제를 Track)
- Table 정의를 추가하면 ETL 작업에 쉽고 유용하게 사용 가능
- `AWS Glue Data Catalog`가 기존 `Apache Hive Metastore`와 동일한 방식으로 **`메타데이터를 관리`**할 수 있다.

##### AWS Glue Jobs   
- AWS Glue에서 ETL 작업을 수행하는 비즈니스 로직

## Amazon Kinesis

### 종류
- `Amazon Kinesis Video Streams`
- `Amazon Kinesis Data Streams`

![image](https://user-images.githubusercontent.com/43158502/138684346-57d171d4-a032-40d6-8ef1-170e7503e819.png)

- `Amazon Kinesis Data Firehose`

![image](https://user-images.githubusercontent.com/43158502/138684377-92c52b2c-68a2-448d-b350-05d182331c86.png)

## 특징

![image](https://user-images.githubusercontent.com/43158502/138684319-b9b54f35-b03d-43a4-a8ad-4f3cf8782c9f.png)

- 데이터 실시간 수집/캡쳐 : `Kinesis Data Streams`
- 데이터 실시간 처리/분석 툴로 로드 및 전송 : `Kinesis Datata Firehose

> [참고] https://jellybean.tistory.com/1

## Amazon API Gateway
- 대규모 보안 API를 쉽게 생성/게시/유지 관리 할 수 있는 완전 관리형 서비스
- API Gateway는 트래픽 관리, COR 지원, 권한 부여 및 액세스 제어, 조절, 모니터링, API 버전 관리 등을 포함하여 최대 수십만 건의 동시 API 호출을 수락하고 처리 등 관련 작업 수행

> API : backend service/application의 front door

## Amazon EMR

- Hadoop이나 Spark와 같은 빅데이터 프레임워크 실행을 간소화하여 방대한 양의 데이터를 처리하고 분석하는 관리형 클러스터 플랫폼
- computing, storage를 분리
- 대량의 데이터를 변환하고 이동할 수 있다.

## AWS Lambda

- `Serverless compute service`, 서버를 프로비저닝하거나 관리하지 않고도 코드를 실행할 수 있는 컴퓨팅 서비스
- `on demand` based on triggers (kinesis data stream이 trigger가 될 수 있다.)

## Amazon Athena

- Serverless
- 움직이거나 DB에 Load할 필요 없이 `S3`에서 직접 데이터를 쿼리할 수 있으며, 실행할 수 있는 Query(대화형 쿼리 서비스)

## Amazon Redshift

- S3와 통합 가능
- 데이터 웨어하우징 서비스(페타바이트 규모(배치)의 정형 데이터에 대해 고성능 쿼리를 간단하고 비용 효율적으로 실행할 수 있다.)
- 클러스터를 실행하여 실행할 수 있다.

## Amazon Elasticsearch
- 오픈 소스
- **search/analytics engine for all types of data**
- 일반적으로 로그 분석 시 사용된다.

## Amazon Kibana
- 시각화

## AWS Lake Formation
- 데이터 레이크를 구축하는데 도움을 주는 서비스

![image](https://user-images.githubusercontent.com/43158502/138705247-47278b14-58a1-4870-b743-93fa1949f92c.png)
