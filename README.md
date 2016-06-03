# NOUS : Incremental Maintenance of Knowledge Graphs
Data-driven applications critically depend on human experts,
who learn about the domain through their interaction with data
over time. NOUS presents a proposal knowledge bases that evolve over time. This
knowledge base will be useful for creating and validating
hypotheses and providing background knowledge for other analytical components.

## Introduction	
NOUS provides complete suite of capa- bilities needed to build a domain specific knowledge graph from streaming data. This includes natural language processing, entity and relationship mapping, rule learning and link prediction. Its search interface supports entity and path queries.

### Major Components of the NOUS are :

* Trusted Source Selection
* Streaming Data Extraction & Fusion
* Pattern Mining
* Link Predication
* Query Question-Answering

#### knowledge_graph
##### Graph Mining Module:
A major research contribution of NOUS is the development of a distributed algorithm for streaming graph mining. The algorithm accepts the stream of incoming triples as input, a window size parameter that represents the size of a sliding win- dow over the stream and reports the set of closed frequent patterns present in the window. 

###### Input
Graph Mining Module supports different input graph formats mentioned above. "dronedata.ttl" input file in the "data/graphmining" directory shows one such format. The input file has tab separated values representing <subject> <relation_ship> <object> <timestamp> <source_id>

`<FAA>     <releases>        <updated UAS guidance>    2015-09-22T13:00:49+00:00       http://www.uavexpertnews.com/faa-releases-updated-uas-guidance-tells-of-new-uas-leaders/`

###### Output

Graph Mining Module generates output in multiple formats. One such format shows discovered patterns with it occurrence frequency.

`(schumer        require technology on   organization    faa     must finalize regulations before        fatal drone accident    ,210)`




### How to build and execute NOUS:
#### Prerequisites
* Java 1.7 OR above
* Maven
* Apache Spark 1.2 OR above
* HDFS File System (Optional)

#### Build
NOUS is developed as a maven project so the easiest way to build the project is to use `mvn package`
#### Run
NOUS includes various components such as Graph Mining, Graph Profiling, Graph Search etc.
These components are executed using different syntax and parameters. Please read individual component section to find it execution syntax.

###### Graph Mining 
On a spark Cluster Graph Mining code can be run using :
`[SPARK_HOME]/bin/spark-submit --verbose --jars "[PATH_TO_NOUS_JAR]" --master [SPARK_MASTER]  --class "gov.pnnl.aristotle.algorithms.GraphMiner" [PATH_TO_NOUS_JAR]  [BASE_TYPE] [MIN_SUPPORT] [TYPE_THRESHOLD] [MAX_ITERATIONS] [INPUT_FILE_PATH `


Data
====
All data is in the data directory. The four data sets are described and credited below.

Citeseer
--------
This data set contains a selection of the CiteSeer data set (http://citeseer.ist.psu.edu/).

These papers are classified into one of the following six classes:

	Agents
	AI
	DB
	IR
	ML
	HCI
