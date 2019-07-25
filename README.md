# Social-network-Graph-Link-Prediction---Facebook-Challenge
### Problem statement: 
Given a directed social graph, we have to predict missing links to recommend friends/connnections/followers (Link Prediction in graph)<br>
### Data Overview
Dataset from facebook's recruting challenge on kaggle https://www.kaggle.com/c/FacebookRecruiting  
data contains two columns: source and destination edge pairs in the directed graph.<br>
    - Data columns (total 2 columns):  
    - source_node         int64  
    - destination_node    int64  <br>
### Mapping the problem to supervised learning problem:
- Map this to a binary classification task with 0 implying an absence of an edge and 1 implying the presence of the edge. 
<br>Now, we need to featurize a pair of vertices (u_i,u_j) such that these features can help us predict the presence/absence of an edge. 

    
### Performance metric for supervised learning:  
- Both precision and recall are important, hence F1 score is good choice
- Confusion matrix

### Requinments: 
- Python3
- numpy
- pandas
- matplotlib
- seaborn
- networkx <br>
<pr> NetworkX is a Python package for the creation, manipulation, and study of the structure, dynamics, and functions of complex networks. We are using it to implement our Graphs. </pr>

## How To Use?
<ol>
  
<li> Run FB_EDA file, which has all the Exploratory Data analysis, and train test split process.</li>
<li> Run FB_Featurization which has all featurization done.</li>
<li> Run FB_Models, training part is done by Random Forest Classifier </li>
</ol>

### Featurization:
    
we will create these features for both train and test data points<br>

<ol>
<li>jaccard_followers</li>
<li>jaccard_followees</li>
<li>cosine_followers</li>
<li>cosine_followees</li>
<li>num_followers_s</li>
<li>num_followees_s</li>
<li>num_followers_d</li>
<li>num_followees_d</li>
<li>inter_followers</li>
<li>inter_followees</li>
<li>adar index</li>
<li>is following back</li>
<li>belongs to same weakly connect components</li>
<li>shortest path between source and destination</li>
  <li>Weight Features
    <ul>
        <li>weight of incoming edges</li>
        <li>weight of outgoing edges</li>
        <li>weight of incoming edges + weight of outgoing edges</li>
        <li>weight of incoming edges * weight of outgoing edges</li>
        <li>2*weight of incoming edges + weight of outgoing edges</li>
        <li>weight of incoming edges + 2*weight of outgoing edges</li>
    </ul>
</li>
<li>Page Ranking of source</li>
<li>Page Ranking of dest</li>
<li>katz of source</li>
<li>katz of dest</li>
<li>hubs of source</li>
<li>hubs of dest</li>
<li>authorities_s of source</li>
<li>authorities_s of dest</li>
</ol>

# Referance to Features:
<ol>
  <li>Jaccard Distance: http://www.statisticshowto.com/jaccard-index/ </li>
  <li>Cosine Similarity(Otsuka-Ochiai coefficient): https://en.wikipedia.org/wiki/Cosine_similarity</li>
  <li>Page Rank
    <ul>
      <li>https://en.wikipedia.org/wiki/PageRank</ul>
      <li>https://networkx.github.io/documentation/networkx1.10/reference/generated/networkx.algorithms.link_analysis.pagerank_alg.pagerank.html</li>
    </ul>
  </li>
  <li>Shortest Path: https://stackoverflow.com/questions/9430027/networkx-shortest-path-length </li>
  <li>Weakly Connected Components: https://www.quora.com/What-are-strongly-and-weakly-connected-components </li>
  <li>Adamic/Adar Index: https://en.wikipedia.org/wiki/Adamic/Adar_index </li>
  <li>Katz Centrality: 
    <ul>
      <li>https://en.wikipedia.org/wiki/Katz_centrality</ul>
      <li>https://www.geeksforgeeks.org/katz-centrality-centrality-measure/</li>
    </ul>
  </li>
  <li>HITS Score(Hubs and Authority): https://en.wikipedia.org/wiki/HITS_algorithm </li>
   </ol>

- Reference papers and videos :  
    - https://www.cs.cornell.edu/home/kleinber/link-pred.pdf
    - https://www3.nd.edu/~dial/publications/lichtenwalter2010new.pdf
    - https://kaggle2.blob.core.windows.net/forum-message-attachments/2594/supervised_link_prediction.pdf
    - https://www.youtube.com/watch?v=2M77Hgy17cg
    


