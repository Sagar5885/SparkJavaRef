# sparkTutorial
Project source code for James Lee's Aparch Spark with Java course.

Check out the full list of DevOps and Big Data courses that James and Tao teach.

https://www.level-up.one/courses/


Appache Spark

Defination:
Appache Spark is a fast in memory data processing engine which allows data workers to efficiently execute streaming, machine learning or SQL workload that requires fast iterative access to datasets.

Speed:
- Run computations in memory
- Apache Spark has an advance DAG execution engine that supports acyclic data flow and in memory computing.
- 100 times faster run in memory and 10 times faster even when run on disk than MapReduce.

Generality:
- A general programing model that enables developers to write applications by composing arbitary operators.
- Spark makes it easy to combine different processing model seemlessly in the same application.
For Example:
    - Data Classification through spark machine learning library
    - Streaming data through source via spark streaming
    - Querying the resulting data in real time through spark sql

Spark Project Managed By Gradle

RDD:
- Resilient Distributed Datasets - It is simply a capsulation around a very large scale dataset. In spark all work is expressed as either creating new RDDs, transforming existing RDDs, or calling operations on RDDs to compute a result.
Under the hood, spark will automatically distribute the data combined in RDDs across your cluster and parallelized the operations you perform on them.

- It offers two types of operations - Transformation and Actions
    Transformation - ex: filters, map
    Actions - ex: first

-General Flow:
    - Generate initial RDDs from external data
    - Apply Transformations(sample, disctinct)
    - Launch Actions

- How to create RDDs?:
    - Take existing collection from your programe and pass it to SparkContext's Parallelize method.
- Create RDDs:
    - Spark JDBC driver:
    https://docs.databricks.com/spark/latest/data-sources/sql-databases.html

    - Spark Cassandra connector:
    http://www.datastax.com/dev/blog/kindling-an-introduction-to-spark-with-cassandra-part-1

    - Spark Elasticsearch connector:
    https://www.elastic.co/guide/en/elasticsearch/hadoop/current/spark.html

sample:
    sample operations create random sample from RDD
    useful for testing purpose

disctinct:
    return disctinct rows from input RDD
    disctinct transformatoin is expensive because it requires shuffling all data across the partitions to ensure that we recieved only one copy of each element.

Some of certain operations two RDDs performs and produce results:
    Union - all including duplicates
    Intersection - all common (no duplicates)
    Substraction - substract common from one of RDD
    Cartesian product -

RDD are immutable and resilient

Lazy Evaluation

Caching and Persistance:
    Memory_only,..etc
    What if caching too much? - Spark will not break but automatically get reed of unused data and re-compute them again as per needed.
    So in this manner spark job never breaks but could be little slower because recomputation.


Spark Architecture:
    Master Slave Arch. -> Driver Program to work nodes
    Driver Program is Job/Spark Job
    Work Nodes - Slaves all nodes distributes the work load and contains Executors, cache and task

Spark Components:
    Spark Core:
        It provides Batching, scheduling and basic iq functionalities which all achive by many of Spark bellow compnents:

        Spakr SQL:
            provide SQL like interface to work with data
            we can write queries looks like sql

        Spark Streaming:
            provides an API for manupulating data streams that closely match the spark cores RDD API.
            it can work with hdfs, kafka, floom,...etc

        Spark MLlinb:
            Machine Learning Library of spark here provides many high quality algorithms and blazing speed.
            Support Java, Python,
            Algorithms and utility includes - classification, regression, clustering, collaborative filtering and dimensionality reduction, etc.

        Graph X:
            Graph computation engine build on top of Spark that enable users to interactively create, transform and reason about graph structured data at scale.

Spark Used by Data Scientist and Data process application engineers.

Pair RDD:
    Many example of Key Value Pairs
    Spark Java API allows use Scala.tupple2 class

Partition:
    Helps to partition Job


Joins:
    Default is Shuffle Join - which is costaly so it's recomended to avoid it


Accumulator:

Spark SQL:



