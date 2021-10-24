# AWS Data Related Service

## 도움되는 관점
- AWS 의 여러 모듈로 Data Lake를 구성.
- Data Lake를 **여러 부분**으로 나눠서 생각할 필요가 있다.
  - `Store and Catagoring`
  - `Data movement`
  - `Analytic and Processing`

### DB
- 불가능(확장성 문제)

### Amazon S3 
- `Storage Layer`
- 형식에 구애받지 않는다.
- 유형에 따라 별도로 저장되어서는 안된다. 모든 형식이 같은 공간에 존재해야 한다.(중앙 집중식)
  - S3에는 모든 유형의 콘텐츠를 저장할 수 있는 **버킷** 개념이 있다.
- 스케일링을 설정할 필요가 없다.(확장에 관한 얘기)
- 내구성이 뛰어나다.
- 액세스 빈도에 따라 Tier를 설정할 수 있다.(비용 문제 고려 가능)
