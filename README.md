An Experimental Study of Multi-stage Retrieval Systems

Information Retrieval (IR) is concerned with search over large unstructured data like web pages, emails, and image libraries, among others. One of the applications of IR is search engines, which find relevant web pages for user queries. Modern search engines, such as Google, Bing, and Baidu, encompass data structures known as inverted indices, which maintain billions of web documents and serve in fulfilling user information needs. To effectively and efficiently answer user queries, search engines typically employ three major stages, namely: (1) candidate set generation stage, (2) feature extraction stage, and (3) candidate set re-ranking stage. 

During the candidate set generation stage, a retrieval strategy is executed on top of an inverted index, which involves a ranking algorithm (e.g., BM25) to retrieve top K ranked documents for any user query. To expediate the retrieval process, retrieval strategies apply pruning models (e.g., MaxScore, WAND), which aggressively prune the number of documents fetched and ranked from inverted indices, especially if they host billions of documents and serve time-sensitive applications like search engines.

In the feature extraction stage, various features are extracted from the top K documents of any query returned in the first stage. These features are generally classified into four categories: query dependent, query independent, query-only, and contextual features. Obviously, query dependent features (e.g., scores of documents produced by the ranking algorithm) vary based on query types. In contrary, query independent features (e.g., PageRank) are not influenced by query terms but rather by the characteristics of the underlying dataset. Query-only features are document independent (e.g., query length), and contextual ones involve information about different features (e.g., the mean, variance, and standard deviation of ranking scores).

In the candidate set re-ranking stage, the features extracted by the feature extraction stage are passed to a trained machine learning model, which re-ranks the top K documents. Some of the machine learning algorithms used for re-ranking are linear classifiers, neural networks, and forest of trees, to mention just a few. After candidate set re-ranking is complete, top 10-50 results are returned as a final answer for the given user query.

Over the past several years, there has been much focus on designing and developing efficient (i.e., quick) retrieval strategies for the candidate set generation stage, while maintaining effectiveness (i.e., quality of results). Many machine learning techniques have been also applied to re-rank the K documents in order to enhance effectiveness, but in an almost complete obliviousness to retrieval strategies. To this end, we note that the three stages discussed herein are not independent. For instance, it is reasonable to assume that the quality and number of documents retrieved in the first stage impact the effectiveness and efficiency of the third stage. Moreover, the type and number of features extracted in the second stage may influence the effectiveness of the third stage. To our knowledge, this correlation between the different stages of multi-stage IR systems and its real impact on efficiency and effectiveness as experienced by users has not been fully investigated in literature.

In this thesis, we will comprehensively explore and analyze the correlation between the different stages of multi-stage IR Systems. In particular, we will ask and try to answer two major research questions. First, what are the effects of stages one and two on stage three? Said differently, which pruning techniques, ranking algorithms, and values of K in stage one and features in stage two are most impactful on stage three? As noted earlier, in stage three there are many machine learning algorithms for re-ranking top K documents. These algorithms will demonstrate different efficiencies and effectiveness based on the configurations of stages one and two. Consequently, it becomes essential to identify the optimal configurations of these two stages in order to maximize performance.

The second research question that we will ask and attempt to answer is, are there features in stage two that can be leveraged in stage one to boost the end-to-end efficiency and effectiveness of multi-stage IR systems? For example, there are many Link Analysis features such as PageRank, which are generally used by machine learning models in the third stage. We conjecture that retrieval strategies in stage one can employ some of these features to improve the precision of the top K documents. Furthermore, we hypothesize that this increased precision in stage one can serve in increasing the effectiveness of the third stage. 

This thesis suggests that the above two research questions can be answered through a comprehensive experimental study that observes, identifies, explains, and potentially models the performance of a representative search engine to various configurations. Based on the collected results and gleaned insights we will provide recommendations for best practices and promising research directions. 

