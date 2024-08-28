# Stark大数据治理引擎
## 基于Spark打造的简单易用、超高性能批流一体数据集成和数据分析引擎
* 开箱即用：无需任何编码，配置规则文件即可完成一站式的数据采集、数据建模和数据分析等任务
* 批流一体：支持离线、实时、离线实时混合三种数据读写模式，做到真正批流一体，离线和实时数据全流程打通
* CDC数据捕获：支持变化数据捕获（增删改），支持将CDC数据实时更新到目标数据源，支持CDC实时与离线数据源多源异构融合
* 数据源丰富：支持常见关系型数据库、NoSQL数据库、数据仓库、图数据库、文件数据源等几十种数据源，以满足各种数据对接需求
* 性能高效：支持单表、多表、整库数据采集和数据分析，可轻松处理百亿级数据，可实时监测任务执行情况，了解数据处理过程
* 易于扩展：基于Stark规则文件进行页面化封装，很容易就能实现一套完整的数据集成、数据建模和数据分析等中台产品

## 引擎特性（持续更新）
|类型         |数据源      |批模式(读)|批模式(写)|流模式(读)|流模式(写)|CDC(读)|CDC(写)   |
|:------------|:-----------|:--------:|:--------:|:--------:|:--------:|:-----:|:--------:|
|关系型数据库 |MySQL       |√         |√         |√         |√         |√      |增、删、改|
|			  |MariaDB     |√         |√         |√         |√         |√      |增、删、改|
|             |PostgreSQL  |√         |√         |√         |√         |√      |增、删、改|
|             |Oracle      |√         |√         |√         |√         |√      |增、删、改|
|             |SQLServer   |√         |√         |√         |√         |√      |增、删、改|
|             |DB2         |√         |√         |√         |√         |√      |增、删、改|
|NoSQL数据库  |HBase	   |√         |√         |√         |√         |       |增、删、改|
|             |Phoenix     |√         |√         |√         |√         |       |增、删、改|
|             |MongoDB     |√         |√         |√         |√         |√      |增、删、改|
|数据仓库     |Hive        |√         |√         |√         |√         |       |增        |
|             |StarRocks   |√         |√         |√         |√         |√      |增、删、改|
|             |Doris       |√         |√         |√         |√         |√      |增、删、改|
|             |ClickHouse  |√         |√         |√         |√         |√      |增、删、改|
|消息中间件   |Kafka       |√         |√         |√         |√         |√      |增        |
|图数据库     |Neo4j       |√         |√         |√         |√         |       |增、删、改|
|文件数据源   |Text        |√         |√         |√         |√         |√      |增、删、改|
|             |CSV         |√         |√         |√         |√         |√      |增、删、改|
|             |Excel       |√         |√         |√         |√         |√      |增、删、改|
|             |JSON        |√         |√         |√         |√         |√      |增、删、改|
|             |ORC         |√         |√         |√         |√         |√      |增、删、改|
|             |Parquet     |√         |√         |√         |√         |√      |增、删、改|

## 免费试用及定制化开发
* 通过以下方式了解更多信息，可接受定制化开发需求↓↓↓
* WeChat：xxx-hx-xxx（潇湘夜雨）
* Email：hexing_xx@163.com
