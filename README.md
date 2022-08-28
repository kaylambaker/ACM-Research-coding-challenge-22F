# Description

This Kaggle notebook creates a visualization of the most popular car models over the years. There are 5 graphs: 3 stacked bar graphs, 1 line graph, and 1 bar chart race graph. To create the bar chart race, the internet option must be on. The Approach section details what data was used for each graph. The graphs appear in the Kaggle notebook in the order they appear in the Approaches section.

# Approaches

## Approach 1

My initial approach was to create a stacked bar graph with the x axis as the years and the y axis as the frequency that each model appeared in each year. The first part of doing this  was to get the frequencies of the car models for each year and put it into a useful data structure; I put them into a dict with year as key and frequency as value. To do this I first figured out how to get the model frequency for 1 year and I then put that code into a loop so It would get the frequencies for all of the present years. The next part was to actually graph the data. To do this I created a pandas DataFrame from the frequencies dict. I thought that the resulting stacked bar graph that used all of the models in the carsforsale dataset was bad because the graph was very hard to read which makes the graph pretty useless.

## Approach 2

From my failures in Approach 1 I realized I would need to take a subset of the dataset in order to make my visualization readable. I decided to create a stacked bar graph of only the top 3 cars per year. To do this I created a sorted list in decreasing order of the frequencies of the models in each year. I then created a list of only the top 3 models of each year and created a dict that mapped years to frequencies. Then I created a pandas DataFrame from the dict and created a stacked bar graph of the data. I liked this graph more than the original but I thought that there may be a better subset of data I could use to create a visualization.

## Approach 3

### Approach 3.1

I decided to create a stacked bar graph with the frequencies of the top 10 overall models through the years. This graph provided an even smaller set of data to examine and shows the incline and decline of popularity of the overall top 10 models. To do this I created a sorted list in decreasing order of all of the model frequencies over the entire dataset and discarded all but the top 10. I then used the frequencies dict and DataFrame I used to create the original graph and discarded all but the top 10 models and created the stacked bar graph.

### Approach 3.2

When looking at the stacked bar graph from Approach 3.1, I thought that using a line graph might make more sense. I thought it would make more sense because with a line graph you can see the growth and decay of the popularity of each model more easily than with a bar graph.

## Approach 4

I then realized that I could make a bar chart race video with Kaggle, so I decided to do that.I used the frequencies dict and DataFrame from the original graph to do this.

## Discarded Approach

After the graph created in Approach 3.2, I was considering including a line graph that would use the top 10 models as a subset and display the percent of market share each car had. I did not end up leaving it in because the data does not have many entries for the earlier years. I felt that because of the difference in the amount of data collected for each year, the graph did not show anything that was particularly useful.

# Analysis of Project and Thoughts

While doing this project I learned a lot about creating data visualizations. The purpose of data visualizations is to create a model of data that can be read and more easily understood by humans. I realized that using a large dataset, like how I did in the first graph, is not human readable on a graph and I realized that to create a more effective visualization of the data I would have to get a smaller subset of the data. The 2nd and 3rd graphs I created were much easier to read and understand because I slimmed down the dataset.

Because this dataset does not have as many entries for the earlier years, the effectiveness and accuracy of analysis on the change of data over time done with this dataset is likely hindered by this. The lack of data for the earlier years is likely due to the popularity of the internet during that time.


# Resources Used

[pandas documentation](https://pandas.pydata.org/docs/)  
[Python 3.10.6 documentation](https://docs.python.org/3/)  
[Bar Chart Race Github](https://github.com/dexplo/bar_chart_race)  
[Bar Chart Race Documentation](https://www.dexplo.org/bar_chart_race/)  
[Tutorial on how to create mapping from 2 lists](https://www.etutorialspoint.com/index.php/548-write-a-python-program-to-map-two-lists-into-a-dictionary)   
[Bilboard Hot 100 History - Bar Chart Race](https://www.kaggle.com/code/stpeteishii/billboard-hot-100-history-bar-chart-race) - specifically used to figure out how to play a bar chart race video in Kaggle
