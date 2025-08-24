## Problem Definition: Drug-Drug Interaction Prediction
The ogbl-ddi dataset from [OGB (Open Graph Benchmark)](https://ogb.stanford.edu/) is a **homogeneous, unweighted, undirected graph, representing the drug-drug interaction network. Each node represents an FDA-approved or experimental drug. Edges represent interactions** between drugs and can be interpreted as a phenomenon where the joint effect of taking the two drugs together is considerably different from the expected effect in which drugs act independently of each other.

**Prediction task:** The task is to **predict drug-drug interactions given information on already known drug-drug interactions**. For the evaluation metric **we would like the model to rank true drug interactions higher than non-interacting drug pairs**. Specifically, we rank each true drug interaction among a set of approximately 100,000 randomly-sampled negative drug interactions, and count the ratio of positive edges that are ranked at K-place or above (Hits@K). We found K = 20 to be a good threshold in our preliminary experiments.

Main Graph Structure of OGB DDI
The OGB DDI dataset is represented as an undirected graph, where:
* Nodes (𝑉): Represent drugs (4,267 nodes).
* Edges (𝐸): Represent known drug-drug interactions (1,334,889 edges).
* Graph Type: Homogeneous graph (all nodes are of the same type: drugs).
* No Node Features: Unlike other OGB datasets, nodes do not have feature vectors.

**Edge Prediction Task:** The goal is binary classification of edges—predicting whether a connection (interaction) exists between two drugs.

**Graph Properties:**
**Sparse but Large:** High number of edges relative to nodes.

**High Connectivity:** Most drugs are interconnected, forming a dense interaction network.
