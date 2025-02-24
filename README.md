# Stark大数据治理引擎
## 基于Spark打造的简单易用、超高性能批流一体数据集成和数据分析引擎
* 【开箱即用】零编码，基于规则文件即可完成一站式数据采集、数据建模、算法建模和数据分析任务
* 【批流一体】支持离线、实时、离线实时混合三种读写模式，离线和实时数据全流程打通
* 【变化捕获】支持CDC变化数据捕获，实时监测数据变化并更新到目标，支持离线与实时数据多源异构融合
* 【来源丰富】支持关系数据库、NoSQL数据仓库、图数据库、文件等几十种数据源，满足各种数据对接需求
* 【信创支持】支持基于X86及ARM架构的国产CPU及操作系统部署，支持达梦、人大金仓等国产信创数据源
* 【机器学习】支持几十种机器学习算法，与各种数据源全流程融合，基于简单配置即可实现复杂的算法建模
* 【算法调优】支持机器学习算法参数调优，支持超参动态优化，算法训练及预测过程可观测，让数据更智能
* 【过程观测】支持单步调试，可监测每一个环节的任务执行情况，了解数据处理过程，核查计算结果和数据质量
* 【性能高效】支持跨数据源单表、多表、多表关联、整库数据采集和数据分析，可利用集群能力处理百亿级数据
* 【易于扩展】基于Stark规则引擎界面化封装，可在极短时间实现整套数据采集、数据建模和数据分析等中台产品

## 数据源特性（持续更新中）
|类型         |数据源        |批模式(读)|批模式(写) |流模式(读)|流模式(写) |CDC(读) |CDC(写) |
|:------------|:------------|:--------:|:--------:|:--------:|:--------:|:------:|:------:|
|关系型数据库  |MySQL        |√         |√         |√         |√         |增,删,改|增,删,改|
|			        |MariaDB      |√         |√         |√         |√         |增,删,改|增,删,改|
|             |Oracle       |√         |√         |√         |√         |增,删,改|增,删,改|
|             |PostgreSQL   |√         |√         |√         |√         |增,删,改|增,删,改|
|             |SQLServer    |√         |√         |√         |√         |增,删,改|增,删,改|
|             |DB2          |√         |√         |√         |√         |增,删,改|增,删,改|
|             |SQLite       |√         |√         |√         |√         |增,删,改|增,删,改|
|NoSQL数据库   |HBase	      |√         |√         |√         |√         |增,删,改|增,删,改|
|             |Phoenix      |√         |√         |          |√         |        |增,删,改|
|             |Cassandra    |√         |√         |√         |√         |增,删,改|增,删,改|
|             |MongoDB      |√         |√         |√         |√         |增,删,改|增,删,改|
|             |Redis        |√         |√         |√         |√         |增      |增,删,改|
|             |Elasticsearch|√         |√         |√         |√         |增      |增,删,改|
|数据仓库      |Hive         |√         |√         |          |√         |        |增     |
|             |StarRocks    |√         |√         |          |√         |        |增,删,改|
|             |Doris        |√         |√         |          |√         |        |增,删,改|
|             |ClickHouse   |√         |√         |√         |√         |增,删,改|增,删,改|
|             |Snowflake    |√         |√         |√          |√        |        |增,删,改|
|消息中间件    |Kafka        |√         |√         |√         |√         |增      |增      |
|图数据库      |Neo4j        |√         |√         |√         |√         |增      |增,删,改|
|空间数据库    |PostGIS      |√         |√         |√         |√         |增,删,改|增,删,改|
|文件数据源    |Text         |√         |√         |√         |√         |增      |增      |
|             |CSV          |√         |√         |√         |√         |增      |增      |
|             |Excel        |√         |√         |√         |√         |增      |增      |
|             |JSON         |√         |√         |√         |√         |增      |增      |
|             |XML          |√         |√         |√         |√         |增      |增      |
|             |ORC          |√         |√         |√         |√         |增      |增      |
|             |Parquet      |√         |√         |√         |√         |增      |增      |
|             |Avro         |√         |√         |√         |√         |增      |增      |
|信创数据源    |OceanBase    |√         |√         |√         |√         |增,删,改 |增,删,改|
|             |GaussDB      |√         |√         |√         |√         |增,删,改 |增,删,改|
|             |达梦         |√         |√         |√         |√         |增,删,改 |增,删,改|
|             |人大金仓     |√         |√         |√         |√         |增,删,改 |增,删,改|

## 机器学习特性（持续更新中）
|学习方式     |算法类型     |算法名称                        |算法简称     |算法描述           |应用场景       |
|:----------:|:-----------:|:------------------------------:|:----------:|:-----------------|:-------------|
|有监督学习   |推荐算法      |AlternatingLeastSquares        |ALS         |交替最小二乘法      |数据推荐       |     
|            |分类算法      |DecisionTreeClassifier         |DTC         |决策树分类          |二分类,多分类  |
|            |             |FMClassifier                   |FMC         |因子分解机分类       |二分类        |
|            |             |GBTClassifier                  |GBTC        |梯度提升树分类       |二分类        |
|            |             |LogisticRegression             |LRC         |逻辑回归分类         |二分类        |
|            |             |MultilayerPerceptronClassifier |MLPC        |多层感知器分类       |二分类,多分类  |
|            |             |NaiveBayes                     |NBC         |朴素贝叶斯分类       |二分类,多分类  |
|            |             |RandomForestClassifier         |RFC         |随机森林分类        |二分类,多分类  |
|            |             |LinearSVC                      |SVC         |线性SVM分类         |二分类        |
|            |回归算法      |AFTSurvivalRegression          |AFTSR       |加速失效时间模型回归 |数据预测      |
|            |             |DecisionTreeRegressor          |DTR         |决策树回归          |数据预测      |
|            |             |FMRegressor                    |FMR         |因子分解机回归      |数据预测      |
|            |             |GBTRegressor                   |GBTR        |梯度提升树回归      |数据预测       |
|            |             |GeneralizedLinearRegression    |GLMR        |广义线性模型回归    |数据预测       |
|            |             |IsotonicRegression             |IR          |保序回归           |数据预测       |
|            |             |LinearRegression               |LR          |线性回归           |数据预测       |
|            |             |RandomForestRegressor          |RFR         |随机森林回归        |数据预测       |
|无监督学习   |聚类算法      |KMeans                         |KMEANS      |K均值聚类          |聚类          |
|            |             |GaussianMixture                |GM          |高斯混合模型        |聚类          |
|            |             |LDA                            |LDA         |潜在狄利克雷分配    |聚类          |

## 规则文件样例（开箱即用，批流一体，支持跨数据源多表关联）
```
{
  "env": {
    "param": "hdfs://cluster/stark/params/test.json",
    "udf": [
      {
        "name": "maps",
        "class": "cn.hex.bricks.udf.Maps",
        "jar": "hdfs://cluster/stark/udf/bricks.jar",
        "temporary": "true"
      }
    ]
  },
  "source": [
    {
      "identifier": "ss001",
      "name": "用户基础信息表(MYSQL存量数据)",
      "type": "MYSQL",
      "mode": "BATCH",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/test",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "root",
        "password": "root",
        "dataset": "users"
      }
    },
    {
      "identifier": "ss002",
      "name": "用户详细信息表(HIVE存量数据)",
      "type": "HIVE",
      "mode": "BATCH",
      "connection": {
        "url": "thrift://127.0.0.1:9083",
        "database": "test",
        "dataset": "users"
      }
    },
    {
      "identifier": "ss003",
      "name": "用户维度信息表(CSV实时数据)",
      "type": "CSV",
      "mode": "STREAM",
      "connection": {
        "url": "hdfs://cluster/test/"
      }
    }
  ],
  "transform": [
    {
      "identifier": "tf001",
      "name": "根据CSV中的用户维度实时数据，对用户基本信息和详细信息进行关联合并",
      "source": [
        "ss001",
        "ss002",
        "ss003"
      ],
      "sql": "select ss001.*, ss002.detail as detail from ss001 inner join ss002 on ss001.id = ss002.id inner join ss003 on ss001.id = ss003.id",
      "transout": [
        "ts001"
      ]
    }
  ],
  "transout": [
    {
      "identifier": "ts001",
      "transform": [
        "tf001"
      ],
      "sink": [
        "sk_jdbc_mysql",
        "sk_jdbc_mariadb",
        "sk_jdbc_oracle",
        "sk_jdbc_postgresql",
        "sk_jdbc_sqlserver",
        "sk_jdbc_db2",
        "sk_jdbc_hive",
        "sk_jdbc_doris",
        "sk_jdbc_starrocks",
        "sk_jdbc_phoenix",
        "sk_jdbc_dameng",
        "sk_jdbc_kingbase",
        "sk_file_excel",
        "sk_file_json",
        "sk_file_text",
        "sk_file_csv",
        "sk_file_orc",
        "sk_file_parquet",
        "sk_file_xml",
        "sk_hive",
        "sk_kafka",
        "sk_hbase",
        "sk_mongodb",
        "sk_elasticsearch"
      ]
    }
  ],
  "sink": [
    {
      "identifier": "sk_jdbc_mysql",
      "name": "通过JDBC协议输出到MYSQL(实时更新)",
      "type": "MYSQL",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/stark",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "stark",
        "password": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_mariadb",
      "name": "通过JDBC协议输出到MARIADB(实时更新)",
      "type": "MARIADB",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:mariadb://127.0.0.1:3306/stark",
        "driver": "org.mariadb.jdbc.Driver",
        "user": "stark",
        "password": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_oracle",
      "name": "通过JDBC协议输出到ORACLE(实时更新)",
      "type": "ORACLE",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:oracle:thin:@127.0.0.1:1521:XE",
        "driver": "oracle.jdbc.OracleDriver",
        "user": "stark",
        "password": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_postgresql",
      "name": "通过JDBC协议输出到POSTGRESQL(实时更新)",
      "type": "POSTGRESQL",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:postgresql://127.0.0.1:5432/stark",
        "driver": "org.postgresql.Driver",
        "user": "stark",
        "password": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_sqlserver",
      "name": "通过JDBC协议输出到SQLSERVER(实时更新)",
      "type": "SQLSERVER",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:sqlserver://;serverName=127.0.0.1;port=1433;databaseName=stark",
        "driver": "com.microsoft.sqlserver.jdbc.SQLServerDriver",
        "user": "sa",
        "password": "password",
        "schema": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_db2",
      "name": "通过JDBC协议输出到DB2(实时更新)",
      "type": "DB2",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:db2://127.0.0.1:50000/stark",
        "driver": "com.ibm.db2.jcc.DB2Driver",
        "user": "stark",
        "password": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_hive",
      "name": "通过JDBC协议输出到HIVE(实时更新)",
      "type": "HIVEJDBC",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:hive2://127.0.0.1:10000/stark",
        "driver": "org.apache.hive.jdbc.HiveDriver",
        "user": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_doris",
      "name": "通过JDBC协议输出到DORIS(实时更新)",
      "type": "DORIS",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/stark",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "stark",
        "password": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_starrocks",
      "name": "通过JDBC协议输出到STARROCKS(实时更新)",
      "type": "STARROCKS",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/stark",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "stark",
        "password": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_phoenix",
      "name": "通过JDBC协议输出到PHOENIX(实时更新)",
      "type": "PHOENIX",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:phoenix:node01,node02,node03:2181",
        "driver": "org.apache.phoenix.jdbc.PhoenixDriver",
        "schema": "STARK",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_dameng",
      "name": "通过JDBC协议输出到DAMENG(实时更新)",
      "type": "DAMENG",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:dm://127.0.0.1:5236/STARK",
        "driver": "dm.jdbc.driver.DmDriver",
        "user": "STARK",
        "password": "STARK",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_jdbc_kingbase",
      "name": "通过JDBC协议输出到KINGBASE(实时更新)",
      "type": "KINGBASE",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:kingbase8://127.0.0.1:54321/stark",
        "driver": "com.kingbase8.Driver",
        "user": "kingbase",
        "password": "kingbase",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_file_excel",
      "name": "输出到EXCEL文件(实时更新)",
      "type": "EXCEL",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users.xlsx"
      }
    },
    {
      "identifier": "sk_file_json",
      "name": "输出到JSON文件(实时更新)",
      "type": "JSON",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users.json"
      }
    },
    {
      "identifier": "sk_file_text",
      "name": "输出到TXT文件(实时更新)",
      "type": "TEXT",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users.txt"
      }
    },
    {
      "identifier": "sk_file_csv",
      "name": "输出到CSV文件(实时更新)",
      "type": "CSV",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users.csv"
      }
    },
    {
      "identifier": "sk_file_orc",
      "name": "输出到ORC文件(实时更新)",
      "type": "ORC",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users.orc"
      }
    },
    {
      "identifier": "sk_file_parquet",
      "name": "输出到PARQUET文件(实时更新)",
      "type": "PARQUET",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users.parquet"
      }
    },
    {
      "identifier": "sk_file_xml",
      "name": "输出到XML文件(实时更新)",
      "type": "XML",
      "mode": "APPEND",
      "connection": {
        "url": "hdfs://cluster/stark/users.xml"
      }
    },
    {
      "identifier": "sk_hive",
      "name": "通过ThriftServer协议输出到HIVE(实时更新)",
      "type": "HIVE",
      "mode": "APPEND",
      "connection": {
        "url": "thrift://127.0.0.1:9083",
        "database": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_kafka",
      "name": "输出到Kafka消息队列(实时更新)",
      "type": "KAFKA",
      "mode": "APPEND",
      "connection": {
        "kafka.bootstrap.servers": "node01:9092,node02:9092,node03:9092",
        "topic": "users"
      }
    },
    {
      "identifier": "sk_hbase",
      "name": "输出到HBase列存数据库(实时更新)",
      "type": "HBASE",
      "mode": "APPEND",
      "connection": {
        "url": "node01,node02,node03",
        "port": "2181",
        "schema": "stark",
        "dataset": "users",
        "primaryKey": "id"
      }
    },
    {
      "identifier": "sk_mongodb",
      "name": "输出到MongoDB文档数据库(实时更新)",
      "type": "MONGODB",
      "mode": "APPEND",
      "connection": {
        "url": "mongodb://127.0.0.1:27017",
        "database": "stark",
        "dataset": "users"
      }
    },
    {
      "identifier": "sk_elasticsearch",
      "name": "输出到ElasticSearch全文检索数据库(实时更新)",
      "type": "ELASTICSEARCH",
      "mode": "APPEND",
      "connection": {
        "url": "127.0.0.1",
        "port": "9200",
        "dataset": "users"
      }
    }
  ]
}
```

## 规则文件样例（机器学习，支持流式数据增量预测）
```
{
  "env": {},
  "source": [
    {
      "identifier": "user_movie_training",
      "name": "用户对电影类型的偏好记录",
      "type": "JSON",
      "mode": "BATCH",
      "connection": {
        "url": "hdfs://cluster/stark/ml/data/user_movie_training.json"
      },
      "options": {
        "multiLine": "true"
      }
    },
    {
      "identifier": "user_movie_prediction",
      "name": "用户电影类型偏好预测",
      "type": "JSON",
      "mode": "STREAM",
      "connection": {
        "url": "hdfs://cluster/stark/ml/data/user_movie_prediction"
      },
      "options": {
        "multiLine": "true"
      }
    }
  ],
  "transform": [
    {
      "identifier": "tf001",
      "name": "对用户电影类型偏好记录进行分类模型训练，用于根据用户预测偏好的电影类型",
      "source": [
        "user_movie_training"
      ],
      "ml": {
        "training": {
          "type": "GBTC",
          "path": "hdfs://cluster/stark/ml/gbtc",
          "params": {
            "labelCol": "preference"
          }
        }
      },
      "transout": [
        "ts001"
      ]
    },
    {
      "identifier": "tf002",
      "name": "根据用户和电影类型推荐记录，预测对该电影类型的偏好程度",
      "source": [
        "user_movie_prediction"
      ],
      "ml": {
        "prediction": {
          "type": "GBTC",
          "path": "hdfs://cluster/stark/ml/gbtc"
        }
      },
      "transout": [
        "ts002"
      ]
    }
  ],
  "transout": [
    {
      "identifier": "ts001",
      "transform": [
        "tf001"
      ]
    },
    {
      "identifier": "ts002",
      "transform": [
        "tf002"
      ],
      "sink": [
        "sk_gbtc_prediction"
      ]
    }
  ],
  "sink": [
    {
      "identifier": "sk_gbtc_prediction",
      "name": "输出根据用户和电影类型预测的偏好结果",
      "type": "MYSQL",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/stark",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "stark",
        "password": "stark",
        "dataset": "sk_gbtc_prediction"
      }
    }
  ]
}
```

## Stark引擎 `[预览版]` 史诗级更新！免费使用19种多源异构数据源，与多达20种机器学习算法无缝融合！
* 12种JDBC类数据源`[MySQL/MariaDB/Oracle/PostgreSQL/SQLServer/DB2/HiveJDBC/Doris/StarRocks/Phoenix/达梦Dameng/人大金仓Kingbase]`
* 7种文件类数据源`[Excel/JSON/Text/CSV/ORC/Parquet/XML]` 
* 20种机器学习算法`[8种分类算法/8种回归算法/3种聚类算法/1种推荐算法]` 
* 点击下载：[Stark-1.4.0-preview.jar](https://github.com/hexnn/Stark/releases/download/1.4.0-preview/Stark-1.4.0-preview.jar) 
* 修改 `Stark-1.4.0-preview.jar` 根目录下的 `rule.json` 规则文件，指定 `source` 和 `sink` 中的数据源连接信息
* 上传修改后的 `Stark-1.4.0-preview.jar` 到服务器（需要安装[Spark3.x](https://archive.apache.org/dist/spark/spark-3.3.4/spark-3.3.4-bin-hadoop3.tgz)客户端，配置JAVA_HOME环境变量即可运行）
* 进入 `$SPARK_HOME/bin` 目录下，执行 `spark-submit --master local[*] Stark-1.4.0-preview.jar` 命令，等待任务执行结束
* 查看 `sink` 节点指定的数据连接及输出，验证数据是否写入成功
> 注意：`[预览版]` 只能使用以上 `[19种多源异构数据源]` 以及 `[20种机器学习算法]` 做 `[批处理]` 操作，想要体验Stark引擎完整版功能请联系↓↓↓

## 完整版免费试用及定制化开发
* 通过以下方式了解更多关于Stark引擎的相关信息，可试用完整版功能，也可接受业务定制化开发需求↓↓↓
* WeChat：xxx-hx-xxx（潇湘夜雨）
* Email：hexing_xx@163.com
