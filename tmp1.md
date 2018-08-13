# K nearest neighbourhood (KNN)
In pattern recognition, the k-nearest neighbors algorithm (KNN) is a non-parametric (it means that it does not make any assumptions on the underlying data distribution) method used for classification and regression. KNN is one of those algorithms that are very simple to understand but works incredibly well in practice. Therefore, KNN could be one of the first choices for a classification study when there is little or no prior knowledge about the distribution data. KNN Algorithm is based on feature similarity. It means that a given data point as a test point, how the neighbor training points determine the test point class label. Before looking into details of KNN, lets talk about some examples.

## Examples of Nonlinear Classification and Regression
Let us remind you one of the classification problems in 2 dimensions (see Figure 1).
![enter image description here](https://lh3.googleusercontent.com/Gt-RcRSLk37nDEJD3ULx8urmJz8kjNp7H7T1C1UtQyBg47IS8eQHKZe-ZeqOGb3VHKgQBGm2TzhH)
*Fig. 1: Binary Classification*.

For both classification and regression, a useful technique can be to assign weight to the contributions of the neighbors, so that the nearer neighbors contribute more to the average than the more distant ones. The basic idea is Label of the test data point is **same as the nearest neighbor**.  Figure 2 illustrates this concept. A black circle as a test point falls into a region in which the closest point is a black ellipse with class label of $1$, so based on the nearest neighbor, we are going to label this new sample as class $1$.
![enter image description here](https://lh3.googleusercontent.com/Ekphmy56jcwIlptFpe6E8Ri5Zxe00j9NBm7HU4g4Smc--Mo9ko1xYZ9E6uuQTkzwkRsefFAwvYdt)
*Fig. 2: KNN intuition*.

But also $K$ in KNN can vary. Lets say someone would like to check $K$ nearest neighbors of the test point in order to make the decision. So you can label of a test instance **same as the majority label of the K-nearest neighbours**, Below is an example of $3-$NN classification. 
![enter image description here](https://lh3.googleusercontent.com/XVBVIna0HNqviEm-05mk_GurmVl539Cn0byTfbA5IVdSWBr2_pfwKZzRNKkLiqpa40wOaGv4BgZg)
*Fig. 3: $3-$NN classification*.

As you can see in Figure 3, a new test point falls into the scope of two training points from class $0$ and one from class $1$. Obviously you trust the $0$ class due to majority.


### Theory of KNN
Now lets have a close look into KNN. Assume an arbitrary data point is represented as:
$$
\textbf{x} = [x_1,x_2,...,x_d] \in \ R^d
$$
Recall the Euclidean distance between data points:
$$
dist(\textbf{x}_i,\textbf{x}_j) = \sqrt{\sum_{r=1}^{d} (x_{ir} - x_{jr})^2}
$$
For finding the majority of decisions based on the close training points, you need to perform average or mean in continuous cases and you need to find the mode of the class labels in discrete format. To summarize:
* Continuous valued target function:
	 * **Mean value** of the $k$ nearest training examples 
* Discrete class label:
	*  **Mode of the class labels** of the $k$ nearest training examples

There is another concept partially related to KNN which is called *Voronoi Diagram*. In mathematics, a Voronoi diagram is a partitioning of a plane into regions based on distance to points in a specific subset of the plane. Have a look at Figure 4. As a Voronoi diagram, you can see it is based on closest neighbors, same concept as KNN. Also clearly data is not linearly separatable and it resulted in complex boundaries and decision rules. Remember that the decision surface formed by the training examples.
![enter image description here](https://lh3.googleusercontent.com/8tiSzQNXH2j_w64m_DnlWFHaIoxhKxULbwI6MHqPrOfbFVTNW-j1u4IUuEZUfqwiWfy7OMNyFXZx)
*Fig. 4: Voronoi diagram*.

Imagine a scenario in which some is performing $10-$NN, and the only real close points are $4$ points. The other $6$ neighbors we are going to analyse is not really related to this point. Actually it could be misleading somehow! But what if we assign different weights distances of data points. So the question here is what is a  Distance-Weighted Nearest Neighbor Algorithm?

Basically we can **Assign weights to the neighbours** based on their **distance** from the test point. For example, weight may be inverse square of the distances. This means **higher the distance** of the neighbour, **lower its weight**. All training points may influence a particular instance. This method is also known as **Shepard’s method**.

### Bayes Error

**Bayes error rate** can show us useful information about boundaries of classification error. In statistical classification, Bayes error rate is the lowest possible error rate for any classifier of a random outcome (into, for example, one of two categories) and is analogous to the irreducible error. By having the Bayes error rate, Cover and Thomas proved that  for multi-class classification using KNN,  following upper bound on error rate:
$$
R^{*} \leq R_{KNN} \leq R^{*}(\frac{2-MR^*}{M-1})
$$
where $M$ is the **number of classes**, $R^*$ is **Bayes error rate**. Asymptotically, the error rate of KNN classifier **is less** than twice the Bayes error rate! In particular, **asymptotic error rate is 0 if Bayes rate is 0**. Consider the Bayes error rate as $0.1$, then the $R_{KNN}$ for the KNN's error rate is bounded roughly like: $0.1 \leq\  R_{KNN} \leq\ (\approx 0.2)$ which is really impressive. 

In addition, there are two important remarks left in about KNN:
* Learning is very **simple** (actually, no learning involved, we just check the test data point)
* **Classification is very time consuming** because we need to find distance with all the training instances


## KNN Algorithm and its Variants
Screencasting


