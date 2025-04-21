# Stark大数据治理引擎
## 基于Spark内核的简单易用、超高性能批流一体数据集成和数据分析引擎
* 【开箱即用】零编码，基于规则文件即可完成一站式数据采集、数据建模、算法建模和数据分析任务
* 【批流一体】支持离线、实时、离线实时混合三种读写模式，离线和实时数据全流程打通
* 【变化捕获】支持CDC变化数据捕获，实时监测数据变化并更新到目标，支持离线与实时数据多源异构融合
* 【来源丰富】支持关系数据库、NoSQL数据仓库、图数据库、文件等几十种数据源，满足各种数据对接需求
* 【信创支持】支持基于X86及ARM架构的国产CPU及操作系统部署，支持达梦、人大金仓等国产信创数据源
* 【机器学习】支持几十种机器学习算法，与各种数据源全流程融合，基于简单配置即可实现复杂的算法建模
* 【算法调优】支持机器学习算法参数调优，支持超参动态优化，算法训练及预测过程可观测，让数据更智能
* 【质量校验】内置50+数据质量校验规则，支持对各种离线和实时数据进行数据质量监测，同时生成校验报告
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

## 质量校验特性（持续更新中）
|质量分类                    |规则参数                 |规则描述                                |使用示例     			                                    |
|:--------------------------:|:-----------------------:|:--------------------------------------:|:---------------------------------------------------------:|
|完整性(checkCompleteness)   |isComplete               |校验单个字段非空                        |"isComplete": ["id"]                                       |
|                            |areComplete              |校验组合字段全部非空                    |"areComplete": ["id,name"]                                 |
|                            |areAnyComplete           |校验组合字段任一非空                    |"areAnyComplete": ["age,birthday"]                         |
|                            |hasCompleteness          |校验单个字段非空比例                    |"hasCompleteness": ["age:ratio>0.2"]                       |
|                            |haveCompleteness         |校验组合字段全部非空比例                |"haveCompleteness": ["name,age:ratio>0.2"]                 |
|                            |haveAnyCompleteness      |校验组合字段任一非空比例                |"haveAnyCompleteness": ["name,age:ratio>0.2"]              |
|唯一性(checkUniqueness)     |isUnique                 |校验字段唯一性                          |"isUnique": ["id"]                                         |
|                            |isPrimaryKey             |校验字段是否为主键                      |"isPrimaryKey": ["id,name"]                                |
|                            |hasUniqueness            |校验单个字段唯一性比例                  |"hasUniqueness": ["id:ratio==1"]                           |
|                            |haveUniqueness           |校验组合字段唯一性比例                  |"haveUniqueness": ["name,age:ratio>0.5"]                   |
|                            |hasDistinctness          |校验单个字段去重性比例                  |"hasDistinctness": ["id:ratio==1"]                         |
|                            |haveDistinctness         |校验组合字段去重性比例                  |"haveDistinctness": ["name,age:ratio>0.5"]                 |
|                            |hasUniqueValueRatio      |校验单个字段唯一性比例                  |"hasUniqueValueRatio": ["id:ratio==1"]                     |
|                            |haveUniqueValueRatio     |校验组合字段唯一性比例                  |"haveUniqueValueRatio": ["name,age:ratio>0.5"]             |
|                            |hasNumberOfDistinctValues|校验单个字段去重后的个数                |"hasNumberOfDistinctValues": ["name:number>0 && number<10"]|
|准确性(checkAccuracy)       |hasSize                  |校验数据行数                            |"hasSize": ["size>0 && size<100"]                          |
|                            |hasColumnCount           |校验字段个数                            |"hasColumnCount": ["count>0 && count<10"]                  |
|                            |hasMin                   |校验数值型字段的最小值                  |"hasMin": ["age:min>=18 && min<=35"]                       |
|                            |hasMax                   |校验数值型字段的最大值                  |"hasMax": ["age:max>=60 && max<120"]                       |
|                            |hasMean                  |校验数值型字段的平均值                  |"hasMean": ["age:mean>=18 && mean<=35"]                    |
|                            |hasSum                   |校验数值型字段的汇总值                  |"hasSum": ["salary:sum>0 && sum<100000"]                   |
|                            |isNonNegative            |校验数值型字段为非负数                  |"isNonNegative": ["age"]                                   |
|                            |isPositive               |校验数值型字段为非0正数                 |"isPositive": ["age"]                                      |
|                            |hasMinLength             |校验文本型字段的最小长度                |"hasMinLength": ["name:length==2"]                         |
|                            |hasMaxLength             |校验文本型字段的最大长度                |"hasMaxLength": ["name:length==4"]                         |
|有效性(checkEffectiveness)  |containsFullName         |校验字段为姓名的比例                    |"containsFullName": ["fullName:ratio>0.8"]                 |
|                            |containsGender           |校验字段为性别的比例                    |"containsGender": ["gender:ratio>0.8"]                     |
|                            |containsIdCard           |校验字段为身份证号的比例                |"containsIdCard": ["idCard:ratio>0.8"]                     |
|                            |containsMobilePhone      |校验字段为手机号码的比例                |"containsMobilePhone": ["mobile:ratio>0.8"]                |
|                            |containsTelePhone        |校验字段为电话号码的比例                |"containsTelePhone": ["tele:ratio>0.8"]                    |
|                            |containsEmail            |校验字段为邮箱账号的比例                |"containsEmail": ["email:ratio>0.8"]                       |
|                            |containsBankCard         |校验字段为银行卡号的比例                |"containsBankCard": ["bankCard:ratio>0.8"]                 |
|                            |containsAddress          |校验字段为地址的比例                    |"containsAddress": ["address:ratio>0.8"]                   |
|                            |containsLongitude        |校验字段为经度的比例                    |"containsLongitude": ["longitude:ratio>0.8"]               |
|                            |containsLatitude         |校验字段为纬度的比例                    |"containsLatitude": ["latitude:ratio>0.8"]                 |
|                            |containsCarNumber        |校验字段为车牌号的比例                  |"containsCarNumber": ["carNumber:ratio>0.8"]               |
|                            |containsURL              |校验字段为URL地址的比例                 |"containsURL": ["url:ratio>0.8"]                           |
|                            |containsIP               |校验字段为IP地址的比例                  |"containsIP": ["ip:ratio>0.8"]                             |
|                            |containsPort             |校验字段为端口号的比例                  |"containsPort": ["port:ratio>0.8"]                         |
|                            |hasDataType              |校验字段是否符合指定数据类型            |"hasDataType": ["id:Numeric"]                              |
|                            |hasPattern               |校验字段是否符合指定的正则表达          |"hasPattern": ["mobile:^1[3-9]\d{9}$"]                     |
|一致性(checkConsistency)    |isLessThan               |校验每行数据的字段c1值小于字段c2值      |"isLessThan": ["c1,c2"]                                    |
|                            |isLessThanOrEqualTo      |校验每行数据的字段c1值小于或等于字段c2值|"isLessThanOrEqualTo": ["n1,n2"]                           |
|                            |isGreaterThan            |校验每行数据的字段c1值大于字段c2值      |"isGreaterThan": ["c1,c2"]                                 |
|                            |isGreaterThanOrEqualTo   |校验每行数据的字段c1值大于或等于字段c2值|"isGreaterThanOrEqualTo": ["c1,c2"]                        |
|                            |isContainedIn            |校验字段值分布在一组固定值中            |"isContainedIn": ["sex:男,女"]                             |
|                            |hasMutualInformation     |校验字段c1和字段c2的数据相互关系        |"hasMutualInformation": ["city,address:ratio>0.5"]         |

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

## 规则文件样例（数据质量校验，支持流式数据增量校验）
```
{
  "env": {},
  "source": [
    {
      "identifier": "ss001",
      "name": "数据质量校验测试表",
      "type": "MYSQL",
      "mode": "BATCH",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/stark",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "root",
        "password": "root",
        "dataset": "dqtest"
      }
    }
  ],
  "transform": [
    {
      "identifier": "tf001",
      "name": "数据质量校验：完整性、唯一性、准确性、及时性、有效性、一致性",
      "source": [
        "ss001"
      ],
      "check": {
        "checkAccuracy": {
          "hasSize": ["size>0 && size<100"],
          "hasColumnCount": ["count>0 && count<10"],
          "hasMin": ["age:min>=18 && min<=35"],
          "hasMax": ["age:max>=60 && max<120"],
          "hasMean": ["age:mean>=18 && mean<=35"],
          "hasSum": ["salary:sum>0 && sum<100000"],
          "isNonNegative": ["age"],
          "isPositive": ["age"],
          "hasMinLength": ["name:length==2"],
          "hasMaxLength": ["name:length==4"]
        },
        "checkCompleteness": {
          "isComplete": ["id"],
          "areComplete": ["id,name"],
          "areAnyComplete": ["age,birthday"],
          "hasCompleteness": ["age:ratio>0.2"],
          "haveCompleteness": ["name,age:ratio>0.2"],
          "haveAnyCompleteness": ["name,age:ratio>0.2"]
        },
        "checkConsistency": {
          "isLessThan": ["n1,n2"],
          "isLessThanOrEqualTo": ["n1,n2"],
          "isGreaterThan": ["n1,n2"],
          "isGreaterThanOrEqualTo": ["n1,n2"],
          "isContainedIn": ["sex:男,女"],
          "hasMutualInformation": ["city,address:ratio>0.5"]
        },
        "checkEffectiveness": {
          "containsIdCard": ["idCard:ratio>0.8"],
          "containsMobilePhone": ["mobile:ratio>0.8"],
          "containsTelePhone": ["tele:ratio>0.8"],
          "containsBankCard": ["bankcard:ratio>0.8"],
          "containsEmail": ["email:ratio>0.8"],
          "containsURL": ["url:ratio>0.8"],
          "containsIP": ["ip:ratio>0.8"],
          "containsLongitude": ["longitude:ratio>0.8"],
          "containsLatitude": ["latitude:ratio>0.8"],
          "hasDataType": ["id:Numeric"],
          "hasPattern": ["idcard:pattern"]
        },
        "checkUniqueness": {
          "isUnique": ["id"],
          "isPrimaryKey": ["id,name"],
          "hasUniqueness": ["id:ratio==1"],
          "haveUniqueness": ["name,age:ratio>0.5"],
          "hasDistinctness": ["id:ratio==1"],
          "haveDistinctness": ["name,age:ratio>0.5"],
          "hasUniqueValueRatio": ["id:ratio==1"],
          "haveUniqueValueRatio": ["name,age:ratio>0.5"],
          "hasNumberOfDistinctValues": ["name:number>0 && number<10"]
        }
      },
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
        "sk_mysql"
      ]
    }
  ],
  "sink": [
    {
      "identifier": "sk_mysql",
      "name": "输出数据质量检测报告",
      "type": "MYSQL",
      "mode": "APPEND",
      "connection": {
        "url": "jdbc:mysql://127.0.0.1:3306/stark",
        "driver": "com.mysql.cj.jdbc.Driver",
        "user": "root",
        "password": "root",
        "dataset": "dqreport"
      }
    }
  ]
}
```

## Stark大数据治理引擎 `[正式版]` 重磅发布！基于二进制安装包，无需任何配置，解压即用！
* 全量功能免费开放，支持批流一体数据采集、CDC变化数据捕获、数据建模、机器学习算法建模和多维数据分析
* 零编码，零技术门槛，仅需配置规则文件即可完成一站式的大数据治理任务，人人都可以成为大数据专家
* 自带集群内核，支持本地模式、集群模式提交任务，集群节点支持动态扩展，可满足百亿级的多源异构数据处理需求
* 支持30+数据源，涵盖关系型数据库、NoSQL数据库、MPP数据库、消息中间件、图数据库、空间数据库、时序库、分布式文件等
* 内置20+机器学习算法，包括分类算法、回归算法、聚类算法和推荐算法等，未来还会融入深度学习及自然语言处理算法等
* 点击下载安装包：[stark-2.0.0.tgz](https://github.com/hexnn/Stark/releases/download/2.0.0/stark-2.0.0.tgz)
* 将安装包上传到服务器，执行 `tar -zxvf stark-2.0.0.tgz` 命令解压完成安装，解压后的目录结构及说明如下
```
stark-2.0.0
  /bin            # 命令行工具，Stark引擎启动入口
  /conf           # 引擎配置文件
  /connect        # CDC数据采集插件
  /data           # 样例数据，包括机器学习训练及预测样本等
  /examples       # 规则文件示例，涵盖离线、实时、批流一体、机器学习规则示例
  /jars           # 依赖包
  /kafka-logs     # kafka数据目录
  /logs           # 引擎执行日志
  /rule           # 规则文件目录
  /sbin           # 管理工具，Stark集群管理命令
  /stark-events   # 任务执行日志
  /zkdata         # zookeeper数据目录
```
* 修改 `rule/rule.json` 规则文件，指定 `source` 和 `sink` 中的数据源连接信息，执行 `bin/stark-run` 命令启动任务
* 支持多种任务提交方式，可按照实际需求自由选择，以下为 `stark-run` 命令行示例
```
Examples:
  1.以默认配置文件和规则文件运行
  $ stark-run

  2.自定义规则文件
  $ stark-run --rule ../rule/rule.json

  3.自定义配置文件和规则文件
  $ stark-run --config ../conf/stark.properties --rule ../rule/rule.json

  4.提交任务到SPARK独立集群
  $ stark-run --master spark://host:port --deploy-mode cluster

  5.提交任务到YARN集群
  $ stark-run --master yarn --deploy-mode cluster --queue default
```
* 任务执行结束后，查看 `sink` 节点指定的数据连接及输出，验证数据是否写入成功

## 联系方式
* 通过以下方式了解更多关于Stark大数据治理引擎的相关信息，也可接受各种定制化开发需求↓↓↓
* WeChat：xxx-hx-xxx（潇湘夜雨）
* Email：hexing_xx@163.com
