# Kmeans-Spark

The motivation (and the [dataset](http://alaska.epfl.ch/~dockermoocs/bigdata/stackoverflow.csv)) for this repository came from Heather Miller's excelent course: [Big Data Analysis with Scala and Spark](https://www.coursera.org/learn/scala-spark-big-data)

The general objective of this code is to analyze a dataset using a distributed k-media algorithm, which groups the publications in the questions and answers of the StackOverflow platform according to their score. The objective is to be able to execute this in parallel for different programming languages, and then comparing the results we got from it.

StackOverflow is a very important source of documentation for software developers. However, the different responses provided by users receive very different ratings according to the value that other users consider the response provides.

This value is reflected in the score of a response. Therefore, we would like to see the distribution of questions and their answers. For example, how many highly rated responses do StackOverflow users post, and how high are their scores? Are there large differences between the highest-rated and lowest-rated responses?

Finally, we are interested in comparing these distributions for different programming language communities. Differences in distributions could reflect differences in documentation availability

For example, StackOverflow might have better documentation for a given library than the API documentation for that library. However, to avoid wrong conclusions, we will focus on the well-defined problem of grouping responses according to their scores.

## About the data set

The data set consists in a CSV (comma-separated values) file with information about StackOverflow posts. Each line in the provided text file has the following format:

postTypeId, id, acceptedAnswer, parentId, score, tag

- postTypeId: Type of the post. Type 1 = question,
  type 2 = answer.
- id: Unique id of the post (regardless of type).

- acceptedAnswer: Id of the accepted answer post. This information is optional, so maybe be missing indicated by an empty string.

- parentId: For an answer: id of the corresponding question. For a question:missing, indicated
  by an empty string.
- score: The StackOverflow score (based on user votes).

- tag: The tag indicates the programming language that the post is about, in case it's a question, or missing in case it's an answer.

The data set was transformed into a parquet file and then loaded in a Jupyter Notebook.

## Instructions to run the code

- Install docker following the instructions provided [here](https://docs.docker.com/install/)

- Once installed, open a terminal and run:

`docker pull jupyter/all-spark-notebook`

- Check the image was downloaded correctly by running

`docker images list`

- Create the folder `work` inside the path `/home/$USER` with the following command:

`mkdir work`

- Move the files in this repository inside the `work` folder

- Start the docker container by running:

`docker run -v /home/$USER/work:/home/jovyan/work -p 8888:8888 jupyter/all-spark-notebook start-notebook.sh --NotebookApp.iopub_data_rate_limit=1.0e10`

- Open a web browser and input the url + token in the URL bar like this:

http://127.0.0.1:8888/?token=THE_TOKEN
