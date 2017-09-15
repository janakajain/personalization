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
  
---  

## Collaborative filtering based recommender systems  
<img src=figures/sarwar_fig1.png></img>

_Source: "Item Based Collaborative Filtering Recommendation Algorithms" by Sarwar et al. (2001)_  
  
The matrix in the figure above maps users to their ratings for items. These ratings can be obtained implicitely or explicitely. The algorithm outputs predictions and recommendations. Predictions are lists of probabilities assigned to items while recommendations is a list of top N items which aren't already in the user's list of rated items.  
There are two types of collaborative filtering based recommendation algorithms:  
  1. **Memory-based**: use the entire user-item data to identify the users who are _neighbors_ and then recommend items rated by similar users.
  2. **Model-based**: first develop a model of user ratings using a probabilistic approach computing the expected value of a rating by a user based on his/her ratings for other items. Machine learning approached such as Bayesian network models, clustering and rule-based models are used in this case.  
  
**Challenges**: There are two major challenges of using collaborative filtering based recommendation algorithms:  
  1. **Sparsity**: When the user-item matrix has very few entries. One case when this happens is when the number of items >> number of users, such that each user rates very few items.
  2. **Scalability**: This happens when the number of users and items increase such that the algorithm efficiency suffers.  
  
---  

## Content filtering based recommender systems  

Content filtering based algorithms look into the items rated by a user and then for a given item of unknown rating, calculate the k most-similar known-items. The similarities of these known-items with the unknown-rating are calculated. The unknown rating is then calculated as the weighted average of the ratings of the known items where the weight in the most simple case for each known-item is its corresponding similarity score. The algorithm can thus be split into two phases:  
  1. **Item similarity computation**: Similarity is a subjective term and can be calculated in a number of ways. Some of these mentioned in the paper are given below:  
    a. Cosine similarity  
    b. Correlation  
    c. Adjusted cosine similarity  
  2. **Prediction computation**: Prediction computation can also be calculated in different ways:  
    a. Weighted sum  
    b. Regression  
  
**Note**: This method takes O(n^2) time to run and thus can be used for calculating similarity scores in a batch mode.  

  
---  

## Some interesting extracts  
> "Technology has dramatically reduced the barriers to publishing and distributing information. Now it is time to create the technologies that can help us sift through all the available information to find that which is most valuable to us."  

> "Users will "vote with their feet" by refusing to use recommender systems that are not consistently accurate for them."