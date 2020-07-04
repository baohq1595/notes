## Unsupervised Learning Proposals

- This note give a proposal about unsupervised learning and representation learning based on deep neural network.
- For a big picture about this proposal, refer to [Representation Learning: A Review and New Perspectives](http://www2.cs.uh.edu/~ceick/7362/T3-1.pdf)


### Motivation

- The performance of machine learning methods is heavily dependent on the choice of data representation (or features) on which they are applied.
- Feature engineering is important but labor-intensive and requires in depth domain knowledge.
- Learning representations of the data that make it easier to extract useful information when building classifiers or other predictors as well as many other downstream tasks (clustering, visualization like t-SNE).
- For some problems, labeled data is expensive to acquire in large amount, so learning in unsupervised manner to extract a good representation of data (from unlabeled data) can help to mitigate the problem of lack of data by applying transfer learning (need less labeled data)for specific tasks that requires labeled data.

### Expected results and usecases

- How to explore raw data distribution and use an appropriate feature extraction.
- What is the appropriate learning objective to achieve good representation.
- Explore some case studies about applying representation learning to downstream tasks (to be more specific on Case studies section).

### Case studies proposal

- Consider two works from [t-SNE](http://www.jmlr.org/papers/volume9/vandermaaten08a/vandermaaten08a.pdf) and [DEC](https://arxiv.org/abs/1511.06335): they used similar way to learn data representation in unsupervised manner, applied non-linear transformation to data, used t-student distribution to measure similarity between datapoint, some questions are:
  1. How to choose a good measurement to measure datapoint similarity (e.g t-student,...).
  2. How to measure the effective of representation learning: whether it was enough for proceeding to downstream task (classification, clustering, ...). Because, **DEC** used auxiliary loss which assumes the high confidence clustering result is the right one, so if representation learning is not good enough, it will destroy the clustering step.
  3. In real case, we do not have **k** parameter (number of clusters), so how do we know the effective of clustering results by looking at NMI (normalized mutual information) metrics like in **DEC**.
  4. **t-SNE** and **DEC** only differ in the final objective: t-SNE is for learning a good manifold of data for good 2D representation, while DEC is for clustering purpose, what is the intuition behind these objective.
