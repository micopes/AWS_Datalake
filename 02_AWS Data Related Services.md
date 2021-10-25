# AWS Data Related Service

## 도움되는 관점
- AWS 의 여러 모듈로 Data Lake를 구성.
- Data Lake를 **여러 부분**으로 나눠서 생각할 필요가 있다.
  - `Store and Catagoring`
  - `Data movement`
  - `Analytic and Processing`

### DB
- 불가능(확장성 문제)

## Amazon S3 
- `Storage Layer`
- 형식에 구애받지 않는다.
- 유형에 따라 별도로 저장되어서는 안된다. 모든 형식이 같은 공간에 존재해야 한다.(중앙 집중식)
  - S3에는 모든 유형의 콘텐츠를 저장할 수 있는 **버킷** 개념이 있다.
- 스케일링을 설정할 필요가 없다.(확장에 관한 얘기)
- 내구성이 뛰어나다.
- 액세스 빈도에 따라 Tier를 설정할 수 있다.(비용 문제 고려 가능)

## AWS Glue

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
- `AWS Glue Data Catalog`가 기존 `Apache Hive Metastore`와 동일한 방식으로 메타데이터를 관리할 수 있다.

