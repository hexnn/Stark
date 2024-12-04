# Stark大数据治理引擎
## 基于Spark打造的简单易用、超高性能批流一体数据集成和数据分析引擎
* 【开箱即用】零编码，基于规则文件即可完成一站式数据采集、数据建模和数据分析等任务
* 【批流一体】支持离线、实时、离线实时混合三种读写模式，离线和实时数据全流程打通
* 【变化捕获】支持CDC变化数据捕获，实时监测数据变化并更新到目标，支持实时与离线数据多源异构融合
* 【来源丰富】支持关系数据库、NoSQL数据仓库、图数据库、文件等几十种数据源，满足各种数据对接需求
* 【过程观测】支持单步调试，可监测每一个环节的任务执行情况，了解数据处理过程，核查计算结果和数据质量
* 【性能高效】支持跨数据源单表、多表、多表关联、整库数据采集和数据分析，可利用集群能力处理百亿级数据
* 【易于扩展】基于Stark规则引擎界面化封装，可在极短时间实现整套数据采集、数据建模和数据分析等中台产品

## 引擎特性（持续更新）
|类型         |数据源      |批模式(读)|批模式(写)|流模式(读)|流模式(写)|CDC(读) |CDC(写) |
|:------------|:-----------|:--------:|:--------:|:--------:|:--------:|:------:|:------:|
|关系型数据库  |MySQL       |√         |√         |√         |√         |增,删,改|增,删,改|
|			        |MariaDB     |√         |√         |√         |√         |增,删,改|增,删,改|
|             |PostgreSQL  |√         |√         |√         |√         |增,删,改|增,删,改|
|             |Oracle      |√         |√         |√         |√         |增,删,改|增,删,改|
|             |SQLServer   |√         |√         |√         |√         |增,删,改|增,删,改|
|             |DB2         |√         |√         |√         |√         |增,删,改|增,删,改|
|NoSQL数据库   |HBase	     |√         |√         |√         |√         |增      |增,删,改|
|             |Phoenix     |√         |√         |          |√         |        |增,删,改|
|             |MongoDB     |√         |√         |√         |√         |增,删,改|增,删,改|
|数据仓库      |Hive        |√         |√         |          |√         |        |增      |
|             |StarRocks   |√         |√         |          |√         |        |增,删,改|
|             |Doris       |√         |√         |          |√         |        |增,删,改|
|             |ClickHouse  |√         |√         |√         |√         |增,删,改|增,删,改|
|消息中间件    |Kafka       |√         |√         |√         |√         |增      |增      |
|图数据库      |Neo4j       |√         |√         |√         |√         |增      |增,删,改|
|文件数据源    |Text        |√         |√         |√         |√         |增      |增      |
|             |CSV         |√         |√         |√         |√         |增      |增      |
|             |Excel       |√         |√         |√         |√         |增      |增      |
|             |JSON        |√         |√         |√         |√         |增      |增      |
|             |ORC         |√         |√         |√         |√         |增      |增      |
|             |Parquet     |√         |√         |√         |√         |增      |增      |
|             |Avro        |√         |√         |√         |√         |增      |增      |

## 规则文件样例（开箱即用，批流一体，跨数据源多表关联）
```
{
  "env": {
    "param": "hdfs://cluster/starks/params/test.json",
    "udf": [
      {
        "name": "maps",
        "class": "cn.hex.bricks.udf.Maps",
        "jar": "hdfs://cluster/starks/udf/bricks.jar",
        "temporary": "true"
      }
    ]
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
    },
    {
      "identifier": "ss003",
      "name": "用户维度信息表(存量数据)",
      "type": "CSV",
      "mode": "BATCH",
      "connection": {
        "url": "hdfs://cluster/stark/users.csv"
      }
    }
  ],
  "transform": [
    {
      "identifier": "tf001",
      "name": "根据CSV中的用户维度信息，对用户基本信息和详细信息进行关联合并",
      "source": ["ss001", "ss002", "ss003"],
      "sql": "select ss001.*, ss002.detail as detail from ss001 inner join ss002 on ss001.id = ss002.id inner join ss003 on ss001.id = ss003.id",
      "transout": ["ts001"]
    }
  ],
  "transout": [
    {
      "identifier": "ts001",
      "transform": ["tf001"],
      "sink": ["sk001","sk002","sk003","sk004","sk005","sk006","sk007","sk008","sk009","sk010","sk011","sk012","sk013"]
    }
  ],
  "sink": [
    {
      "identifier": "sk001",
      "name": "通过JDBC协议输出到MYSQL(实时更新)",
      "type": "MYSQL",
      "dataset": "users_basic_detail",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/stark",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "stark",
        "password": "stark"
      }
    },
    {
      "identifier": "sk002",
      "name": "通过JDBC协议输出到ORACLE(实时更新)",
      "type": "ORACLE",
      "dataset": "users_basic_detail",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:oracle:thin:@127.0.0.1:1521:XE",
        "driver": "oracle.jdbc.OracleDriver",
        "user": "stark",
        "password": "stark"
      }
    },
    {
      "identifier": "sk003",
      "name": "通过JDBC协议输出到POSTGRESQL(实时更新)",
      "type": "POSTGRESQL",
      "dataset": "users_basic_detail",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:postgresql://127.0.0.1:5432/stark",
        "driver": "org.postgresql.Driver",
        "user": "stark",
        "password": "stark"
      }
    },
    {
      "identifier": "sk004",
      "name": "通过JDBC协议输出到DB2(实时更新)",
      "type": "DB2",
      "dataset": "users_basic_detail",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:db2://127.0.0.1:50000/stark",
        "driver": "com.ibm.db2.jcc.DB2Driver",
        "user": "stark",
        "password": "stark"
      }
    },
    {
      "identifier": "sk005",
      "name": "通过ThriftServer协议输出到HIVE(实时更新)",
      "type": "HIVE",
      "dataset": "users_basic_detail",
      "mode": "APPEND",
      "connection": {
        "thrift": "thrift://127.0.0.1:9083",
        "database": "stark"
      }
    },
    {
      "identifier": "sk006",
      "name": "通过JDBC协议输出到HIVE(实时更新)",
      "type": "HIVEJDBC",
      "dataset": "users_basic_detail",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:hive2://127.0.0.1:10000/stark",
        "driver": "org.apache.hive.jdbc.HiveDriver",
        "user": "stark"
      }
    },
    {
      "identifier": "sk007",
      "name": "通过JDBC协议输出到SQLSERVER(实时更新)",
      "type": "SQLSERVER",
      "schema": "stark",
      "dataset": "users_basic_detail",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:sqlserver://;serverName=127.0.0.1;port=1433;databaseName=stark",
        "driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
        "user": "sa",
        "password": "password"
      }
    },
    {
      "identifier": "sk008",
      "name": "输出到EXCEL文件(实时更新)",
      "type": "EXCEL",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users_basic_detail.xlsx"
      }
    },
    {
      "identifier": "sk009",
      "name": "输出到JSON文件(实时更新)",
      "type": "JSON",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users_basic_detail.json"
      }
    },
    {
      "identifier": "sk010",
      "name": "输出到TXT文件(实时更新)",
      "type": "TEXT",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users_basic_detail.txt"
      }
    },
    {
      "identifier": "sk011",
      "name": "输出到CSV文件(实时更新)",
      "type": "CSV",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users_basic_detail.csv"
      }
    },
    {
      "identifier": "sk012",
      "name": "输出到ORC文件(实时更新)",
      "type": "ORC",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users_basic_detail.orc"
      }
    },
    {
      "identifier": "sk013",
      "name": "输出到PARQUET文件(实时更新)",
      "type": "PARQUET",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users_basic_detail.parquet"
      }
    }
  ]
}
```

## Stark引擎 `[预览版]` 重磅更新！支持[MySQL/Oracle/PostgreSQL/DB2/SQLServer/HiveJDBC]六种数据源
* 点击下载：[Stark-1.2.0-preview.jar](https://github.com/hexnn/Stark/releases/download/1.2.0-preview/Stark-1.2.0-preview.jar) 
* 修改 `Stark-1.2.0-preview.jar` 根目录下的 `rule.json` 规则文件，指定 `source` 和 `sink` 中的 `[MySQL/Oracle/PostgreSQL/DB2/SQLServer/HiveJDBC]` 数据源连接信息
* 上传修改后的 `Stark-1.2.0-preview.jar` 到服务器（需要安装[Spark3.x](https://spark.apache.org/downloads.html)客户端，官网下载tgz包解压，安装配置JAVA_HOME即可运行）
* 进入 `$SPARK_HOME/bin` 目录下，执行 `spark-submit --master local[*] Stark-1.2.0-preview.jar` 命令，等待任务执行结束
* 进入 `[MySQL/Oracle/PostgreSQL/DB2/SQLServer/HiveJDBC]` 数据库，查看 `sink` 节点指定的输出表，验证数据是否采集成功
> 注意：`[预览版]` 只能使用 `[MySQL/Oracle/PostgreSQL/DB2/SQLServer/HiveJDBC]` 数据源做 `[批处理]` 操作，想要体验Stark引擎完整版功能请联系↓↓↓

## 完整版免费试用及定制化开发
* 通过以下方式了解更多关于Stark引擎的相关信息，可试用完整版功能，也可接受业务定制化开发需求↓↓↓
* WeChat：xxx-hx-xxx（潇湘夜雨）
* Email：hexing_xx@163.com
