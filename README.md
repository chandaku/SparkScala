# SparkScala

Spark : To create big data execution engine to replace Map Reduce (A Better Execution engine). In 2012 it became part of Apache. Since 2015 people started using and became popular.

If you have huge amount of data then you may go for Spark.

Why I should use spark: Big data processing engine

Databrick who created spark -> Provide some data that to use spark 

Advantage:   Speed(Does processing with most of data in memory),
             Ease of use (can use it with java, scala, python, R, SQL)
             Runs anywhere (Spark Does not come with Storage, it's just a processing engine)

Spark can run on Cluster manager such as Hadoop Cluster, Apache Mesos, Kubernetes(Container Orchestration), Spark Standalone Cluster

Spark --> Cluster Manager --> Storage

Spark has capablity to read data from any data source: Could be RDBMS, Datawarehouse, NoSql, Cloud, SAP, Mainframe, Salesforce, BI.

Spark is also used as ETL tool

*******************************

With Hadoop there are different tools someone needs to learn to do different kind of data processing e.g. For Batch Processing with Map Reduce ease- Apache Pig, For SQL operations it's hive, for Ingest data scoop and flume , For ML --> Mahout

Hadoop is a Batch processing engine only and it's overgrowing for different use caes you need to learn these many tools,

With Spark you can achieve all these.

with spark if you want to do batch processing you should just use Spark-Core(Execution Engine and it is abstraction for RDD), 

SPARK-SQL  For SQL Developer you can use spark-sql(it will provide all sql operation)

Spark Streaming for real time analysis.

Spark-MLLIB for Machine Learning

Spark Graph for Graph analysis

Spark has all kind of data processing under it's one umberalla.


Realtime processing use case of Spark-Streaming is Fraud Detection of Credit Card Transactions and same can also solve Problem related to Machine Learning where you want to give some prediction about 


Programming Language--> Spark Library--> DataFrame/MLPipeline--> Spark Core --> [Different Source of Data such as csv, rdbms, nosql db, huge big data file, kafka event, elastic search, any file format, cassandra, orc, parke , avro]

Categories of Spark Component After Spark Core -- > Cluster--> Storage

Spark Architecture-->

First thing to understand is Spark needs resources which are provided by Cluster Manager e.g. Yarn, Hadoop. Resources are RAM, CPU required to do data processing and cluster provided these resources to Spark Context in the form of executors. These needs to be configured by some data volume calculations.

It has to be configured what will be minimum memory/CPU or maximum memory/CPU allocated for an executor.

Spark Architecture has -- Driver and Executor. Driver is Data node where SparkContext object is created which is submitted to Cluster Manager and based on requirement Cluster Manager will allocate exector or resources which are also called Worker.

When a Job is submitted From Driver(SparkContext) it will be given to Cluster Manager and Based on available processing, Cluster Manager will create some tasks and submit these tasks to worker. Once tasks are completed they will return to cluster manager and cluster manager will join the result and return to Driver Program.
        

50 GB File--> I can ask for Single Executor with 50 GB RAM, but not a good idea. then I will launch 5 executor with each 10 GB RAM and 10 CPU Core. Now How spark will do this, it will use partitioning of 50 GB file and for 1 GB data with 50 partition spread across all 5 executors. 

We need to do wise think while doing this, as CPU are limited available than RAM. so we should plan effectively. Consider following while planning:

Volume/size of data to be processed
How Processing is required i.e. some Real Time procesing or Just a Batch Processing. Think around what should be a partion size

Then calculate some number for RAM and CPU to be allocated  

*******************************************************************************

Some Hands-on: Spark Shell (See your self how to setup Saprk Shell) | To work with Python see for pyspark

once user will access spark-shell it will open spark-shell interactive and also a web-ui will be accessible on port 4040. It will also show spark-context as sc and local mode. local mode means that driver, executor will be on same machine only. You may setup a cluster on GCP or EKS

spark-shell --help, show GCP setup

*******************************************************************************

Talk about Scala programming language: 

Dynamic Type inference, Two type of variables in scala ( Immutable --> Val) (Mutable --> Var)
:paste --> Command
lazy val x = {println("Foo"); 10}

Any programming language needs essentially Driver --> Business Logic

In scala there is no such static class as in Java rather you can make a driver from singlton object in scala responsbile running a program in java

for (i<- 1 to 10 by 2) 

1 to 10 will create a range of collection from 1 till 10 and by 2 is a step function

Batch Processing which is not real time e.g. Bank Transaction processing . Data is stored and processed over a period of time EOD, weekly or monthly

example of batch processing are : Hadoop, RDD spark, SQL processing

REAL TIME PROCESSING: (Streaming) e.g. Offer on Ecommer site, Inventory management

Not sure how much volume of data

Advantage: 

Fault Tolerant
Integration with other library
You don't need learn a new language
Microbatch architecture
Batch Interval



