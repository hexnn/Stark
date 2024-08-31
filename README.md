# Stark大数据治理引擎
## 基于Spark打造的简单易用、超高性能批流一体数据集成和数据分析引擎
* 【开箱即用】无需任何编码，配置规则文件即可完成一站式数据采集、数据建模和数据分析等任务
* 【批流一体】支持离线、实时、离线实时混合三种数据读写模式，做到真正批流一体，离线和实时数据全流程打通
* 【变化捕获】支持变化数据捕获（增删改），支持实时监测CDC数据更新到目标数据源，支持CDC实时与离线数据的多源异构融合
* 【来源丰富】支持常见关系型数据库、NoSQL数据库、数据仓库、图数据库、文件数据源等几十种数据源，以满足各种数据对接需求
* 【过程观测】支持单步调试模式，可实时监测任务执行情况，了解每一步的数据处理过程，核查计算结果
* 【性能高效】支持单表、多表、多表关联、整库数据采集和数据分析，可利用集群能力轻松处理百亿级数据
* 【易于扩展】基于Stark规则文件进行页面化封装，很容易就能实现一套完整的数据集成、数据建模和数据分析等中台产品

## 引擎特性（持续更新）
|类型         |数据源      |批模式(读)|批模式(写)|流模式(读)|流模式(写)|CDC(读) |CDC(写) |
|:------------|:-----------|:--------:|:--------:|:--------:|:--------:|:------:|:------:|
|关系型数据库 |MySQL       |√         |√         |√         |√         |增,删,改|增,删,改|
|			  |MariaDB     |√         |√         |√         |√         |增,删,改|增,删,改|
|             |PostgreSQL  |√         |√         |√         |√         |增,删,改|增,删,改|
|             |Oracle      |√         |√         |√         |√         |增,删,改|增,删,改|
|             |SQLServer   |√         |√         |√         |√         |增,删,改|增,删,改|
|             |DB2         |√         |√         |√         |√         |增,删,改|增,删,改|
|NoSQL数据库  |HBase	   |√         |√         |√         |√         |增      |增,删,改|
|             |Phoenix     |√         |√         |          |√         |        |增,删,改|
|             |MongoDB     |√         |√         |√         |√         |增,删,改|增,删,改|
|数据仓库     |Hive        |√         |√         |          |√         |        |增      |
|             |StarRocks   |√         |√         |          |√         |        |增,删,改|
|             |Doris       |√         |√         |          |√         |        |增,删,改|
|             |ClickHouse  |√         |√         |√         |√         |增,删,改|增,删,改|
|消息中间件   |Kafka       |√         |√         |√         |√         |增      |增      |
|图数据库     |Neo4j       |√         |√         |√         |√         |增      |增,删,改|
|文件数据源   |Text        |√         |√         |√         |√         |增      |增      |
|             |CSV         |√         |√         |√         |√         |增      |增      |
|             |Excel       |√         |√         |√         |√         |增      |增      |
|             |JSON        |√         |√         |√         |√         |增      |增      |
|             |ORC         |√         |√         |√         |√         |增      |增      |
|             |Parquet     |√         |√         |√         |√         |增      |增      |

## 规则文件样例（开箱即用，批流一体，多表关联）
```
{
  "env": {
    "param": "hdfs://cluster/starks/params/test.json",
  },
  "source": [
    {
      "identifier": "ss001",
      "name": "用户基本信息表(存量数据)",
      "type": "ORACLE",
      "dataset": "users_basic",
      "mode": "BATCH",
      "connection": {
        "url": "jdbc:oracle:thin:@//127.0.0.1:1521/XE",
        "driver": "oracle.jdbc.OracleDriver",
        "user": "system",
        "password": "system"
      }
    },
    {
      "identifier": "ss002",
      "name": "用户详细信息表(实时更新)",
      "type": "MYSQL",
      "dataset": "users_detail",
      "mode": "STREAM",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/test",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "root",
        "password": "root"
      }
    }
  ],
  "transform": [
    {
      "identifier": "tf001",
      "name": "用户基本信息和详细信息关联合并",
      "source": ["ss001", "ss002"],
      "sql": "select ss001.*, ss002.detail as detail from ss001 inner join ss002 on ss001.id = ss002.id",
      "transout": ["ts001"]
    }
  ],
  "transout": [
    {
      "identifier": "ts001",
      "transform": ["tf001"],
      "sink": ["sk001"]
    }
  ],
  "sink": [
    {
      "identifier": "sk001",
      "name": "通过JDBC协议输出到HIVE数仓",
      "type": "HIVE",
      "dataset": "users_info",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:hive2://127.0.0.1:10000/test",
        "driver": "org.apache.hive.jdbc.HiveDriver",
        "user": "hive"
      }
    }
  ]
}
```

## Stark引擎 [预览版] 使用指南
* 点击下载：[Stark-1.0.0-preview.jar](https://github.com/hexnn/Stark/releases/download/1.0.0-preview/Stark-1.0.0-preview.jar) 
* 修改`Stark-1.0.0-preview.jar`根目录下的`rule.json`规则文件，指定`source`和`sink`中的 [MySQL] 数据源连接信息
* 上传修改后的`Stark-1.0.0-preview.jar`到服务器（需要安装[Spark3.x](https://spark.apache.org/downloads.html)客户端，官网下载解压即可）
* 进入`$SPARK_HOME/bin`目录下，执行`spark-submit Stark-1.0.0-preview.jar`命令，等待任务执行结束
* 进入 [MySQL] 数据库，查看`sink`节点指定的输出表，验证数据是否采集成功
> 注意：[预览版] 只能使用 [MySQL] 数据源做 [批处理] 操作，想要体验Stark引擎完整版功能请联系↓↓↓

## 完整版试用及定制化开发
* 通过以下方式了解更多关于Stark引擎的相关信息，可接受定制化开发需求↓↓↓
* WeChat：xxx-hx-xxx（潇湘夜雨）
* Email：hexing_xx@163.com
