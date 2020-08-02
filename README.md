# Analysis of the Benefits of Re-factoring Code

## Overview of Project:
The goal was to provide Steve with a tool that could analyse performance for a specific set of stocks in 2017 and 2018.  After delivering 
the tool, we set out to see if there was a way to improve the code such that it became both more efficient and able to handle a larger 
population of stocks.

## Results:
### Stock Analysis:
Of the stocks Steve gave us to analyse, only two stocks showed year-over-year improvement in yearly returns: RUN and TERP.  Of those two, 
only RUN had a positive return in 2018.  TERP improved their performance by virtue of having a smaller loss than the year before.  Also,
while ENPH posted smaller returns in 2018 than 2017, it still had 2018 returns of almost 82% on high volume.  See below: 


Of the 12 stocks Steve asked
me to analyse, I would strongly recommend RUN stock, and would only offer a lukewarm endorsement of ENPH, which has posted strong returns
in two consecutive years, even if trending downwards.








### Analysis of Script Performance:
Re-factoring our script definitely improved the efficiency of the code.  Establishing an index for the list of stocks allowed us not to have 
to nest the loops, which created additional permutations of code in the initial build.  In the initial analysis, the 'inner loop' relied on 
iterations of the cell coordinates in order to identify the specific stock being analyzed and and return a value:  IMAGE:CODE  As a result
the Inner Loop ran through all the data looking for one specific stock ticker (depending on which iteration it was up to) and then performed
the calculation.   With the re-factored code, the : IMAGE: CODE

The refactored code resulted in a more than 80% reduction in processing time!

IMAGE: GRAPHS (1,2,3)

##Summary:

	1. Refactoring code is useful for separating constant elements from variable elements in a piece of code.  If something is a known quantity and will be constant for all iterations
of your script (like our list of stock tickers), it is better to remove that element from the loop, create a container for it, and simply reference it in the loop.  Calculating the information
inside the loop significantly increases processing time.  Also, an effort should be made to minimize the size of nested loops, as each additional loop results in additional processing time.

	2.
