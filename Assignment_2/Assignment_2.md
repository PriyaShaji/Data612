Research Discussion Assignment 2
================

## Objective

For this discussion item, please watch the following talk [YouTube
URL](http://www.youtube.com/watch?v=3LBgiFch4_g) and summarize what you
found to be the most important or interesting points. The first half
will cover some of the mathematical techniques covered in this unit’s
reading and the second half some of the data management challenges in an
industrial-scale recommendation system.

## Music Recommendations at Scale with Spark

### Mathematical Techniques

I found the explanation of ways to find good recommendations
interesting.

1)  <strong> Manually tag attributes </strong>:

Pandora is doing with the music genome project. They have music experts
who tag a bunch of cataloges.

2)  <strong>Collaborative Filtering</strong>:

Looking at what users are listeing to and analyzing that and finding
relationships and recommending music based on that.

3)  <strong>Explicit Mtrix Factorization</strong>:

For example Netflix have bunch of movies and bunch of cataloges and
those users have rated some subset of the movies and goal is to predict
how users will rate new movies, so that those movies will be recommended
whcih are going to be rated
highly.

### Data management challenges in an industrial-scale recommendation system

1\)<strong> How SPARK helps with the I/O overhead:</strong>

By loading the ratings matrix into memory and there is no requirement to
reread from disk for every iteration. Loading into memory, cache it,
join it to where the ratings are cached and keep performing the
iterations.

2)  <strong>pairRDDFunctions:</strong>

Splits the data into key value pairs and all the PairRDDFucntions helps
to work on individual nodes.

3)  <strong>Issues with Kryo serialization:</strong>

Kryo serialization is faster than java serialization but may require you
to write and/or register your own serializers.

4)  <strong>Larger datasets:</strong>

Running with larger datasetes often results in failed executors and job
never fully recovers.
