This project is to identify fraudsters using a hybrid of statistical, machine learning and graph techniques. The statistical analysis takes a time window and analyzes the raw log to derive cumulative statistics upon which anomalies are identified (items that are significantly different than the norm). At the same time, the machine learning classifier would take the same raw data within the time window and classify items that are anomalous. 

Now having identified these anomalous items, we then apply a graph analysis on these items. Taking a longer time window (since a longer history may provide further evidence as to whether these items are indeed fraudsters), we model the nodes as the items and the directed edges as which node communicates with which other node. Having this graph, we then perform a classification using graph metrics, where we derive metrics such as triangle count and identify nodes that have the weakest communities. 

Now the nodes that were identified from the graph analysis are much more likely to be fraudster. These nodes are then passed to a human fraud analyst for confirmation. Once the confirmation is provided then this labeled data is provided as training data for the previously mentioned random forest classifier. 