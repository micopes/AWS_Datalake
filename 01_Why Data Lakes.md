# Why Data Lakes


## Data Lake

- 형식에 관계없이 원시 데이터를 저장
- 미래에 발생할 일에 대한 답을 제공할 수 있다.

### Data Lake 구성요소
- Ingest and Store
- Catalog and Search
- Process and Serve
  - Computing을 Storage에서 분리하는 것이 좋다. Cloud 서비스를 사용하면서 불필요한 비용을 지불하고 싶지 않다면.
- Protect and Secure

## DB vs Data Lake

### DB
- 처리와 저장이 함께.
- 규모에 대한 유연성이 떨어짐(확장이 어렵다)
- 처리하지 않고 저장하거나, 저장하지 않고 처리한다.

### Data Lake
- 중앙 집중식 저장소
- 정형 및 비정형 데이터를 안전하게 저장
- 확장에 제한이 없다.

![image](https://user-images.githubusercontent.com/43158502/138584277-7d22e0a4-d405-42b5-91ed-42ba45717dff.png)

## Data Lake vs Data Warehouse

### Data Lake
- Python, Spark와 같은 것을 사용 -> power, flexibility (특히 통계 관련을 사용하는 경우 통계에만 집중하는 Computing Framework 사용 가능)
- 정형 및 비정형 데이터가 함께 작동한다.
- `schema-on-read`

### Data Warehouse
- 대부분 SQL
- 구조화된 데이터로만 작동
- 분석 쿼리를 수행하도록 최적화. Data Lake보다 일반적으로 빠르다. 정규화 but 유연성이 떨어진다.
- `schema-on-write`

> `Data -> Data Lake에 저장 -> Data Lake에서 정리 -> DAta Warehouse에 저장`

![image](https://user-images.githubusercontent.com/43158502/138584270-6bdfd6ca-1f28-436c-8f9b-89ef0a94a244.png)

`[참고] https://www.snowflake.com/trending/data-lake-vs-data-warehouse`

