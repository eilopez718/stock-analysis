# Analysis of the Benefits of Re-factoring Code

## Overview of Project:
The goal was to provide Steve with a tool that could analyse performance for a specific set of stocks in 2017 and 2018.  After delivering 
the tool, we set out to see if there was a way to improve the code such that it became both more efficient and able to handle a larger 
population of stocks.

## Results:
### Stock Analysis:
Of the stocks Steve gave us to analyse, only two stocks showed stronger returns in 2018 than 2017: RUN and TERP.  Of those two, 
only RUN had a positive return in 2018.  TERP improved their performance by virtue of having a smaller loss than the year before. Also, 
while ENPH posted smaller returns in 2018 than 2017, it still had 2018 returns of almost 82% on high volume.  See below: 


![2017_returns](https://user-images.githubusercontent.com/68127033/89134376-b316a000-d4f2-11ea-91f7-c768e80d93ce.png)


![2018_returns](https://user-images.githubusercontent.com/68127033/89134516-d7bf4780-d4f3-11ea-87af-2f13b928f480.png)

Of the 12 stocks Steve asked me to analyse, I would strongly recommend RUN stock, but would only offer a lukewarm endorsement 
of ENPH, which has posted strong returns in two consecutive years, even if trending downwards.

### Analysis of Script Performance:
Refactoring our script definitely improved the efficiency of the code.  Establishing an index for the list of stocks allowed us not to have 
to nest the loops, which created additional permutations of code in the initial build.  In the initial analysis, the 'inner loop' relied on 
iterations of the cell coordinates in order to identify the specific stock being analyzed and return a value:  

![all_stocks_code](https://user-images.githubusercontent.com/68127033/89134674-bb6fda80-d4f4-11ea-9343-08929dc95b0d.png) 

As a result
the Inner Loop ran through all the data looking for one specific stock ticker (depending on which iteration it was up to) and then performed
the calculation.   Additionally, the "If" statements we used to derive the starting and ending prices were streamlined, since the ticker symbol
had already been defined within that loop.

![refactored_code](https://user-images.githubusercontent.com/68127033/89134669-bad74400-d4f4-11ea-983f-232df7f1a2d3.png)

As as result, the script run times for each of the years were drastically reduced:

**2017 results w/ original code:** 

![green2017](https://user-images.githubusercontent.com/68127033/89134675-bc087100-d4f4-11ea-8e64-8baf46121057.PNG)

**2017 results w/ refactored code:**

![VBA_Challenge_2017](https://user-images.githubusercontent.com/68127033/89134672-bb6fda80-d4f4-11ea-905d-1035a9e03ac1.png)

**2018 results w/ original code:**

![green2018](https://user-images.githubusercontent.com/68127033/89134668-ba3ead80-d4f4-11ea-8a83-6bd2320b38ff.PNG)

**2018 results w/ refactored code:**

![VBA_Challenge_2018](https://user-images.githubusercontent.com/68127033/89134673-bb6fda80-d4f4-11ea-8df3-d79934fc6503.png)

The refactored code resulted in a more than 80% reduction in processing time!

![Run Chart](https://user-images.githubusercontent.com/68127033/89134670-bb6fda80-d4f4-11ea-8060-dd8569d33ea5.png)

## Summary:

### Advantages and Disadvantages of Refactoring Code in General:
	Refactoring code is useful for separating fixed elements from variable elements in a piece of code.  If something 
is a known quantity and will be constant for all iterations of your script (like our list of stock tickers), it is better to remove
that element from the loop, create a container for it, and simply reference it in the loop.  Calculating the information inside the
loop significantly increases processing time.  Also, while loops are a necessary and useful way of solving problems, they are 
memory intensive and code should be written in a way to minimize the complexity of the loops being run.

### Advantages and Disadvantages of the Original and Refactored VBA script:
	The biggest advantage of re
	
	







