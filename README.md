# DS4002-M3
---

## Table of contents[![](./images/pin.svg)](#table-of-contents)
1. [INTRODUCTION](#introduction)
2. [HYPOTHESIS](#hypothesis)
3. [SRC](#src)
4. [DATA](#data)
5. [FIGURES](#figures)
6. [REFERENCES](#references)

---

## INTRODUCTION[![](./images/pin.svg)](#introduction)
In “Differences in Emoji Sentiment Perception between Readers and Writers”, an experiment was conducted that looked at the emoji sentiment of authors versus
that of writers. Berengueres and Castro found that readers and writers broadly agree on the sentiments of emojis. The largest discrepancy between readers and writers occurs for negative emojis, such as the sad face emoji. We would like to see how emoji sentiment perception differs from country to country [1].
Even though emojis are widely used to provide a reaction through digital communication, it is still better to keep in mind that some meanings of emojis are not universally accepted. The team would like to analyze the sentiment of the top 50 most used emojis in the world. 

---

## HYPOTHESIS[![](./images/pin.svg)](#hypothesis)
In the top 50 most used emojis in the world, at least 50% of them denote more positive feelings than negative feelings, with a sentiment score above 0 on a scale from -1 to 1. Additionally, the correlation between the popularity of emojis and their sentiment scores are greater than 0.5. 

---

## SRC[![](./images/pin.svg)](#src)
![made-with-R](https://img.shields.io/badge/Made%20with-R-1f425f.svg)<br>

### Installing/Building Code
First, one must make sure that R and RStudio are installed on their system. Then, you can download the script from our src folder, along with the dataset in the data folder. Make sure that the files are saved into the same directory and change the working directory to where the files are located. Finally, you can click run to view the outputs of the code locally.


### Usage of Code
One would want to use our code to replicate and verify our results, or to possibly run further analysis on our dataset.


---
## DATA[![](./images/pin.svg)](#data)
The data is retrieved from the Kaggle website as image data. There are 12 columns total, but our analysis focus is limited to  the emoji observations, the occurrences, negative, neutral, positive and sentiment ratings. There are 752 observations total. Some questions we explored through the graphical analysis below were: What variables could be quantified numerically or categorically for analysis, what was the distribution of positive sentiment among the top 50 most used emojis, what was the score distribution by occurrence, and the linear regression for sentiment occurrence by sentiment scores. Some refinements to the hypothesis arose, as we had to make sure that there would be enough observations across the entire distribution that we analyzed (from -1 to 1 for positive sentiment). The dataset not only contains emoticons, but also includes pictographs, miscellaneous symbols, and others. Therefore, the first thing we did was to filter emojis based on their unicode.block. Then, we found 76 emoticons and limited them to the top 50 most used emoticons. Also, our goal is to find the correlation between occurrence of emoji and their sentiment scores. The number of occurrences could be really different. Thus, we analyzed log(occurrences) for our project instead. The sentiment score is calculated by ((1 * number of positive votes) + (-1 * number of negative votes)) / total number of votes.

---

## FIGURES![](./images/pin.svg)

### **Figures Table**
* Modified Data Table
* Pie Chart - Do the Top 50 Most Used Emoticons Denote More Positive Feeling?
* Scatter plot - The Correlation of Sentiment Scores and Occurences
* Linear Regression Model


### **Data Set - Modified:**
![](./figures/dataset_emoticons.png)
The data set is modified so that it only contains information for each emoticon. An emoticon, short for "emotion icon", is more widely used to express one's feeling.

### **Pie Chart:**
![](./figures/emoticon_pie.png)
To analyze whether or not at least 50% of the top 50 most used emoticons denote more positive feelings than negative feelings, we first made a pie chart. It is quite surprising to see that there are no emoticons with a sentiment score of 0. However, from the result, we can conclude that at least 50% of them have sentiment scores greater than 0 on a scale from -1 to 1, which means that they are more commonly used accompanied with positive texts. 

### **Scatterplot:**
![](./figures/score_and_occur.png)
The scatterplot shows the log(number of occurences) of each emoji on the y-axis, with the sentiment score that each emoji received on the x-axis. This allows us to visualize which emojis portray positive sentiments and which ones protary negative sentiments. Also, based on the graph, it seems like there is a correlation between two varaibles, which leads to further investigation.

### **Linear Regression Model:**
![](./figures/linear_reg_model.png)
The graph shows the result of the linear regression analysis on the tranining data. Training data are selected randomly from the full dataset. The x-axis has the sentiment score associated with the test value, and the y-axis has the log(number of occurrences) for each sentiment score. 

![](./figures/linear_reg_data.png)
The equation of trained linear regression model is log(occurences) = 1.25 * sentiment_score + 6.537. The mean standard error conducted on the testing data is 0.87. iF the MSE value is less than 1, the model is accurate, and the closer the MSE value is to 0, the more perfect a model is. 

---

## REFERENCES
## links to MI 1 and 2
https://github.com/Lychee030/DS4002-M3/blob/main/M3-2%20Data%20Analysis.pdf
