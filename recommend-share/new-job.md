爬取文章处理程序任务识别
==
爬取文章数据流：  
1. 爬取文章保存到数据库A中。  
2. 处理程序去重、打标，结果放置于数据库B。  
3. 人工审核并对齐文章库中已有条目。  
4. 最后上线。


因此文章处理程序可以考虑设计成离线定时任务，工程基于Spark构建，并提供以下功能：
+ 爬取文本去重，考虑采用SimHash算法
+ 文本关键词提取，考虑采用TextRank算法
+ 文本聚类，考虑采用LDA算法
+ 文本命名体识别，采用词典结合CRF的方式
+ 文本词嵌入，考虑采用Word2Vec
