# kmeans-spark

The motivation (and the dataset) for this repository came from Heather Miller's course: [Big Data Analysis with Scala and Spark](https://www.coursera.org/learn/scala-spark-big-data)

The general objective of this code is to analyze a dataset using a distributed k-media algorithm, which groups the publications in the questions and answers of the StackOverflow platform according to their score. The objective is to be able to execute this in parallel for different programming languages, and then comparing the results we got from it.

StackOverflow is a very important source of documentation for software developers. However, the different responses provided by users receive very different ratings according to the value that other users consider the response provides.

This value is reflected in the score of a response. Therefore, we would like to see the distribution of questions and their answers. For example, how many highly rated responses do StackOverflow users post, and how high are their scores? Are there large differences between the highest-rated and lowest-rated responses?

Finally, we are interested in comparing these distributions for different programming language communities. Differences in distributions could reflect differences in documentation availability

For example, StackOverflow might have better documentation for a given library than the API documentation for that library. However, to avoid wrong conclusions, we will focus on the well-defined problem of grouping responses according to their scores.
