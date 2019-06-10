Research Discussion Assignment 1
================

## Discussion

Choose one commercial recommender and describe how you think it works
(content-based, collaborative filtering, etc). Does the technique
deliver a good experience or are the recommendations off-target?

<strong>Commercial Recommender: YouTube </strong>

  - YouTube’s recommendation system is one of the most sophisticated and
    heavily used recommendation systems in industry.

  - YouTube recommendations are driven by Google Brain, which was
    recently opensourced as TensorFlow. By using TensorFlow one can
    experiment with different deep neural network architectures using
    distributed training.

  - The system consists of two neural networks. The first one, candidate
    generation, takes as input user’s watch history and using <strong>
    collaborative filtering </strong> selects videos in the range of
    hundreds.

  - An important distinction between development and final deployment to
    production is that during development Google uses offline metrics
    for the performance of algorithms but the final decision comes from
    live A/B testing between the best performing algorithms.

  - Candidate generation uses the implicit feedback of video watches by
    users to train the model. Explicit feedback such as a thumbs up or a
    thumbs down of a video are in general rare compared to implicit and
    this is an even bigger issue with long-tail videos that are not
    popular.

  - To accelerate training of the model for newly uploaded videos, the
    age of each training example is fed in as a feature. Another key
    aspect for discovering and surfacing new content is to use all
    YouTube videos watched, even on partner sites, for training of the
    algorithm.

  - This way <strong>collaborative filtering</strong> can pick up viral
    videos right away. Finally, by adding more features and depth like
    searches and age of video other than the actual watches, YouTube was
    able to improve offline holdout precision results.

  - The second neural network is used for Ranking the few hundreds of
    videos in order. This is much simpler as a problem to candidate
    generation as the number of videos is smaller and more information
    is available for each video and its relationship with the user.

  - This system uses logistic regression to score each video and then
    A/B testing is continuously used for further improvement. The metric
    used here is expected watch time, as expected click can promote
    clickbait.

  - To train it on watch time rather than clickthrough rate, the system
    uses a weighted variation of logistic regression with watch time as
    the weight for positive interactions and a unit weight for negative
    ones. This works out partly because the fraction of positive
    impressions is small compared to total.

These techniques developed by YouTube engineers, delivers a good
experience to users in recommending the videos of user’s preferences.

## References

1)  [10th ACM Conference on Recommender
    Systems](https://recsys.acm.org/recsys16/)

2)  [YouTube engineers analyzed in greater detail the inner workings of
    YouTube’s recommendation
    algorithm](http://static.googleusercontent.com/media/research.google.com/en//pubs/archive/45530.pdf)
