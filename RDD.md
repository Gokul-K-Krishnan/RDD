Abstact
1.	Resilient Distributed Datasets(RDD) is a distributed memory abstraction which is performed in-memory(RAM)   on a large cluster in a fault tolerant way.

Introduction
2.	Main Advantage of RDD is in iterative alogorithm and interactive data mining tool and Data reuse mainly when there is a  need for intermediate result to be processed.
3.	Main challenges of RDD is to developing programmable interface that can provide fault tolerance effectively
4.	Excisitng systems like RDD are distributed shared memory, key value databases and piccolo but these are nota efficient  fault tolerance 
5.	RDD provides coarse-grained transformation which means transformations(map, filter, and join)  to be applied to the whole dataset, but not individual elements on the dataset. 
6.	RDD is implemented in Spark which provides a convenient language-integrated programming interface
7.	Spark is the first system that allows a general-purpose programming language to be used at interactive speeds for in-memory data mining on clusters
8.	Spark is up to 20× faster than Hadoop for iterative applications and speeds up a real-world data analytics report by 40× times

RDD
9.	RDD Abstraction is created form stable data or from transformation.
10.	 User has control on persistance and partioning in RDD by the use of spark programming interface
11.	Main difference bettween RDD adn DSM is that DSM allows write for each element which is restricted in RDD which makes more effficent fault tolerance
12.	RDDs are best suited for applications that apply the same operation to all elements of its dataset

Spark Programming Interface
13.	Spark provides the RDD abstraction through a language integrated API similar to DryadLINQ  in Scala, a statically typed functional programming language for the Java VM.
14.	Some RDD operations in spark are join, map(one to one), flatmap(one to many), reduceByKey, groupByKey, sort
15.	Example application for iterative algorithms are Logistic regression and PageRank

Representing RDD
16.	RDD is represented in five pieces a set of partitions (which are atomic pieces of the dataset), a set of dependencies, partitioner (metadata about its partitioning scheme), iterator and data placement
17.	The dependencies are of two types narrow(map,filter,union) and wide dependencies (groupByKey)

Implementation
18.	 Spark in about 14,000 lines of Scala which runs over Mesos cluster manager allowing it to share resources with Hadoop,MPI and other applications and spark can also read data from any Hadoop input source
19.	 Whenever a job is sheduled, the sheduler examines the RDD's lineage graph to bild a  directed acyclic graph of stages to execute.Each stage contains as many pipelined transformations with narrow dependencies. scheduler assigns tasks to machines based on data locality using delay scheduling.
20.	Spark can run interactively from the interpreter to query big datasets.The two changes in spark are Class shipping  and Modified code generation
21.	Spark provides three options for storage of persistent RDDs in-memory storage as deserialized Java objects,in-memory storage as serialized data, and on-disk storage

Evaluation
22.	In spark is eavluated against Hadoop and HadoopBinMen for running a iterative machine learning algorithm like K-,means and  logistic regression for both the algorithms in the first iteration spark was the fastest in the subsequent iteraton spark was 25.3× and 20.7× than Hadoop and HadoopBinMen
23.	 Spark outperformed Hadoop with inmemory storage of binary data (HadoopBinMem) by a 20× margin. 
24.	The performance of Spark with Hadoopfor PageRank is compared using a 54 GB Wikipedia dump. 10 iterations of the PageRank algorithm ran to process a link graph of approximately 4 million articles.In which Spark was  2.4× faster over Hadoop on 30 nodes
25.	Some of the user application built using spark are In memory analytics,Traffice modelling,Twitterspam classification  and Interactive Data mining

Disscusion
26.	 Existing Programming Models are Map Reduce, DryandLINQ, SQL and Pregel.

Related Work
27.	Realted works are Cluster Programming Models, Caching Systems, Lineage and Relational Database.
