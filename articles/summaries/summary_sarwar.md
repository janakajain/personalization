# Summary:  "ItemBased Collaborative Filtering Recommendation Algorithms"  
  
#### Link: [http://files.grouplens.org/papers/www10_sarwar.pdf](http://files.grouplens.org/papers/www10_sarwar.pdf)  
#### Publication year: 2001 
#### Authors: Badrul Sarwar, George Karypis, Joseph Konstan, and John Riedl  
---  
  
In this paper, the authors contend how item-based recommendation algorithms fare better than user-based recommendation algorithms both in terms of speed and quality. Both these factors are becoming increasingly important with the increasing scale of operations and competition. Models based on weighted-sum and regression are compared with the one based on K-nearest neighbour to demonstrate this hypothesis. The results support the hypothesis.  

The paper explicitely describes its contributions as:  
  1. **Analysis** of item-based prediction algorithms and **identification** of different ways to implement its sub-tasks.  
  2. **Formulation** of a pre-computed model of item-similarity to increase the online scalability of item-based recommendations.  
  3. An experimental **comparison** of the quality of several different item-based algorithms to the classic user-based (nearest neighbor) algorithms.

This paper begins with a gentle introduction to the concept of recommendation and its significance in modern systems today. It briefly explains the collaborative filtering as a technique of mapping users to items and presenting similar items to similar users. It also touche upon the two challenges associated with collaborative filtering:  
  1. **Scale**: With increasing number of users and increasing amount of information stored for each user, algorithms such as KNN may not scale well.  
  2. **Quality**: of recommendations is an important factor in determining the overall utility of a recommendation system.  

These two challenges are also inter-related which adds to the complexity of the problem. In order to mitigate both these design challenges, a new approach based on item-based algorithm is proposed. Item-based algorithms avoid the bottleneck of user-size by first exploring relationships between items, and then suggesting a user with items similar to the ones he/she has already liked. This approach arguably also works around the "quality" problem claiming that the relationship betwene items is relatively static.

The paper then continues to discuss collaborative filtering algorithms and their two variants, _memory-based_ and _model-based_ approaches, before discussing a few challenges associated with _memory-based_ approaches and introducing _item-based_ approach and its sub-tasks.  
  
### Collaborative filtering based recommender systems  
<img src=figures/sarwar_fig1.png></img>

_Source: "Item Based Collaborative Filtering Recommendation Algorithms" by Sarwar et al. (2001)_  


### Some interesting extracts  
> "Technology has dramatically reduced the barriers to publishing and distributing information. Now it is time to create the technologies that can help us sift through all the available information to find that which is most valuable to us."  

> "Users will "vote with their feet" by refusing to use recommender systems that are not consistently accurate for them."