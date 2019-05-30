# Mining Graph-based Fault Classifier from the History of Bug Fixes

## Project summary
Ever since the emergence of software, locating its faults has been a hot research topic. Researchers have proposed various approaches, and such tools are widely used in the software development. Despite their incredible success, programmers still call for better tools. A study shows that some programmers are reluctant to use any tools when they are locating faults in their development. A natural way to improvement the state of the art is to learn how programmers locate faults. With the rapid development of open source software, open source communities accumulate many bug fixes. As a specific type of commits, a bug fix contains a set of buggy files and their corresponding fixed files, which illustrate how programmers repair bugs. From bug fixes, it can be feasible to learn an automatic model to locate faults, but no prior approaches have achieved that vision, due to various technical challenges. For example, a recent study indicates that most bug fixes are not compilable after checking out, which hinders most advanced static/dynamic tools from analyzing bug fixes. In this paper, we propose the first approach, called CLAFA, that trains a graph-based fault classifier from bug fixes. CLAFA is built on a recent partial-code tool called GRAPA, which enables complete code tools such as WALA to analyze partial programs as they analyze complete programs. After GRAPA builds system dependency graphs from a bug fix, CLAFA compares the graphs from the buggy code with the graphs from the fixed code to locate buggy nodes, and extracts various various graph features for the buggy and clean nodes. Based on the extraction, CLAFA trains a classifier that combines Adaboost and the decision tree learning, and the trained CLAFA can predict whether a node of a system dependency graph is buggy or not.

## Dataset
aries [training](/data/aries_9training.rar) [testing](/data/aries_9testing.rar)

mahout [training](/data/mahout_9training.rar) [testing](/data/mahout_9testing.rar)

derby [training](/data/derby_9training.rar) [testing](/data/derby_9testing.rar)

cassandra [training](/data/cassandra_9training.rar) [testing](/data/cassandra_9testing.rar)

## Data format 

- Node features

	@attribute nodevec[0] numeric
	...
	@attribute nodevec[9] numeric // F1, The main code name (full method name or field name)
	
	@attribute nodeType numeric // F2, The node type
	
	@attribute numberOfApi numeric // F3, The number of API names
	
	@attribute numberOfClientCode numeric // F4, The number of client code names
	
	@attribute numberOfDocOccurence numeric // F5, The occurrences of code names in bug reports

- Local features
D denotes data dependencies
C denotes control dependencies
indegree and in denote incoming nodes
outdegree and out denote outgoing nodes

- Global features
g denotes global features

## Related tools

The latest version of GRAPA is hosted on its [website](https://github.com/drzhonghao/grapa).

Some dependencies are available on the website of [Pattern finder](https://github.com/yewang16/pattern-finder)

